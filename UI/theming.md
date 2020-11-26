 MaterialApp(theme: _buildTheme(context),
        
  ThemeData _buildTheme(context) {
    final _color = mainColor;
    final ThemeData base = ThemeData.light();
    return base.copyWith(
      visualDensity: VisualDensity.adaptivePlatformDensity,
      primaryColor: _color,
      buttonTheme: base.buttonTheme.copyWith(
          buttonColor: _color,
          textTheme: ButtonTextTheme.primary,
          colorScheme: ColorScheme.light().copyWith(primary: _color)),
      iconTheme: IconThemeData(color: _color),
      scaffoldBackgroundColor: _color,
      textTheme: _buildNotebookTextTheme(base.textTheme, _color),
      primaryTextTheme: _buildNotebookTextTheme(base.primaryTextTheme, _color),
      accentTextTheme: _buildNotebookTextTheme(base.accentTextTheme, _color),
      primaryIconTheme: base.iconTheme.copyWith(color: _color),
      inputDecorationTheme: InputDecorationTheme(
        focusedBorder: OutlineInputBorder(
          borderSide: BorderSide(
            width: 2.0,
            color: _color,
          ),
        ),
        border: OutlineInputBorder(),
      ),
    );
  }

  TextTheme _buildNotebookTextTheme(TextTheme base, Color color) {
    return base
        .copyWith(
          headline5: base.headline5.copyWith(
            fontWeight: FontWeight.w500,
          ),
          headline6: base.headline6.copyWith(fontSize: 18.0),
          caption: base.caption.copyWith(
              fontWeight: FontWeight.w400, fontSize: 14.0, color: mainColor),
          bodyText1: base.bodyText1.copyWith(
              fontWeight: FontWeight.w100, fontSize: 16.0, color: mainColor),
        )
        .apply(
          fontFamily: 'OpenSans',
          displayColor: color,
          bodyColor: color,
        );
  }