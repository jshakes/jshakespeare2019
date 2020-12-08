---
date: 2020-12-07 12:20:52+00:00
title: How did JavaScript’s console.log get its name?
description: Let’s take an etymological stroll through history and find out how these two unusual words ended up in JavaScript.
featured_image: post_images/log-lady-twin-peaks.jpg
featured_image_caption: Catherine E. Coulson gives `console.log` a different meaning as the Log Lady in *Twin Peaks*
featured_image_alt: Still from the 1980s TV show Twin Peaks showing actress Catherine E. Coulson as the Log Lady stroking her pet log
slug: javascript-console-log-etymology
---

If you’re a JavaScript developer you will be familiar with `console.log`, a function for printing a value to the console. `console.log` is often used for debugging, and if you’re a great JavaScript developer like me, you mostly use it to determine whether your code is working by printing things like `'asdasdsds'` or `'HELLO IS THIS RUNNING?!?!'`.

```javascript
const msg = 'JavaScript is fun';
console.log( msg );
```

```text
> 'JavaScript is fun'
```

Even if you write `console.log` many times a day, you probably haven’t stopped to think about how the words ‘console’ and ‘log’ ended up in a programming language. Isn’t ‘console’ something you do when someone is upset? Isn’t a ‘log’ something you put on a fire? 

Let’s take an etymological stroll through history and see what we can find. Our journey will take us from the early days of computing to medieval churches to the high seas, and we’ll learn that the seemingly unrelated definitions of these words have more in common than you might think.

## Console

This is a JavaScript debugging console. It displays messages that help a programmer understand what’s happening in the code that’s being executed.

{{< figure class="post__figure--medium" src="/post_images/js-console.gif" alt="A screenshot of the JavaScript debugging console in Google Chrome showing various logged messages" caption="The JavaScript console in Google Chrome’s developer tools. Messages from `console.log` (or in the case of the red and yellow messages, `console.error` and `console.warn`) appear here" >}}

The concept of a debugging console is not unique to JavaScript. It’s a basic software interface common to many programming languages and applications. It provides a way for a program to output low-level textual information and, optionally, receive inputs for controlling the program.

{{< figure class="post__figure--medium" src="/post_images/osx-console.gif" alt="A screenshot of the OSX Console application" caption="The OSX Console application" >}}

The definition of console as a software feature comes from the early days of computing, when a user interacted with a computer mainframe (which was often very large and possibly located in another room or building) via an array of controls set in a desk.

{{< figure class="post__figure--medium" src="/post_images/ibm7090.jpg" alt="A man in a white shirt pressing a button on a 1960's IBM computer console" caption="A meteorologist at the console of the IBM 7090 electronic computer in the Joint Numerical Weather Prediction Unit in 1965. Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:IBM_7090_console_used_by_a_meteorologist,_1965.jpg)" >}}

Early computer consoles were controlled by switches and buttons, while output was relayed to the operator via lights, dials, and paper printouts. Over time, consoles evolved to incorporate a command-line interface on a screen, with which the user would enter instructions using a keyboard.

We can find analogs of the computer console by looking to the world of music. Sound mixing consoles have existed in one form or another since the advent of electrical audio recording and broadcast almost a century ago.

But the use of the word console to describe a panel of electrical controls can be traced even further back, beyond the discovery of electricity itself, to the pipe organ.

{{< figure class="post__figure--medium" src="/post_images/pipe-organ-ebrach-kirche.jpg" alt="Interior photograph of a church showing the pipe organ facade below a large stained glass window" caption="The pipe organ facade in the former abbey church in Ebrach, Germany. Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Ebrach_Kirche_rose_window_Orgel_P4252411efs.jpg)" >}}

The pipe organ is the largest musical instrument, and is played by an organist who sits at a complex array of controls called a console. Organ consoles consist of keyboards (typically three to five), pedals, and stops - binary valves used for controlling wind flow to the pipes.

{{< figure class="post__figure--small" src="/post_images/organ-console.jpg" alt="A pipe organ console with console brackets" caption="Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Usnaconsole.jpg)" >}}

Organ consoles give us another everyday term: the idiom ‘pulling out all the stops’, meaning to apply maximum effort to a task. When every stop on the console is open an organ will produce sound using every available pipe, and therefore at maximum volume.


{{< figure class="post__figure--small" src="/post_images/cesar-franck.jpg" alt="Painting of composer and organist César Franck pulling out an organ stop" caption="Composer César Franck pulling out a stop at the console of the organ at St. Clotilde Basilica, Paris, 1885. Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Cesar_Franck_At_Organ.jpg)" >}}

But where did this type of console get its name? One clue lies in the fact that many organ consoles share a design feature with the console table. Modern console tables are typically four-legged, free-standing structures designed to abut a wall. But if we go back a few centuries, we find that console tables were more commonly wall-mounted with brackets beneath the table surface to bear the load.

{{< figure class="post__figure--medium" src="/post_images/console-table.jpg" alt="Marble and gilt oak console table with decoratively carved supporting brackets" caption="French Regency console table from the Metropolitan Museum of Art collection in New York. Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Console_table_MET_DP268329.jpg)" >}}

These supporting brackets are where the console table, (and perhaps the organ console) gets its name. In architecture, a console refers to an ornamental bracket that supports a protruding structure, such as a ledge, cornice, or balcony.

{{< figure class="post__figure--small" src="/post_images/console-architecture.jpg" alt="A neoclassical stone console supporting a balcony" caption="Neoclassical stone console supporting a balcony at the Maison médicale de l'Œuvre du calvaire in Brussels. Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Fa%C3%A7adebalconconsolechausseewavreneoclassique.jpg)" >}}

At this point, our etymological path forks. An architectural console may get its name from the verb ‘to console’: literally *con solaris* or ‘with soothing’; a relieving of pain or, perhaps, of weight. You could consider the job of a console to ‘relieve’ the weight of the structure above it.

An alternative explanation takes us back to the church, where in medieval times choir stalls were decorated with carved male figures called *consolateurs* or ‘consolers’. This in itself may have been a pun on the fact that consolers were often carved into armrests, thus supporting the weight of a seated chorist’s arms.

{{< figure class="post__figure--small" src="/post_images/choir-stall.jpg" alt="Illustration of wooden choir stalls showing carved consoles in the arm rests" caption="Illustration showing the carved wooden *consolateurs* in the armrests of the choir stalls at Andlau Abbey in Alsace, France. Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Stalles.eglise.Anellau.png)" >}}

So, far from being coincidental homonyms, it turns out that the many definitions of ‘console’ share a common etymological root, even when it’s used as a verb. Does the same go for ‘log’?

## Log

In computing, the term ‘log’ derives from a ship’s log, which is short for ‘logbook’. A logbook is used for recording information about any event taking place aboard a vessel, from navigation to maintenance to changes in crew. While there are typically no restrictions about what can be recorded in a logbook, the name comes from a very specific use: recording the ship’s speed.

Long before the invention of modern instruments, such as GPS, recording speed was an essential part of navigating the seas. Sailors would measure their speed and record it in the logbook every half hour, and by knowing how fast they were going, combined with the direction in which they were traveling (measured using a compass), they could work out where they were on the map.

{{< figure class="post__figure--medium" src="/post_images/ships-logbook.jpg" alt="Ships logbook showing handwritten entries" caption="Logbook from the USS Savannah with entries from September 3-15, 1943. Image credit: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:19430903-19430915_USS_Savannah_CL-42_Turret_Two_log_book_entries.jpg)" >}}

The logbook got its name from the chip log, a device that sailors used to measure the ship’s speed. This consisted of a quarter-circle piece of wood (the ‘chip’) with a rope tied to it, in which knots were tied at regular intervals.

{{< figure class="post__figure--medium" src="/post_images/chip-log.jpg" alt="Chip log" caption="19th century chip log. Image credit: [Wikimedia Commons](https://en.wikipedia.org/wiki/File:Loch_%C3%A0_plateau.jpg)" >}}

A sailor would throw the chip overboard and count how many knots spooled out while another sailor timed him using a sand timer. When the timer was up, the number of knots that had passed over the stern could be used to calculate the ship’s speed, which was then recorded in the logbook. This is where we get the term ‘knot’ as shorthand for 1 nautical mile per hour.

{{< figure class="post__figure--medium" src="/post_images/chip-log-engraving.jpg" alt="An engraving of three mates measuring a ship’s speed using a chip log" >}}

Before the invention of the chip log, an even more rudimentary technique for gauging speed was the Dutchman’s log. One sailor would throw any floating object (probably an actual log) over the bow of the ship while another sailor on the stern timed how long it took for the object to pass him. With this measurement (and knowing the length of the ship), the sailors could make a rough estimate of how fast they were travelling.

The days of using a log to measure a ship’s speed lie centuries behind us, but ‘log’ is a ubiquitous term in modern life thanks to its importance in computing (just think how many times you ‘log in’ to various pieces of software every day). And it’s just one of many modern definitions whose origins lie in our civilization’s long maritime history. We don’t need to look far to find more: the word ‘cyber’ derives from the ancient Greek word *kubernētēs*, meaning steersman or rudder, and the word ‘gadget’ was a slang term used by sailors for any part of a ship that they couldn’t remember the correct name of.

So next time you write `console.log` in your editor, spare a thought for the computer pioneers, pipe organists, medieval carvers, and old-word mariners who played a small part in giving us the very modern definitions of these two words.

---

*If you enjoyed this, you may want to read [ Your creations will not outlast you](/your-creations-will-not-outlast-you/).*
