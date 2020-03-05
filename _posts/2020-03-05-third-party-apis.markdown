---
layout: "post"
title: "Third party APIs"
date: "2020-03-05 11:56"
category: "Backend"
---

# What to do when your third party API fails:

 1. Circuit breaker design pattern: Check if the resource if available so your program does not crash if it does fail. FAIL FAST.
 2. Show cached content.
 3. Check for timeouts: Let the user know to try again later or wait for a few more minutes. Prevent them from refreshing the form and putting in more requests. Mark the necessary resources as unavailable.
 4. Fail gracefully and store any user-data to temporary storage.
 5. Validate the input data
 6. Network retries.
 7. Test the APIs continuously and monitor them. Keep calling the API and check if you get the right results.
 8. Rate limiting
 9. API virtualization (for testing, saves cost)
 10. synthetic / real-user monitoring
 11.  asynchronous scripting
 12. Self hosting scripts
### References:
1. https://doc.akka.io/docs/akka/current/common/circuitbreaker.html
2. https://netflixtechblog.com/fault-tolerance-in-a-high-volume-distributed-system-91ab4faae74a
