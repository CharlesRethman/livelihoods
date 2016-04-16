# Livelihoods

## Intro--Why _Livelihoods_ and what the $%@#* is HEA?

The Livelihoods project is basically the design of a suitable backend to store Household Economy Approach (HEA) data.
HEA is a _framework_ to help both practitioners and decision-makers in both policy and programmes understand how people make a living. This can be used for many things: from managing disasters to finding ways to generate jobs. It has enjoyed overwhelming use by public bodies such as government bodies, NGOs and multi-lateral agencies but it could also find more use by the private sector.  It works by building models based on an understanding of the relationships between households' assets, incomes, food sources and expenditures; for example, it can model the impact of a hazard or shock on this system, taking into account what households can actually do for themselves. This gives it the desirable capability of creating _predictions_ or _forecasts_ of human deprivation or difficulty, with an estimation of the scale and depth that can inform the design of interventions. Furthermore, these interventions and their outcomes can be measured against the forecast, given a whole set of complex variable changes.

Presently, data are stored in **_dreadful_** spreadsheets that are a nightmare to keep concurrent, cannot be shared, and cannot be made publicly accessible (e.g. via the web). The aim is to be able to capture this complex livelihoods data, organise it and provide a simple way of sharing between ground user, analysts and their audiences.

## So, what am I doing here?

I'm starting out by building some JSON files with example data. These are real data sets from real assessments. The aim is to figure out how to the structure HEA livelihoods information in a document-based NoSQL database (like MongoDB). This means I need to decide stuff like where to embed data, where to use referenced links (SQL-style), how many collections to use, etc. My purpose is to use as few collections as possible, without too much unnecessary repetition of information either. I am also thinking about atomicity, what if two users are working on different data for the same livelihood zone? This dictates that the basic document unit should be an **interview**, not a livelihood zone. The interview will then have to link to a separate **livelihoods** collection (livelihood zone-level information), so apps will have to call two queries. Wealth groups will be in embedded arrays and within the interviews.

Can this be done? Can a whole interview be stored into a single NoSQL document? So far, the data is not big (only 21 kB), despite the prettied `interview.json` file having over 500 lines. Therefore, I extrapolate that even if all 18 interviews were combined into their baselines **huge** baseline with 17 interviews of four wealth groups and community groups will only be about 2 MB; well below the limit of 16 MB and still very manageable documents for MongoDB, especially if it's running the Wired Tiger engine.

## And then what?

The plan is to import this data into MongoDB and and then build a suitable platform-neutral back-end and front-end (web, mobile) for viewing or working on it. The mobile front-end is intended to become the myLIVING app.
But first, I'll play around with the MongoDB shell and see how the data will respond. I will try to summarise it there first and calculate incomes by source and category.
There is more to come to this back-end. Livelihood Zones maps will be added (as geoJSON), as will settlements and survey centres.
