---
date: 2014-04-02 12:00:00+05:00
layout: post
permalink: code-isnt-poetry
title: Code isn't poetry
description: Hemingway's prose was masterful in its simplicity and terseness. Can we write code the same way?
featured_image: /post_images/hemingway.jpg
featured_image_caption: Illustration by Eleanor Shakespeare
---

Ernest Hemingway’s masterfully uncluttered prose made for some of the best novels to come out of America in the 20th century. He sought to achieve truthfulness of language, primarily by eschewing ornament and flamboyance in his writing. Of his 1964 novel *A Moveable Feast* he said

> "If I started to write elaborately, or like someone introducing or presenting something, I found that I could cut that scrollwork or ornament out and throw it away and start with the first true simple declarative sentence I had written.”

People tend to mistake Hemingway’s style as pure terseness, but this is not always the case. He did not write with a minimalist agenda, he simply championed readability. Whilst he often wrote in a staccato fashion he also penned sentences spanning an entire paragraphs, repeating the same words several times to enforce their meaning.

The reason Hemingway wrote this way was because he understood that the medium is not the message. If syntax or vocabulary got in the way of the story it would detract from the essence of the story itself. Through writing as he did, Hemingway emulated a conversational style of writing that reads with little effort.

As developers we can apply this aesthetic to the way we write code. When we know that our code will be read by a human at some point (even it is by our future selves), we should try to write it in a way that is as uncluttered, simple and non-egotistical as possible.

Twitter developer Angus Croll explored how Hemingway would have written Javascript in <a href="http://byfat.xxx/if-hemingway-wrote-javascript" target="_blank">a post</a> from a couple of years ago. He described his Hemingway example as

> "Code reduced to its essentials with no word or variable wasted. It’s not fancy; maybe its even a little pedantic - but that’s the beauty of Hemingway’s writing.”

An ongoing point of contention amongst programmers is whether code should be terse or verbose. Terse code is that which is reduced to its minimum required syntax to achieve its means, while advocates of verbose code favour redundancy and legibility to aid understanding.

But to argue for either a terse or verbose style is reductive. What we should aim for is the shortest possible elapsed time to both write and read code. Sometimes that means writing and structuring code in a way that forgoes clever tricks and time-saving devices because in the long run it will make it easier to maintain. It can also mean writing code that appears terse to make it more legible.

Let’s consider a basic example. Ternary operators are often used by programmers to shorten three-way operations. If we wanted to represent the phrase 'red sky at night, shepherd's delight' in Ruby we could do so using a ternary operator like this

```ruby
forecast = sky_color == "red" ? "sunny" : "rainy"
```

Or we could write it in longhand form

```ruby
forecast = if sky_color == "red"
  "sunny"
else
  "rainy"
end
```

While the first example is more terse the second is certainly more readable. It may even be that the first takes longer for the developer to write, dependent on their familiarity with ternary operators.

There's a tendency in web and software development to be constantly pushing ourselves - often on the job - to write code in increasingly abstract and inventive ways. This typically stems from the natural and healthy desire to do a job as well as possible and use the full set of tools available, but it comes with increased comprehension time both to write and to read. It’s the programmer’s equivalent of digging out a thesaurus and picking out unfamiliar and superfluous vocabulary.

In the words of Brian Kerningham

> "Debugging is twice as hard as writing the code in the first place. Therefore, if you write the code as cleverly as possible, you are, by definition, not smart enough to debug it.”

In other words, if you can do a job effectively with the tools available and familiar to you and your fellow developers, it's quicker to use them than to drive out to the hardware store and pick up a bunch of fancy new tools you don't know how to use.

To apply Hemingway's style of writing to programming is to understand that 'clever' programming does not inherently improve the quality or readability of code, just as abstract or overly-elaborate prose does not inherently improve the readability of a novel. Rather, by writing in as pragmatic a way as possible, a developer will produce code that is both easy to write and to read. Economy of language is championed whilst simultaneously reducing the barrier of entry to readers.

As with literature, code can be a window into another realm. But whereas simply-written code is like a clear and clean pane of glass, overly clever code can be like an ornate stained glass window. It may look decorative and have taken great skill to make, but it’s almost impossible to see through it.

The Hemingway philosophy is this: do not write with ego or pretense, but rather with pragmatism. If something can’t be written by simple means, the concept must be broken down into simpler constituent parts. Do not clutter your writing with self-indulgent embellishments. Do not confuse simplicity with brevity. Write in a direct, clear manner regardless of how many bytes it takes to do so.

Stick to this philosophy, and make Papa proud.
