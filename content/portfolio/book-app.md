+++
title = "Book Exchange"
description = "An app for users to swap books"
slug = "book-app"
siteurl = "http://books.catherinebacon.co.uk"
githublink = "https://github.com/CatherineBacon/booktradeextension"
siteimage = "/img/book_app.png"
date = "2017-05-02"
+++


### Background

I've been steadily working through the [FreeCodeCamp](https://www.freecodecamp.com) (fcc) online bootcamp.
This app started life as part of one of fcc's [backend projects](https://www.freecodecamp.com/challenges/manage-a-book-trading-club).
However, my parents were intrigued by the site. They are members of a book club and so have a steady supply of books which they wouldn't necessarily have chosen to read and don't really want to keep. This is how my parents became my first "clients" and generated a list of requirements for them to use the site.

### Creating the app

The original fcc challenge had a fairly limited set of user stories:

- I can view all books posted by every user.
- I can add a new book.
- I can update my settings to store my full name, city, and state.
- I can propose a trade and wait for the other user to accept the trade.


#### Getting started

I wanted the site to update in real time as users added removed books without the page having to reload.
[React](https://guide.meteor.com/react.html) seemed a good choice for this as the page re-rendering would be taken care of for me. There also needed to be a database to store the books and user accounts. The database needed to link to update the React part of the site. I settled on [Meteor](https://www.meteor.com/) to do this; it seemed to combine everything I was after; it could handle user accounts and a books database and can integrate with React.

As this was my first time using Meteor I followed their [React-Meteor tutorial](https://www.meteor.com/tutorials/react/creating-an-app) making adaptations along the way to fit the functionality I wanted in this app.

### Adding some polish

Showing a list of books is fine, but I wanted something a little more engaging. So finding an api like [google-books-search](https://github.com/smilledge/node-google-books-search) was fab - I could get information about a book (author, description) as well as a pretty picture. Having this in place meant it's what I used when adding the search functionality on the AllBooks page; the search request uses the same api and returns the first ten results. The search box is one of the things I added after speaking with my parents. You'll need to search, you know, for when the site is massive ;-)

Once I had the site pretty much working (well at least fulfilling the user stories above), I decided it needing prettifying. In hindsight, I should have done this as I went along, but hey ho!

One of the first things I did was to incorporate [masonry](http://masonry.desandro.com/) to display the books and created the individual books panels. I then styled the app with [react-bootstrap](https://react-bootstrap.github.io/) and the Flatly theme from [boostswatch](https://bootswatch.com/).

Finally, I spent a long time trying to work out how to get the infinite scroll functionality of masonry to work. It took a bit of trial and error, but eventually worked out that it wasn't working, because the trigger was never appearing at the bottom of the page. A slight tweak of the margin parameter, and there you have it!

### Extending the project

At this point I had a basically functioning demo site. (One of the main downfalls was that nothing actually happened when users traded books!) Being proud of my work, I should it to my parents and it caught their imagination! After a weeks cogitation (and some pertinent questions) they gave me a list of additional functions that the site would need for them and their chums use it.

The first thing to do was to add the ability to search for books and I mentioned above. Which I was pretty pleased with once I got it up and running.

Up to this point users had been logging in with the standard accounts-ui form described in the meteor tutorial. It didn't fit the look of the rest of the site and I needed users addresses to facilitate the book trade, so I needed extra fields on each user account.

I found I kept going round in circles with user accounts and was more than a little flummoxed with the meteor documentation on adding new fields to the sign up form. After much fiddling, I decided not include the address information on initial sign up, but on a separate profile page. Which meant a prettier sign-in form and a more straightforward method of changing an address.

At this point I needed to think about subscriptions and publications. As it stood, all the books were being send to the client on the MyBooks page and I was filtering which to render. This worked ok with a small number of books, but the site would quickly become sluggish. the same is true for the AllBooks page (I may have only been displaying the first 10, but all the books were being subscribed to). The same was true for successful trades. To help improve the site's performance I added a variable to the publication/subscription which gave information on how many results to return. This initially caused me a bit of confusion, but once I understood that meteor and react acted separately, that there were meteor variables and the react state I started to see what was happening.

Lastly, for the site to actually work, users needed to be notified when to trade and where to send the book. It would also be nice if they new when another user wanted one of their books. Meteor has a built in email system which was fairly straightforward to incorporate (although it took me a shamefully long time to realise it only ran on the server!). The trickiest part of the email part was getting it set up on heroku and mailgun. I needed some assisstance with this part...I found it very confusing about how to join all the services together.

My parents have given me a longer list of requirements which I will continue to work through....let's see if they can twist their friends arm into using the site!

### Libraries/Frameworks

I used [Meteor](https://www.meteor.com/) as the platform. Combined with [React](https://guide.meteor.com/react.html). I also used [React Router](https://github.com/ReactTraining/react-router/tree/master/packages/react-router) for the routing.
List of book options and book cover image obtained from the [node google-books-search api](https://github.com/smilledge/node-google-books-search).
It is styled with [react-bootstrap](https://react-bootstrap.github.io/) and the Flatly theme from [boostswatch](https://bootswatch.com/).
I also used [react-selectize](https://github.com/furqanZafar/react-selectize) for the dropdown.
