CityWatch
=============
Kinvey Android Sample App to show off Facebook Open Graph integration with deep-linking and multiple objectTypes associated with an action. This application allows users to report hazardous conditions around their town, such as traffic obstructions, fires, floods, dangerous animals, etc.

## Tutorial 
See [Kinvey's Open Graph Tutorial](http://devcenter.kinvey.com/android/tutorials/facebook-opengraph-tutorial) how to set up your in Facebook's app system and configure the backend. The tutorial covers the process of configuring the app to work with Kinvey and Facebook. 

## Using the Sample
The sample repository requires the Kinvey Android Library and Fracebook SDK that it was developed against.

* [Download Kinvey Android Library](http://devcenter.kinvey.com/android/downloads)
* [Download Facebook SDK](http://developers.facebook.com/android/downloads/)
* [Download Action Bar Sherlock](http://actionbarsherlock.com/)

### Set-up the Backend
1. Create your City App on Facebook.
    * CityWatch sample uses `kinveycitywatch` as its namespace. 
    * Set up the `report` action.
    * Set up the following objects:`Emergency`, `Fire`, `Flood`, `Health`, `Infrastructure`, `Obstruction`, `Other`, `Weather`, `Wildlife`.
    	* These inherit from `Object` and have the following Optional fields:
    	     * `location` (GeoPoint)
    	     * `severity` (String)
    	     * `risk` (String)
    	     * `repeate` (String)
    	     
2. Create a new App on [Kinvey](https://console.kinvey.com/).
    1. Create a "CityWatch" collection to store the data for each meal uploaded by the users.
    2. Set up mappings in the "Data Links" -> "Facebook Open Graph" settings. Follow the steps in [this tutorial](http://devcenter.kinvey.com/android/tutorials/facebook-opengraph-tutorial) set up the mappings between the Kinvey object and the Facebook object.
         * You'll need to paste the "get code" for the each of the object types. This will set up some of the fields and settings for your object types.
         * Map the following fields:
         	* `og:title` -> `title`
         	* `og:image` -> `imageURL`
         	* `location:latitude` -> `latitude`
         	* `location:longitude` -> `longitude`
         	* `risk` -> `risk`
         	* `severity` -> `severity`
         	* `repeat` -> `repeat
         * You will need to add additional mappings for these fields:
            * `og:description` -> `description`

    3. Add a new action `kinveycitywatch:report` to represent the reporting action.

### Set-up the App
1. In `assets\kinvey.properties:` enter your Kinvey app __App ID__ and __App Secret__.
2. In strings.xml, enter your __Facebook App ID__ in the `facebook_app_id` key.  
3. In your Android Manifest, enter your `Google Maps API Key`


## Contact
Website: [www.kinvey.com](http://www.kinvey.com)

Support: [support@kinvey.com](http://docs.kinvey.com/mailto:support@kinvey.com)