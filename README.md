# Auroras.live Changelog
A _*_ denotes an unreleased or beta product. Dates are in the form of day / month / year

## Mobile App

### 0.8.0
All changes apply to free and paid versions, except where noted.

 - Initial Play Store release
 - Free: Updated icon to denote free version
 
### 0.9.0*

 - Free: Fixed potential bug where [ads would prevent data from loading](https://github.com/Auroras-live/issues/issues/11)
 - Share icon is now [platform specific](https://github.com/Auroras-live/issues/issues/8) (e.g. Android shows Android share icon, iOS shows iOS)
 - [Back button behaviour fixed](https://github.com/Auroras-live/issues/issues/7). You now have to press back twice to exit the app
 - Day selector on Kp forecast page now has a [different colour](https://github.com/Auroras-live/issues/issues/2) to make it easier to see when you've changed the date
 - Tweaked temperature on the weather page to [avoid confusion](https://github.com/Auroras-live/issues/issues/1) for those who live in areas where the temperature drops below zero
 - A message is now displayed when loading the data times out. Pressing OK will attempt to reload the data
 - Fixed bug where the app would [let you pick](https://github.com/Auroras-live/issues/issues/12) invalid values for push notifications

## Pebble Watch
### 1.0.0
 - Initial public version

## Website
### Master
 - Initial public version

### 16/08/2016
 - Changed the dash in the temperature to a colon to avoid confusion to people who live in places where the temperature drops below 0

### 01/09/2016
 - Fixed a typo in the himawari-nz image. Now the satellite image should load correctly
 
## API
### v1
 - Initial public version

### August 5th, 2016
 - Fixed a bug where the Kp value in the current conditions embed image would appear black if > 4 but < 6

### August 18th, 2016
 - Fixed a bug where timezone offsets weren't being applied correctly. 

### September 4th, 2016
 - Bumped the throttle limit for push notification registration from 1 per 10 seconds to 2 per 10 seconds. This should eliminate a bunch of app errors for people.

## Other
