# Auroras.live Changelog
A _*_ denotes an unreleased or beta product. Dates are in the form of day / month / year

## Mobile App

### 0.8.0
All changes apply to free and paid versions, except where noted.

 - Initial Play Store release
 - Free: Updated icon to denote free version
 
### 0.9.7

 - Free: Fixed potential bug where [ads would prevent data from loading](https://github.com/Auroras-live/issues/issues/11)
 - Share icon is now [platform specific](https://github.com/Auroras-live/issues/issues/8) (e.g. Android shows Android share icon, iOS shows iOS)
 - [Back button behaviour fixed](https://github.com/Auroras-live/issues/issues/7). You now have to press back twice to exit the app
 - Day selector on Kp forecast page now has a [different colour](https://github.com/Auroras-live/issues/issues/2) to make it easier to see when you've changed the date
 - Tweaked temperature on the weather page to [avoid confusion](https://github.com/Auroras-live/issues/issues/1) for those who live in areas where the temperature drops below zero
 - A message is now displayed when loading the data times out. Pressing OK will attempt to reload the data
 - Fixed bug where the app would [let you pick](https://github.com/Auroras-live/issues/issues/12) invalid values for push notifications
 - Fixed date on the three day Kp forecast page (shows Day Name / Day of the month, instead of Month, Day of the Month)
 - Map colours updated to be easier on the eye
 - Added status messages to the loading overlay so you know at what stage the loading process is. 
 - Added loading bar so you can see (in addition to the loading statuses) how loading of data is progressing
 
### 0.9.8 *
 - Added 500 rule calculator to the new tools menu
 - Fixed [issue #16](https://github.com/Auroras-live/issues/issues/16) where iOS screen brightness would reset every time you open the app.
 
## Pebble Watch
### 1.0.0
 - Initial public version

## Website
### Master
 - Initial public version

### August 16th, 2016
 - Changed the dash in the temperature to a colon to avoid confusion to people who live in places where the temperature drops below 0

### September 1st, 2016
 - Fixed a typo in the himawari-nz image. Now the satellite image should load correctly
 
### October 16th, 2016
 - Added a clock icon to time-sensitive widgets. This tells you that the times shown are local and not UTC
 
### October 21st, 2016
 - Changed map theme
 - Added weathercam to map
 - Added day / night overlay
 - New map icons for a slicker look
 
### March 12th, 2017
 - Added colours to the thee day, nowcast and Kp widgets
 
## API
### v1
 - Initial public version

### August 5th, 2016
 - Fixed a bug where the Kp value in the current conditions embed image would appear black if > 4 but < 6

### August 18th, 2016
 - Fixed a bug where timezone offsets weren't being applied correctly. 

### September 4th, 2016
 - Bumped the throttle limit for push notification registration from 1 per 10 seconds to 2 per 10 seconds. This should eliminate a bunch of app errors for people.
  
### September 24th, 2016
 - Added state to the weather->location
 
### October 4th, 2016
 - Added humidity to the weather, primarily for the [weathercam](http://github.com/auroras.live/weathercam)
 - Sunrise, sunset, moonrise and moonset times are now timezone aware. Previously they were returned as UTC only

### October 16th, 2016
 - Bug fixed with iOS notifications (free version)
 - [Bug fixed with push notifications](https://github.com/Auroras-live/issues/issues/15) (all versions)
 
### October 25th, 2016
 - Updated AuroraMAX webcam URL to new 1080p version
 
### November 10th, 2016
 - Fixed bug in `&format=xml` parameter
 
### December 13th, 2016
 - Added throttling to the main API. Any more than 10 calls a second and you get blocked for 5 minutes. This was done to negate a DDOS on the site. Please contact admin@auroras.live for access 

### December 16th, 2016
 - Added `jsonp` as a format. See [auroraslive.io](http://auroraslive.io) > API > Introduction for developer docs
 - Added `colour` as a colour format alongside `hex` and `rgb`. See the developer docs for information 
 
### December 18th, 2016
 - Modified the logging functions so they now store the IP address. This is only used internally to help diagnose errors and better prevent DOS attacks. 
 
### December 19th, 2016
 - Caching has been rebuilt. When a call is made, the item is grabbed from the cache if it exists. If it doesn't, it is cached and returned. The `Expires` header is grabbed from the originating source, and that is the item's expiry time. If `Expires` isn't returned by the third party server, the item is cached for 60 seconds. This reduces the load time from approximately 5 seconds, down to 1 second during heavy use, and approximately 2-3 seconds during quieter times.
 
### February 5th, 2017
 - Caching has been tweaked. If the requested information has been cached (and is still valid), it is returned to the user. If the item is expired or not cached, it is fetched again and recached. If the fetching and recaching fails (which will occur if the fetching takes longer than 10 seconds), the last copy of the information is retrieved from the database. If the item doesn't appear in the database, an error is thrown. This fixes [issue 19](https://github.com/Auroras-live/issues/issues/19)
 
### April 11th, 2017
 - Bugfix for SQL caching. Prevously the caching method would cache the SQL query, which included parameters, but not parameter values. The caching method now takes into account the parameter values, so now things like the archives should now start working again.

### August 10th, 2017
 - Added `kp1minute`. Call like so: https://api.auroras.live/v1/?type=ace&data=kp1minute

## Other
