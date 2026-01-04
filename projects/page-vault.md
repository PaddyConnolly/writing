# Page Vault

I originally attempted to build a job tracking application, and hit so many hurdles along the way that I decided to restart and thoroughly plan out a new job tracking app.

## The Issue

The issue which I kept encountering was with the web scraping, which was strange, as out of all of the technologies scoped in the project (React, TypeScript, Python Scraping, Docker etc.) it was one of the only ones I was genuinely confident with. But it was more of an architecture problem. Some companies do their best to prevent any sort of scraping bots to view their site content, and job trackers are probably some of the biggest culprits for scraping sites which don't want to be scraped. 

I had it all planned out, I would scrape the jobs, and then I would feed it to an LLM via their API which would take the HTML and spit out a lovely, JSON-formatted object, with all the information I could need.

There were two problems with this. First, LLM calls cost money, but that could be solved, I would add stronger preprocessing so I was sending less data to the LLMs, and spend less on tokens. But I didn't even get that far, because of the second problem - some sites wouldn't serve you the page at all if you were detected to be a scraper. And I know there's all sorts of things you can do to get around this, but I didn't really want to go too far with that so I started cooking up a different solution.

## The Solution

I was frustrated with the fact that I could load up a page, see the page, see the HTML, and the very same page would come back empty in my database. And then I realised, if I could just take what I could see, and send it to my app, then it would all work out.

I quickly came up with the idea for a web extension, with the sole purpose of listening in the background for a hotkey press, and that would trigger the extension sending the data to a database. You could accomplish this with a simple web server - but I didn't want to do that. I was already looking for an excuse to learn Rust, and so I decided to build the server only using Rust standard library functions.

Then I could effectively plug in this database to my Beautiful Soup parser using a FastAPI backend, and then I could serve a simple CRUD app which lets you manage your saved jobs.

Over the course of the project, I came up with various ideas for new features, including AI job content parsing and new hotkeys to mark jobs as applied on the Python side, as well as multi-threading, logging and observability on the Rust side.

I haven't mentioned React and TypeScript much because I try and do as little of that as possible.
