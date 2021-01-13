# Tamedia TDA Crawling Challenge.

## Intro 

This challenge is about showing us that you are a hacker with a fast perception and excellent analytic skills but also that you are able to build robust and scalable solutions.
We want you to build a *distibuted crawler* that retrieves a list of articles from one of our newspaper sites, does some transformations on the data and serves back the results via a simple API endpoint.

## Scenario

For an internal review, we'd like to have an API endpoint that, given a particular date (e.g. 2021-01-10), returns the **number** of articles about Covid-19 published on that day on a subsection of one of our sites (see below).

An article about Covid-19 is *defined as follows*: Contains the word "Corona" OR the word "Covid-19" in the titleHeader OR the title OR the lead:

![bl](img/challenge.jpg)


## Site to crawl

- www.tagesanzeiger.ch/schweiz - Subsection Schweiz (Switzerland)


## Step 1

You should figure out how to crawl the above website best and store the crawled articles and/or the results of your transformation steps in the appropriate storage system.

- to speed up the crawling, the program should scale horizontally, i.e. can be deployed in a cluster, while still dumping each article only once (we know that for this type of crawler, a distributed system would probably not be necessary, still we'd like to see how you would do it if it were necessary, e.g. because there are thousands of changes on the website to be crawled every day)
- bonus if you come up with some strategies regarding fault tolerance and error handling

## Step 2

Build a simple API endpoint that returns the amount of Covid-19 articles published on a particular day given that day. The method (POST or GET) and the specifics of the API are up to you. 

- the API does not have to be deployed on a cloud infrastructure for this exercise, it's enough if it runs on localhost
- bonus if you come up with a strategy for deploying the whole system on the cloud


## Step 3

Containerize the single components of your crawling system and write a [docker-compose.yml](https://docs.docker.com/compose/) for local testing.

You do not necessarily need to implement all features but make sure you document your decisions and TODOs.

Watch your time and try to get as far as possible in about 4-6 hours of hacking.


## Evaluation criterias

What we look for:

- ability to break down *business* requirements into prototype code
- code can be built and run with one command
- [Clean code](https://www.amazon.com/Clean-Coder-Conduct-Professional-Programmers/dp/0137081073/) and [architecture](https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164/)
- proper use of language and framework idioms
- usage of external libraries that should simplify the task
- strip away unneeded features, time is scarce!
- document your approach, your decisions and your general notes
- check that your last commit compiles
- send us link where to checkout code from (e.g. github)

Bonus:
- as detailed in the single steps

Hints:
- there is actually an API that our frontend uses to fetch the articles from the backend (CMS)
- the subsection is constantly updated by our journalists - make sure not to miss an article


