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

As this was my first time using Meteor I followed their [React-Meteor tutorial](https://www.meteor.com/tutorials/react/creating-an-app) making adaptations along the way to fit the functionality I wanted in the book app.

### Adding some polish

showing the covers

veryfying book.

prettying up

masonry (http://masonry.desandro.com/)

infinite scroll


### Extending the project

Search

Login - improve/customise and add fields

subscription - limit numbers.....improve performance for when site is massive

Emails

add address



### Libraries/Frameworks

I used [Meteor](https://www.meteor.com/) as the platform. Combined with [React](https://guide.meteor.com/react.html). I also used [React Router](https://github.com/ReactTraining/react-router/tree/master/packages/react-router) for the routing.
List of book options and book cover image obtained from the [node google-books-search api](https://github.com/smilledge/node-google-books-search).
It is styled with [react-bootstrap](https://react-bootstrap.github.io/) and the Flatly theme from [boostswatch](https://bootswatch.com/).
I also used [react-selectize](https://github.com/furqanZafar/react-selectize) for the dropdown.
