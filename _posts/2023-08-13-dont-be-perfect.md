---
layout: post
title:  "Don't be perfect"
---

As a fresh junior engineer, I saw fault in around every corner in our codebase and systems. The syntax, the libraries, the best practices, even the language. Everything was subpar and far from perfect. Since then, I jumpstarted various initiatives to improve that same codebase's documentation and migrating our code to [Kotlin](https://kotlinlang.org/). These two initatives had differing degrees of success. Without a doubt, both intitiatives have improved our code health, but now as a mid-level I begin to doubt their impact. Both initaitives easily took tens of hours of my time, and while it is clear that there is more Kotlin and more documentation, what has actually changed? Let's take a look:

## Documentation Initiative
First joining my team, I struggled and floundered for various reasons: personal and systemic. One of the systemic issues was a lack of documentation across our services. 
1. How do I start the service locally? 
2. How do I debug the service?
3. How does our service connect to other services end-to-end?
2. Where are the logs? How do I query those logs?
3. What are the architectural decisions made in our codebase?
4. What are the guidelines for contributing to this codebase?
5. And so much more as the days and weeks went on ...

I have the answers to these questions now, but it took 2 years to gain mastery over the services to achieve those answers. Asking my peers, forgetting the answers, deriving the answers myself again; this vicious cycle built my confidence in the processes around our services. This happened more than just once: for every new service architecture I onboarded onto. What's the solution? Documentation.

More specifically, a team effort to provide clear, concise, and comprehensive (CCC) documentation. Getting to that destination from near zero is quite the task, and quite frankly we are still not even close. Ten separate services, hundreds of files without sufficient documentation, READMEs which aren't written, standard operating procedures (sop) that are verbally communicated, we have a long way to go. I realized quickly that gathering interest from my team, particularly my seniors, as a junior engineer was a more difficult challenge than I could handle (another systemic issue). What can we do?

Take one step at a time. Sharing my gripes with a friend of mine, they replied back to me: "Be the change you want to see". Well shit. I'm no better than anyone else. I was stuck on the fact that my team would never reach CCC documentation, that I ignored the benefits of taking just one step closer to that goal. The smallest step I could come up with was to create READMEs for codebases that I worked with, including basic information. 

Taking about 15 minutes per service, I created a README with start-up information. Nearly every week before this, developers messaged in our group message (slack channel): `How do I start this service? This service is not working locally. Am I running the right commands?` For the past year since those READMEs have been created, those message have gone extinct. This documentation is clear, concise, but nowhere near comprehensive. Despite not fulfilling my criteria for our perfect documentation we have seen tangible, clear benefit from this single step.

Since then I found other gaps in knowledge and wrote SOPs for "Resolving common types of tickets" for engineering oncalls, a guide on how to use our logging interface, and various other guides for tools that our team uses: making them clearly accessible from our team wikis and chat channels. Each of these documents are used nearly every day and are actively maintained by teammates for a simple reason: *they are clearly and immediately useful*.

## Kotlin Initiative
[Learning Kotlin](https://kotlinlang.org/docs/kotlin-tour-welcome.html) is an approachable task; learning the basics only takes a day or two and it has [clear benefits](https://developer.android.com/kotlin/first) over it's predecessor, Java. Why is it so hard to get the rest of my team to believe in Kotlin? 

## Contrasting Initiatives


## Conclusion

Don't be perfect, but incrementally work towards when it really matters.