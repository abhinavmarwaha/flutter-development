FirebaseFirestore _firestore = FirebaseFirestore.instance;

  static final FirebaseMethods instance = FirebaseMethods._internal();

  FirebaseMethods._internal();

  bool _initialized = false;

  Future<void> init() async {
    if (!_initialized) {}}