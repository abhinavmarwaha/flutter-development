
 TableCalendar(
              calendarController: _calendarController,
              events: _events,
              initialSelectedDay: DateTime.now(),
              dayHitTestBehavior: HitTestBehavior.opaque,
              initialCalendarFormat: CalendarFormat.month,
              formatAnimation: FormatAnimation.slide,
              startingDayOfWeek: StartingDayOfWeek.sunday,
              availableGestures: AvailableGestures.all,
              availableCalendarFormats: const {
                CalendarFormat.month: '',
              },
              calendarStyle: CalendarStyle(
                outsideDaysVisible: false,
              ),
              headerStyle: HeaderStyle(
                formatButtonTextStyle:
                    TextStyle().copyWith(color: Colors.white, fontSize: 15.0),
                formatButtonDecoration: BoxDecoration(
                  color: Colors.deepOrange[400],
                  borderRadius: BorderRadius.circular(16.0),
                ),
                centerHeaderTitle: true,
              ),
              onDaySelected: _onDaySelected,
              onVisibleDaysChanged: _onVisibleDaysChanged,
              onCalendarCreated: _onCalendarCreated,
              builders: CalendarBuilders(
                dowWeekdayBuilder: (context, weekday) => Padding(
                  padding: const EdgeInsets.fromLTRB(0, 0, 0, 20),
                  child: Center(
                      child: Text(
                    weekday,
                    style: TextStyle(
                        fontWeight: FontWeight.w400, color: Color(0xFFAFAFAF)),
                  )),
                ),
                selectedDayBuilder: (context, date, _) => Container(
                  color: Color(0xFFFFE6A6),
                  child: Stack(children: [
                    Align(
                        alignment: Alignment.topRight,
                        child: Text(
                          date.day.toString(),
                          style: Theme.of(context)
                              .primaryTextTheme
                              .bodyText1
                              .copyWith(fontSize: 16),
                        )),
                    ..._buildStars(date)
                  ]),
                ),
                todayDayBuilder: (context, date, _) => Stack(children: [
                  Align(
                      alignment: Alignment.topRight,
                      child: Text(
                        date.day.toString(),
                        style: Theme.of(context).primaryTextTheme.bodyText1,
                      )),
                  ..._buildStars(date)
                ]),
                markersBuilder: (context, date, events, holidays) {
                  final children = <Widget>[];

                  // if (events.isNotEmpty) {
                  //   children.add(
                  //     Positioned(
                  //       right: 1,
                  //       bottom: 1,
                  //       child: _buildEventsMarker(date, events),
                  //     ),
                  //   );
                  // }

                  return children;
                },
                dayBuilder: (context, date, events) => Stack(children: [
                  Align(
                      alignment: Alignment.topRight,
                      child: Text(date.day.toString())),
                  ..._buildStars(date)
                ]),
              ),
            ),