return MultiProvider(
        providers: [
          ChangeNotifierProvider(
            create: (_) => UserProvider.instance(),
          ),
          ChangeNotifierProvider(
            create: (_) => HomeworkProvider(),
          ),
          ChangeNotifierProvider(
            create: (_) => NotificationProvider(),
          ),
        ],
        child: Builder(builder: (context) {
            return MaterialApp;}));