import 'dart:io';

import 'package:clasroom_commons/models/user.dart';
import 'package:classroom/services/firebase_methods.dart';
import 'package:classroom/util/utilities.dart';
import 'package:flutter/widgets.dart';
import 'package:firebase_auth/firebase_auth.dart' as auth;

enum Status { Uninitialized, Authenticated, Authenticating, Unauthenticated }

class UserProvider with ChangeNotifier {
  auth.FirebaseAuth _auth;
  auth.User _firebaseUser;
  User _user;

  Status _status = Status.Uninitialized;

  UserProvider.instance() : _auth = auth.FirebaseAuth.instance {
    _auth.authStateChanges().listen(_onAuthStateChanged);
  }

  Status get status => _status;
  auth.User get firebaseUser => _firebaseUser;
  User get user => _user;

  Future signOut() async {
    await _auth.signOut();
    _status = Status.Unauthenticated;
    _user = null;
    notifyListeners();
    return Future.delayed(Duration.zero);
  }

  Future<void> _onAuthStateChanged(auth.User firebaseUser) async {
    if (firebaseUser == null) {
      _status = Status.Unauthenticated;
      _user = null;
    } else {
      _firebaseUser = firebaseUser;
      _user = await FirebaseMethods.instance.userFuture(_firebaseUser.uid);
      _status = Status.Authenticated;
      if (_user.userRoll != UserRoll.student) signOut();
    }
    notifyListeners();
  }

  Future<void> signinwithPhoneEmail(String phoneNo, String password) async {
    final String email = phoneNo + "@notebookapp.mathmaterate.com";
    try {
      auth.UserCredential userCredential = await auth.FirebaseAuth.instance
          .signInWithEmailAndPassword(email: email, password: password);
    } on auth.FirebaseAuthException catch (e) {
      if (e.code == 'user-not-found') {
        Utilities.showToast('No user found for that mobile No.');
      } else if (e.code == 'wrong-password') {
        Utilities.showToast('Wrong password.');
      } else {
        try {
          final result = await InternetAddress.lookup('google.com');
          if (result.isNotEmpty && result[0].rawAddress.isNotEmpty) {
            Utilities.showToast(e.code);
          }
        } on SocketException catch (_) {
          Utilities.showToast("Not Connected To internet");
        }
      }
    }
  }
}
