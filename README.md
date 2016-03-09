# Livelihoods

## Intro--Why _Livelihoods_ and what the $%@#* is HEA?

The Livelihoods project is basically the design of a suitable backend to store Household Economy Approach (HEA) data.

HEA ... blah, blah, blah

Presently, data are stored in **_dreadful_** spreadsheets that are a nightmare to keep concurrent, cannot be shared easily, and cannot be made publicly accessible (e.g. via the web).

## So, what am I doing here?

I'm starting out by building some JSON files with example data. These are real data sets from real assessments. The aim is to figure out how to the structure HEA livelihoods information in a document NoSQL database (like MongoDB) -- deciding stuff like where embed data, where to use (SQL-like) references, how many collections to use, etc. As a rule, I want to use as few collections as possible, without too much unnecessary repetition of documents. I am therefore building a whole baseline for a livelihood zone as a single document object, containing embedded wealth group arrays and within them, embedded interview arrays.

## And the future?

Eventually, the plan is to import this data into MongoDB and and then build a suitable platform-neutral back and front end for viewing or working on it. With a mobile front end, this will become the myLIVING app.
