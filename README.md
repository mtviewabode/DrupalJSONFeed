PROJECT
   Touramador.com contracted with an app company to pull data (specifically Events and Listngs, http://www.touramador.com/calendar 
and http://www.touramador.com/things-do respectively into the VisitAmador app.  The app company needed the data in a JSON format, which this
module tama_export.module does.
 Touramador.com uses Drupal CMS, so utilizing this custom built tama_export.module, the Events and Listings 
categories were downloaded into an XML format, and then converted the XML to JSON format, and does some post-processing
as well since the app had a slightly different format than the website.

FILES
   readme.txt
   tama_export.module
   all_basic_pages.xml
   event_calendar.xml
   tama_export_live.info

DESCRIPTION
   Drupal modules are constructed along specific guidelines (see https://www.drupal.org/docs/7/creating-custom-modules/getting-started).  The modules
are written in PHP but are named *.module.  There are two hook functions: tama_export_info() which provides information, and tama_export_menu() which
connects the Drupal module to the custom function tama_export_data().

   The function tama_export_data() reads in the .xml files (all_basic_pages.xml for listings; event_calendar.xml for events) and converts XML to JSON.  
The function to process the listings "tama_export_process_listings()" does some extensive post processing because the app displays the categories "Places to Stay" and
"Restaurants" differently from the website.  The function to process the events "tama_export_process_events()", on the other hand, did not require any post-processing 
and very straightforwardly converts the raw .xml file directly to .json.

   drupal_json_output() is a Drupal api that enables *.json output.

   This module is run nightly by the app company to update the app with website data.

AUTHOR

Jo Ann Daughety

