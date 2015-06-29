App Engine application for the Udacity training course.

## Changes from last submission

added query for featured speaker to asynchonous task in main.py
removed duplicate send confirmation email function
explained query problem in README.md
did not implement Enum comparison for query problem
was not sure how to improve API path structure for queries

## Task 1:  Design Choices 

Sessions have been created as a child entity of Conferences because each session occurs within a particular conference.  Sessions can then be searched for that are in a specific conference.  typeOfSession is defined as a repeated property to allow for sessions that are have several different types associated with them. startTime was deined as a TimeProperty to allow for filtering based on time.      

Speakers have been defined as stringproperties within the Session entity.   

## Task 2:  Session Wishlist


addSessionToWishlist(SessionKey) endpoint has been defined and allows the user to add specific sesssions their wishlist.  

getSessionsInWishlist() endpoint has been defined and returns all sessions in a users wishlist.  


## Task 3:  Additional Queries 

getSessionShorterThan - this endpoints get sessions that are shorter than a certain number of minutes.  This might be useful if you only had a small amount of time and wanted to check out a portion of a conference.  

getSessionByName - this query allows the user to find a session based on the session name.  This could be useful if you wanted to find a session didn't know the conference that it was associated with.  

Description of problem - Since user is looking for sessions before 7pm and does not want workshops, two inequality filters are needed and this is not allowed.  To solve the problem, an inequality filter for time can be used, and then the program can iterate over session keeping sessions that do not have workshop in their topic.  

## Task 4:  Get Featured Speaker 

getFeaturedSpeaker has been implemented 


## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]

## Setup Instructions
1. Update the value of `application` in `app.yaml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
1. Update the values at the top of `settings.py` to
   reflect the respective client IDs you have registered in the
   [Developer Console][4].
1. Update the value of CLIENT_ID in `static/js/app.js` to the Web client ID
1. (Optional) Mark the configuration files as unchanged as follows:
   `$ git update-index --assume-unchanged app.yaml settings.py static/js/app.js`
1. Run the app with the devserver using `dev_appserver.py DIR`, and ensure it's running by visiting your local server's address (by default [localhost:8080][5].)
1. (Optional) Generate your client library(ies) with [the endpoints tool][6].
1. Deploy your application.


[1]: https://developers.google.com/appengine
[2]: http://python.org
[3]: https://developers.google.com/appengine/docs/python/endpoints/
[4]: https://console.developers.google.com/
[5]: https://localhost:8080/
[6]: https://developers.google.com/appengine/docs/python/endpoints/endpoints_tool
