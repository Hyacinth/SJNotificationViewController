# SJNotificationViewController #

SJNotificationViewController lets you put dead-simple notifications that slide up from the bottom of a view into your iOS apps.

All you need to do is import the QuartzCore framework, create a notification, give it a view to slide up from, and tell it to show itself. Like this:

	SJNotificationViewController *notificationController = [[SJNotificationViewController alloc] initWithNibName:@"SJNotificationViewController" bundle:nil];
	[notificationController setParentView:aView];
	[notificationController setNotificationTitle:@"Hello"];
	[notificationController show];
	
![](http://d.pr/WRd4+)
	
That gives you a basic notification that slides up from the bottom of `aView`. When you want your notification to slide down again, you just call `[notificationController hide]`. Pretty simple, right?

You can customise a few things about SJNotificationViewController:

## Notification Levels ##

SJNotificationViewController has a property called `notificationLevel` that changes the notification's background colour. A notification's `notificationLevel` is one of `SJNotificationLevelError` (red -- for error notifications), `SJNotificationLevelMessage` (blue -- for regular notifications), or `SJNotificationLevelSuccess` (green -- for success notifications). The exact RGB values for the notification levels aren't set in stone yet. Right now, they're extremely red, extremely blue, and extremely green.

![](http://d.pr/3XL8+)

![](http://d.pr/RLA+)

![](http://d.pr/rDGj+)

## Tapping on a Notification ##

By default, tapping on a notification just hides it, but you can define your own action/selector pair to be called when the notification is tapped with `[notificationController setTapTarget:self action:@selector(doSomething)]`.

## Spinner ##

By default, a notification doesn't have a spinner, but you can give it one by calling `[notificationController setShowSpinner:YES]`. Doing so will shrink the notification's label to fit the spinner.

![](http://d.pr/7QVJ+)

## More In-Depth Customisations ##

If you want to get into the .m file, you can change the colours that correspond to the different notification levels, the durations of the various animations, and the opacity of the notification's background.
