# Breadcrumb logger

An absolutely bare-bones, stripped-down GPS track logging application for Android, optimized for use in low-income settings. Expected to work on cheap, generic or off-brand Chinese-manufactured phones available in African markets.

The application is not intended to show a map or interact with the user other than to be launched. Users are relatively uneducated African rural surveyors who are expected to be doing something else all day, not paying attention to the GPS breadcrumb logger. The application's role is to record GPS points for later use, stay out of the way, and not consume too much power!

Intended to facilitate gathering road data in unmapped areas of low-income countries. See missingmaps.org for more details.

## Workflow

- The user activates the application. A splash screen with several drop-down options appears.
  - Logging interval (default 5 minutes, configurable from 1 second to 1 day)
  - Time until shutdown (default 9pm that same day)
  - Repeat schedule (default every day from 7am to 9pm)
- The user accepts the defaults, or modifies them with the dropdown menus, and pushes a big, obvious, "Start Logging" button. 
- The application then retires to the background, where it consumes minimum power, waking up only to take a GPS point at the specified interval.
  - Extra points if it shows a small, unobtrusive icon in the status bar at the top of the phone's screen, simply saying it's happy and working, or displaying a red "not happy" status, which when clicked shows a simple error message ("can't get a GPS fix, point overdue by 8:32," "Please activate your GPS receiver," or similar).  
- GPS points are recorded including a time-stamp, but otherwise contain minimum information.
  - Timestamp is ideally from the GPS receiver itself, not from the phone's clock, which may be set improperly (GPS time is very precise).
- The user may remember to shut off the application, but otherwise it turns off at the specified shutdown time.
- The app should ensure that in the event of a crash, a phone shutdown, or a battery running out the data up until the moment of the problem is safely recorded. Nothing fancy, just a main data file per session or day that only gets written to by appending, and a shadow copy that gets written to after the main one (in case even the append write goes wrong and somehow corrupts the file).
  - If the app runs out of memory, it should stop logging, not wrap. Do NOT throw away points taken in the past; they might be really far away! Better to lose the most recent points.
  
### Extra points
- The ability to sync data to a server is a nice bonus, but pulling the datafile from a USB cable is fine (clean folder structure and flat text files in UTF-8 are a must). The ability to sync to an ODK server would be marvellous, but again not necessary, only a nice bonus.
- The ability to send messages containing the positions at specified intervals would be a really nice bonus feature, and really help keep field teams safe!
  - For example, the phone could be set to take a GPS point every 5 minutes, but to send a position message every 30 minutes.
  - The position messages could use fallback; if the user has a data pack and the internet is working, great, use it to send all of the positions since last message! If not, fall back to SMS with only the current position (with a longer sending interval). 
