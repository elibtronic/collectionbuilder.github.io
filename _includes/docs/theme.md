The CollectionBuilder site's display options are controlled most heavily by the theme.yml found in our _data directory. These variables impact every page the site builds, so familiarizing yourself with them should be helpful. 

This file controls bits of almost every page used, including: 

- [Collection Header](#header)
- [Home Page](#home-page)
- [Item Page](#item-page)
- [Map Page](#map-page)
- [Subjects Page](#subjects-page)
- [Locations Page](#locations-page)
- [Timeline Page](#timeline-page)
- [About Page](#about-page)

{% if page.collection == "contentdm" or page.collection == "workshop" %}
This file also includes some means to [change the image sizing](#image-sizing) for the CONTENTdm images being pulled via the API. 

{:.blockquote .pl-4}
> *If your images are appearing blurry or take too long to load, try adjusting the image-sizing settings.*

{%endif%}

At the very end of the file, you can also make some sweeping changes to [the way Bootstrap looks](#bootstrap-config), from changing the color of the navbar to using totally new themes built by Bootswatch.

{:.py-4 .mt-4 #header}
***

## Header and Head metadata 
These variable determine how the header looks on all pages save for the collection home page. They also help determine the metadata variables embedded within each html page to assist with indexing of the collection.

- **tagline** - This will appear underneath the header title on all pages except the homepage.
    - example --> tagline: Photographs of University of Idaho Boxers and Boxing Teams, 1934 - 1953
- **description** - A short description of the collection. This appears on the home page in a box that has a button going to the about page for the user to learn more. 
    - example --> description: "A digital collection comprised of 52 photographs of boxers and boxing teams from the University of Idaho" 
- **author** - You! Add your github username, or just your regular old name (or your institution, or just leave it blank).
	- example --> author: dcnb


{:.py-4 .mt-4 #home-page}
***

## Home page

The home page is very customizable. The first five variables control how the large image one first sees upon coming to the site appears. The other variables control various boxes displayed on the page that detail highlights or aspects of the collection. We call this a bento box style, and if you want to delete or move variables, you can just edit the "home-infographic.html" file. See our Home Page page for more info. 

*Note:* The features that display on the home page can be customized via the "home-infographic.html" file in the layouts folder. More on customizing that file can be found in our [finishing section](finishing.html#home)

- **home-banner-image-number** - This is a CONTENTdm variable. Select the cdm-id number of any image in your collection to make it the feature image on the home page. It's best to choose an image that is large and more "landscape" than "portrait," i.e. more horizontal than vertical. 
	- example --> home-banner-image-number: 15
- **home-banner-image-link** - IF you are not using the CONTENTdm skin, use this field to link to an image you'd like to feature. This might be an object in your object directory or a link to an outside photograph. Leave blank if you enter a number above for a CONTENTdm image.
	- example --> home-banner-image-link: https://www.example.com/picture.jpg
- **home-banner-image-title** - This will create a tag for screen readers to describe the featured image. It's important for us to include accessibility features throughout; if you ever see an area that needs assistance, please let us know. 
	- example --> home-banner-image-title: 1947-1948 University of Idaho boxing squad 
- **home-title-y-padding** - This variable determines how large your featured image will appear. A smaller number will feature a smaller amount of the image. More techinically, this determines, via CSS, the margin from the top and bottom your title portion will appear.
	- example --> home-title-y-padding: 12em
- **home-banner-image-position** -  [options: top, center, bottom] Default: top | This determins what portion of the image will appear. If you'd like the bottom of a larger image to show up, put bottom. 
	- example --> home-banner-image-position: bottom
- **carousel-height** - in px, but don't include the "px"; default is 300.
	- example --> carousel-height: 500
- **featured-subjects** - If left blank, the top subjects will be automatically generated to create top 5 subjects. If you'd like to instead feature different subjects to lead to better browsing, substitute them here. Separate multiple options by semi-colon(';'). 
	- example --> featured-subjects: corn;soy;basketball
- **featured-subjects-max** - Sets number of top subjects to display if auto generating, default: 5
	- example --> featured-subjects-max: 6
- **featured-locations** - separate by semi-colon(';') - if left blank, like subjects, this will automatically generate the top 5 locations
	- example --> featured-locations: University of Idaho; Sacramento, California;
- **featured-locations-max** - set number of top locations to display if auto generating
	- example --> featured-locations-max: 4
- **mediatypes** - options[documents,images,video,audio,data,youtube] For multiples, separate by semi-colon(';'). If semi-colon is present, the browse items on the browse page will display a type field. If only one media type (and thus no semi-colon), no type field will display. 
	- example --> mediatypes: images


{:.py-4 .mt-4 #browse-page}
***

### Browse page
See our Customizations page and the config-browse.csv for these options. Fields given the "btn" option in the config-browse.CSV file can be multivalued with ";" such as subjects.




{:.py-4 .mt-4 #item-page}
***

## Item page 
- **browse-buttons** - true / false, adds previous/next arrows to items, but doubles build time. We usually add these at the end. They're a nice feature for improved browsing, as they let users use the mouse or the right and left arrows to move through the collection. 
	- example --> browse-buttons: true



{:.py-4 .mt-4 #map-page}
*** 

## Map page
{:.pl-4}
> See our [customization section on map configuration](customization.html#config-map) for field display options. 

The options below will set the center, zoom level, and optional features of your map. For larger collections with many items at one spot, we recommend turning on the map-cluster option and turning off the map-search feature. 

The map is created by using [Leaflet](https://leafletjs.com/), an open-source mapping application, and if you'd like to go even further with customization, you can visit their site and look for even more customization options. 

A user can change the layer the map is using by clicking on the Layer button at the top right of the map. The map can be searched by clicking on the magnifying glass just below the layers option at the top right. 

- **latitude**- This determines the center of map.
	- example --> latitude: 46.727485 
- **longitude**: This determines the center of map.
	- example --> longitude: -117.014185
- **zoom-level** - Determines the zoom level for your map. The higher the number, the more zoomed-in you'll be. 
	- *options:* any number between 1 and 16
	- example --> zoom-level: 5
- **map-search** - Enables a user to search the map via the large magnifying glass on the top right. This is not suggested with large collections.
	- *options:* 'true' or leave blank 
	- example --> map-search: true
- **map-search-fuzziness** - Allows for less precision with search terms. Fuzzy search range from 1 = anything to 0 = exact match only.
	- example --> map-search-fuzziness: 0.35
- **map-cluster** - This clusters markers that are near each other and is suggested for large collection or with many items in same location.
	- *options:* 'true' or leave blank 
	- example --> map-cluster: true
- **map-cluster-radius** - This determines the size of clusters, from ~ 10 to 80
	- example --> map-cluster-radius: 25


{:.py-4 .mt-4 #subjects-page}
***


## Subjects page

The subjects page is generated via a JSON file that is automatically built when the collection is generated. Subjects that appear more often will appear larger. 

With these settings, you can determine whether you want a subject page, what the minimun number of times a subject term must appear before being displayed, and any stopwords that should be removed from the tag cloud visualization. 

- **subjects-off** - true / false, turns off subject generation to lower dev build time (then page doesn't work!)
	- *options:* 'true' or 'false'
	- example --> subjects-off: false
- **subject-min** - min size for subject cloud, too many terms = slow load time!
	- *options:* 1 - 99 (note that a really large number will likely make no subjects appear)
	- example --> subject-min: 4
- **stopwords** - set of subjects separated by ;, e.g. we use boxers;boxing for boxing collection because they're unnecessary. Really, this should probably be addressed in the metadata but sometimes metadata isn't perfect.
	- example --> stopwords: boxers;boxing;boxer


{:.py-4 .mt-4 #locations-page}
***


## Locations page

This page functions exactly as the Subjects page does. If you have a 'location' field, by using the setting below to turn on the generation of the page, the tool will build a page at "locations.html"

***Impotant note:*** In order to have this page appear to your users, you must also add a row in the [_data/config-nav.csv](customization.html#config-nav) that reads: "Locations,locations.html"

- **locations-on** - true/false, - when true, will generate a location.html page. You will need to adjust the nav-configuration.csv to include the page on the header if you turn this on. 
	- *options:* 'true' or 'false' 
	- example --> locations-on: true


{:.py-4 .mt-4 #timeline-page}
***


## Timeline

The timeline is built by year, with each year become a row where thumbnail versions of the items appear. This section will let you determine which years are in the dropdown button at the top right that allows a user to jump down the page. 

- **year-navigation** - Sets years to appear in dropdown nav on top right. If left blank, these will auto-generate. (We recommend leaving this blank.)
	- example --> year-navigation: #"1900;1905;1910;1915;1920"
- **year-nav-increment** - Sets the increment at which the nav years are automatically generated. Default is '5'
	- example --> year-nav-increment: 7


{:.py-4 .mt-4 #about-page}
***

## About page

The about page is found at the base of the directory, where it's called "about.md". It's the only page file that will likely need your personal attention. More on writin the page can be found in our [finishing section](finshing.html#about).

- **about-off** - true / false, if true will not show link to about page on front "Description" section. You will need to erase the link in nav-configuration.csv as well. 
	- example --> about-off: true


{:.py-4 .mt-4 #image-sizing}
***


## images 
This is a CONTENTdm specific variable section for adjusting size of images used throughout. If your images are typically very large, you might adjust these to drop down the images being loaded. And vice versa for collections with smaller images.

- **image-percentage-large** - default 70
	- example --> image-percentage-large: 50
- **image-percentage-medium** - default 40 
	- example --> image-percentage-medium: 30
- **image-percentage-small** - default 20
	- example --> image-percentage-small: 10


{:.py-4 .mt-4 #bootstrap-config}
***


## Bootstrap Theme Options
These options will adjust the theme's color and look. 

- **navbar-color** - Choose from "navbar-light" for use with light background colors, or "navbar-dark" for dark background colors navbar-dark
	- example --> navbar-color: navbar-dark
- **navbar-background** - Choose from bg-primary, bg-secondary, bg-success, bg-danger, bg-warning, bg-info, bg-light, bg-dark, bg-white bg-dark
	- example --> navbar-background: bg-dark
    
### Change Theme with Bootswatch
Bootswatch creates themes for Bootstrap 4 sites. You can check them out here: <https://github.com/thomaspark/bootswatch>.

Choose from: cerulean; cosmo; cyborg; darkly; flatly; journal; litera; lumen; lux; materia; minty; pulse; sandstone; simplex; sketchy; slate; solar; spacelab; superhero; united; yeti 

- **bootswatch** - leave blank or comment out for plain bootstrap
	- example --> bootswatch: cerulean

gh-repository: https://github.com/uidaholib/collectionbuilder-cdm-template



{:.py-4 .mt-4}
***
