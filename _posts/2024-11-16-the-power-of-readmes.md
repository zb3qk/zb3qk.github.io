---
layout: post
title: Writing Good READMEs
categories: [Documentation]
---

### Why update the README?

The README is the first file I look at when contributing to a codebase for the first time.

A few days ago, one of my coworkers hopped on a call with our senior engineer how to test his changes on one of our services locally. 
They spent time going through a test scenario together and called it a day. Before they ended the call though I asked them to "add it to the README". Why do this? Testing can become trivial with sufficient documentation and we can save time and effort for the future. Let's add some numbers to this.

The call between the senior and the junior took 20 minutes. Writing decent documentation may take around 30 minutes. With decent documentation, testing would take a junior around 10 minutes. How can documentation save everyone's time? 
1. The time spent together took 20 minutes from both the junior and the senior
2. 30 minutes to write the documentation from the senior may be longer than 20 minutes to figure out testing once
3. But this safeguards the senior's time in the future since 20 minutes here and there across multiple months/years can add up very quickly.
4. This saves junior developers' time from the offset since 10 minutes is less than the 20 to figure things out

Let's say the need to test this codebase comes up 5 times a year, sporadically enough that the senior needs to be reminded how to do such testing. `20 minutes * 5 iterations = 100 minutes a year` which could otherwise be saved by writing documentation for 30 minutes. Additionally, `(20 - 10 minutes) * 5 iterations = 50 minutes` time from junior engineers. 

At a high level, this does not seem like a lot in the grand scheme of things. But let's say the senior engineer leaves the team. They were the only person who had context on this service and testing it. That context is now gone. It is possible to figure out that lost information, but at what cost? With a [20% annualized turnover rate for engineers](https://newsletter.pragmaticengineer.com/p/attrition), this is a very real concern. Updating README's in this way future-proofs the team and product from crashing whenever critical team-members find other opportunities.

### Writing Good READMEs

When writing a README, I'm thinking from the perspective of a contributor:
1. *New Contributor* Someone who has never worked on this codebase before
2. *Active Contributor* Someone who may have context, but has forgotten some details

The difference between each of these users is:
1. The new contributor needs one-time introductory context
2. The active contributor needs commonly used information at their fingertips

Experience and usecase will determine what information to include in a README and that may translate differently for each individual and team. Here, I'll be sharing my experience and what my READMEs look like for a web service codebase:

```md
## Overview (what does this package do)
DragonRiderService processes user messages from myWebsite.com and is responsible for returning ML/LLM based responses.
1. [architecture](linkToArchitecture)

## Contribution/Onboarding
### Initial setup

\```
# Run these commands on your local machine
command1
command2
\```

### Starting a local server
1. (hacky steps if needed) In your `build.xml` remove the line `<real-server-startup />`
2. Run the following command `docker run ...`

### Accessing local logs
1. Once your local server is running navigate to `relateive/route/to/directory`
2. Run grep/tail on the application logs with the most recent dated logs

### Testing locally
1. After server startup, navigate to `localhost:4000/explorer` in your browser
2. Use [example requests](linkToExampleRequests) to validate that your service is running as expected

## Production Details
### Logs
1. `service-log`: logs of each request and response that the service processes
2. `application-log`: logs emitted from code
3. `PMAdmin`: logs which are emitted during startup and indicate any initial runtime issues

You can access logs in production by navigating to [this website](linkToLogsWebsite)

### Dashboard/Metrics
1. [dashboard](linkToDashboard)

```

Looking back at our two contributors, the most useful sections are:
1. *New Contributor* Overview
2. *New Contributor* Initial startup/Onboarding
3. *New and Active Contributor* Server Startup
4. *New and Active Contributor* Testing your local service
5. *Active Contributors* Links to dashboards

My rule of thumb is: *Provide enough information for new contributors to start and all the common resources that active contributors use to develop*

Not everyone on your team may be zealous about writing good/useful READMEs (or any documentation for that matter), but that shouldn't stop you from saving yourself and your peers from absent README grief. When I first joined my team, many of our packages did not have READMEs. It took hours to get the initial context necessary to work on these services, but I documented that effort. I was the first person to commit a README and 3 years later others have added their contributions as well. Make sure you communicate to your team the value of a README and the time saved/risk averted by writing it. And whenever you see folks using your README, then that's a win you can communicate. 

Once contributors generate value from accessbile information (while actively contributing to it) and new hires are able to work on your codebases with ease, you can rest assured that you have a *Good README*.
