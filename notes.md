# VALA Tech Camp

## Introduction

* Overview of who I am and background
** Previously worked as a web developer, and have worked on integrating APIs from different sources to make new applications and tools

### Outline of session

* Session won't be overly technical - you won't need to be fluent in programming to get a lot out of this session. However, the session will introduce some concepts and techniques that you'll be able to use, particularly if you do more work in  web development.

* It would take a half-day or full-day workshop to build a simple tool from scratch using an API, so in the hour that we have we're going to take a slightly different approach

* Recap of the HTTP request response lifecycle
* Recap of what ReST is and why we use it for APIs
* Recap of how APIs work, and key terminology for APIs

Then, using this information we're going to go on a Treasure Hunt, using the TROVE API, to hunt down some answers. Along the way we're going to encounter some challenges, and chat about how to either avoid or overcome these as you build your tools.

* I'll be guided by you in terms of what you'd like to know, so if you're already comfortable with an area that we're covering, let me know, and equally, if you'd like to know more, or have something explained in a different way, please just let me know.

### Learning objectives

By the end of this session, you will be able to

* Understand the basics of the HTTP protocol
* Understand the concept of ReST
* Understand key terminology surrounding APIs
* Understand key steps to planning and developing simple tools based on APIs
* Have a better understanding of where to go next for help on your API journey

### Discussion

* Does anyone already have in mind a tool that you'd like to build?

## Links for the session

#### Link to the presentation online

#### API Technical Guide
* http://help.nla.gov.au/trove/building-with-trove/api-technical-guide

#### User profile, including API key
* http://trove.nla.gov.au/userProfile#developer

#### Trove API console
* http://troveconsole.herokuapp.com/


## HTTP protocol - reviewing the request response lifecycle

Cover different between a CLIENT (USER AGENT) and a SERVER

The HTTP protocol is a a REQUEST and RESPONSE protocol. The CLIENT sends a REQUEST to the server, and the server, if it does not encounter an error, sends a RESPONSE to the CLIENT.

### Exercise

* Hi, how are you?
* I'm good thanks, how are you?
* Really awesome, thanks!

* Hi, my name's Kathy! Great to meet you
* Hi, my name's XXX :D

Tin cans and string
https://flic.kr/p/8ymgpW
Wes Peck
Local Call

## ReST - Representational State Transfer

* Representational state Transfer
* Stateless
* Cacheable
* Able to update a live system
* Interact with parts of a system without impacting on the whole
* A system of resourses - each component is a resource accessible via a URL

### HTTP methods - the four verbs

The four verbs
* GET
* POST
* PUT
* DELETE


    GET − Provides a read only access to a resource.

    PUT − Used to create a new resource.

    DELETE − Used to remove a resource.

    POST − Used to update an existing resource or create a new resource.

    OPTIONS − Used to get the supported operations on a resource.

    Different resources will support different OPTIONS

    What happens if a resource does not support an option?

REST HTTP verbs from Lynda.com
https://cdn.lynda.com/video/159164-93-635298550191440052_338x600_thumb.jpg

SLIDE - ReST verbs

## What is a ReST API?

* Is a type of *architecture* - which is just a fancy word for describing how IT systems are built together
* Way of abstracting data, working with only one or a few elements at a time
* Can abstract away the underlying complexity of the database or system, allowing that system to change "under the hood" without affecting tools built on the API
* Way of leveraging multiple data sets for new and useful tools
* Building tools "on top" of existing platfroms - ie Twitter, Xero etc

## API concepts

### API keys

What are API keys and why are they used?
Used to identify the source of an API request
Can be paid or free
Used to provide different levels of access
Used to do rate limiting
https://stackoverflow.com/questions/1453073/what-is-an-api-key

### Rate limiting

A method of restricting the volume of API requests that are able to be sent
Mechanism to stop server from being overload
https://en.wikipedia.org/wiki/Rate_limiting

### Useful API tools

* Postman - https://www.getpostman.com/
* Insomnia - https://insomnia.rest
* Hurlit - https://www.hurl.it/
* HTTP Requester - https://addons.mozilla.org/En-us/firefox/addon/httprequester/

HTML exercise tools
https://thimble.mozilla.org/en-US/
Does thimble do API requests?

## Working with APIs

### What problem are you trying to solve with your tool

Before you start building your tool, it's a good idea to have a think about what problem you're trying to solve. There's some good techniques to approach this - such as user stories, wireframing, or something as simple as sketching out the flow of how you want tool to work.

### Queries

Different APIs will have different formats to request data, but there are some common syntax elements that will be useful to know

#### Executing a query

api.company.com/object/id

ie

api.twitter.com/people/3838383838

can also use a combination of parameters such as

api.company.com/?q=myQueryTerm&parameter=value&parameter2=value2

(Trove uses this approach)


#### URL encoding

Need to talk about URL encoding in queries
ie a space is %20

#### Data returned by an API

Often you'll need to use more than one API to build your tool - different APIs return data in different ways - some return XML, some return JSON, so you need to learn skills in dealing with both of these data types.

Different programming languages have different tools for handling JSON and XML, but it's useful to have an understanding of them both.

##### JSON example

{
  {
    "id:": 1482810384,
    "name": "Tim Tam",
    "species": "canine",
    "breed": "Pembroke Welsh Corgi",
    "dob": "15 March 2014",
    "faveFood": "sardines",
    "faveWord": "walkies",
    "offspring": null
  },
  {
    "id:": 2848298,
    "name": "Petra Lou",
    "species": "canine",
    "breed": "Pembroke Welsh Corgi",
    "dob": "20 September 2002",
    "faveFood": "cheese",
    "faveWord": "cuddles",
    "offspring":
      {
        "name": "Deborah Lou",
        "name": "Jemima Lou"
      }
  }

}

##### XML example

<?xml version="1.0" encoding="UTF-8"?>
<animal>
  <id>1482810384</id>
  <name>Tim Tam</name>
  <species>canine</species>
  <breed>Pembroke Welsh Corgi</breed>
  <dob>15 March 2014<dob>
  <faveFood>sardines</faveFood>
  <faveWord>walkies</faveWord>
  <offspring></offspring>
<animal>
<animal>
  <id>2848298</id>
  <name>Petra Lou</name>
  <species>canine</species>
  <breed>Pembroke Welsh Corgi</breed>
  <dob>20 September 2002<dob>
  <faveFood>cheese</faveFood>
  <faveWord>cuddles</faveWord>
  <offspring>
    <name>Deborah Lou</name>
    <name>Jemima Lou</name>
  </offspring>
<animal>


## Treasure Hunt

### Problem statement

_Using open data, I want to build a small web application that showcases influential people in STEM - science, technology, engineering and maths - in Australia._

I'm going to use Trove as a starting point, and then as we explore challenges in building apps with APIs, we'll look at some other tools.

### What problem are you solving?

Building simple tools with APIs is at its core problem solving. We build and make tools to solve problems. So, before you begin building your tool or app, pay close attention to

* what problem you're solving - are you solving the right problem?
* who you're solving the problem for, and what their needs are - are you solving the problem for the right person?
* how you're solving the problem - are you providing the right solution to the right problem?

### Problem: How do you find the API for your tool?

* https://www.programmableweb.com/
* https://www.programmableweb.com/news/49-library-apis-librarything-worldcat-search-and-bookshare/2012/11/06

### Understanding the services of the API

* different data formats
* different 'endpoints' supported in the API
* different actions supported
* rate limits in the API
* how the data is paged or sequenced - esp. if a lot of data is returned
* API key or agreement - what is required - commercial vs non-commercial

### Constructing a request to an APIs

### First Vice-Chancellor - finding out data using newspapers

Deakin University opened in Geelong in the 1970s. Who was the first Vice Chancellor of the University? Which University were they previously from? What was their academic discipline? Why was this unusual?

http://api.trove.nla.gov.au/result?q=geelong AND deakin university&zone=newspaper&l-decade=197&encoding=json&key=vitbcjb0reu355og&sortby=relevance

* Zone - newspaper
* Query - Geelong AND Deakin University
* l-decade parameter - filter just to the 1970s
* encoding - json
* sortby parameter

Decompose the Query

### Finding more information on a specific person

This person is often referred to by their two initials and their surname. What do those two initials stand for?

We can use a different ZONE of the Trove API to do a people based search.

http://api.trove.nla.gov.au/result?q=jevons&zone=people&encoding=json&key=vitbcjb0reu355og&sortby=relevance

This query brings back 17 results - what could we do to make it more specific?

http://api.trove.nla.gov.au/result?q=jevons f r&zone=people&encoding=json&key=vitbcjb0reu355og&sortby=relevance

This result only brings back a URL, the ID of this person.

The other thing we could do here is sort by relevancy

What happens when we do a GET request on this URL?

This comes back as HTML - not as data.

Is there a way for this record to be shown as JSON data?

Unfortunately the Trove API doesn't have a People zone.

The service address is: http://www.nla.gov.au/apps/srw/search/peopleaustralia

### Problem: APIs are often incomplete or only provide a portion of what you need for your app / mashup

How do you work around them?
Do you need another API to use?
Is there another way to get the data you wish to display?


### Where do I go next?

If you're interested in building your application out further,
