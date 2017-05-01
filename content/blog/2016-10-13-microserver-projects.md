---
title:  "First Node projects"
description: "Two microserver projects done!"
date: "2016-10-13"
slug: "first-node-projects"
---
I've just completed the first two microserver node-based projects in the backend section of [FreeCodeCamp](https://www.freecodecamp.com). Woohoo!

## Time stamp microserver

Check out the first one [here](https://fcctimestampmicroserver.herokuapp.com/).

When someone updates the url with either a unix time or a natural date (in the month day, year format) it returns the result in json as follows:

```javascript
{ "unix": 1412985600000, "natural": "October 11, 2014" }
```

I started by just trying to get the server to return the string from the url. Then I moved on to getting it to return a json object. At that point I moved on to thinking about the date.... this is where things got tricky. Using the `new Date(n)` method and all the associated methods really helped. I got a bit unstuck with the data type (the input was always a string, so how could the server identify when it was a number representing unix time?), this led to a slightly unsatisfying bit of code converting strings to numbers and testing to see if it was succesful. Check out the code for the project [here](https://github.com/CatherineBacon/fcc-time-stamp-api).

Moving the project to heroku was intersting. It required a little bit of tweaking with the settings to get started. Changing the package.js file was a new thing for me. I'd not come across this before and needed to be pointed in the right direction. Kinda neat now I've done it though, and its great to think that something I've written is out there in the world :-).

In summary, my server works by taking the string at the end of the url, and it tries to parse it to a number. If it succeeds the server uses the number as the unix time and converts it to a date. If it is not a number, it takes the original string and converts that to the date. If the date is invalid it returns `null` for both the unix and natural dates in json. Otherwise it spits out the unix time and natural date using the methods associated with the inbuilt `Date()` method.

If I were to keep working on the microserver I'd make the front page much prettier and easier to use - the date wouldn't be passed via the url, but rather through a form or something similar. I'd also update the code so a wider variety of date formats work (being British, I can't get the hang of month-day-year, I'm a fan of day-month-year or year-month-day).

Once I'd got this microserver just about acceptable, I moved on to the second node project...


## User information microserver

The second one is [here](https://fccheaderparsermicroserver.herokuapp.com/).

It parses information in the request header and returns it as json in the following format:

```javascript
{"ip": users-ip-address, "language": browsers-language-setting, "os": operating-system-of-the-browser}
```

I used this project as a first foray into test driven development. :-o

Test driven devlopment was tough. I found it really complex to write the tests to start with. I can see why it is useful, but at the level I'm at, it took longer the write the tests than the code itself! I got particularly stuck around having to set information for the tests, I think this is called 'defining the test environment', but setting something then testing that you set it seemed counter intuitive to me.

Once the tests were written, the code for this isn't too different to the project above, it took a little bit of googling to find how to access the header information from the `req`, but once you know how to get to it, creating and returning the json object was not too tricky. See the code [here](https://github.com/CatherineBacon/fcc-header-parser).

If I were to keep improving this project, I'd make the landing page nicer and more user-friendly, I'd also present the ip address in a much nicer format.

As it is, I think it's good to go! On to a url shortening microserver for the next task!
