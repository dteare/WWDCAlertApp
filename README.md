This is a simple app that will generate a local notification every time [WWDC page](https://developer.apple.com/wwdc/) updates.

It refreshes every 2 mins and caches the last fetched content of [WWDC page](https://developer.apple.com/wwdc/). If the most recent content is not exactly same as previously cached copy (using `[NSString isEqualToString]`), it will trigger a UILocalNotification. 

The app also generates a UILocalNotification, if the app is killed or there was an error fetching the latest [WWDC page](https://developer.apple.com/wwdc/).

Here's my [Blog post](http://rmatta.com/day/2013/03/20) on the App.

#### How does it run in background?

The app registers for background mode to receive location updates. Every time it is backgrounded, it kicks off a background task that wakes up every 2 mins to refresh the [WWDC page](https://developer.apple.com/wwdc/). If the app is running out of background time allotted to it, it triggers location update on CLLocationManager, which allows for a reset of (bumps up) allotted background time to the app. As you might have already realized, this app will use GPS approximately every 9 mins and also use network to refresh [WWDC page](https://developer.apple.com/wwdc/) every 2 mins; so beware of the high battery consumption. _On an iPhone 5, it drained 15% of battery over 6 hours, while running in the background._

Please feel free to modify and run it on your local devices to be able to track WWDC tickets. If you find a bug, please submit a fix/report to the repo for everyone to benefit. Also, this app was put together quickly over an evening, and has not been field tested well, so please do not make this the only source of tracking WWDC date update and use other means as well.

*NOTE*: This app will NOT be approved (rightfully so) by Apple for the AppStore. It uses location updates to be able to run in the background. There is no valid reason for this type of app to use location updates.

## Credits

This app uses to [AFNetworking](https://github.com/AFNetworking/AFNetworking) to download [WWDC page](https://developer.apple.com/wwdc/).

## Contact

Find me on Twitter: [@rmatta](https://twitter.com/rmatta)
