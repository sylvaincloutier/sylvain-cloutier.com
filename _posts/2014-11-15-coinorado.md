---
layout: post
title: "Coinorado"
date: 2014-11-15
---

#### Main Idea

For this [Hackathon][], I worked with my roommates [Sam][] and [Cris][],
to develop a Bitcoin based [remittence system][] that was accessible
through basic SMS messaging. We stayed up for 24 hours and ended up
winning half a bitcoin at the competition!

#### Technology Used

Twilio, Heroku, Python Flask, Blockchain API, Git

<figure>
		<img class="displayed" src="/pictures/coinorado/coinorado_twilio.png" alt="Twilio" width="50%" height="50%" align="middle">
		<figcaption> Working with Twilio</figcaption>
</figure>

#### Summary

There were three aspects of the project that we needed to solve to make
it work: Interfacing with SMS, parsing input, and making the Bitcoin
transactions. To actually receive the messages, I setup an account and
started working with the Twilio API. I redirected these messages to a
Flask server we had set up and were hosting on Heroku that would parse
the information of the SMS string and make the proper calls to the
Blockchain API to handle the actual bitcoin transactions. By the end of
the 24 hour competition we were able to create accounts, check balances,
and send bitcoins all via SMS messages. We probably lost about 6 hours
(25%) of our work by making a bad push to our Heroku server, which
happened to work on our local Flask instance. We started getting an
ominous “Internal Server Error” that not even Heroku’s rollbacks would
fix. This just goes to show how lack of sleep can impair logical
thinking and create negative feedback loops, especially in a group
context.

#### Hard Lessons Learned

Make Git tags! We lost 25% of our work because we weren’t working with
Git properly, something made more complex by the two origins we were
using for Github and Heroku. If we had had a proper Git tag every hour
or so, we would have had a much easier time spinning up new servers
based on our tags in case of catastrophic failures.

<figure>
		<img class="displayed" src="/pictures/coinorado/server_error.png" alt="Server Error!" width="75%" height="75%">
		<figcaption>The Dreaded Server Error!</figcaption>
</figure> 

#### Soft Lessons Learned

I recognized how important it is when working in a group to meet often
and debug regularly, the essence of the Agile system. We were far more
productive group programming and discussing our plans in real time that
working independently in our own bubbles.

  [Hackathon]: http://www.colorado.edu/studentgroups/bitcoin/coin-orado
  [Sam]: https://github.com/untra
  [Cris]: https://github.com/cdsalazar
  [remittence system]: https://github.com/antsankov/coinorado_hackathon
  [Twilio]: /pictures/coinorado/coinorado_twilio.png
  [Server Error!]: /pictures/coinorado/server_error.png =1