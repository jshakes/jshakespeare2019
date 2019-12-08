---
date: 2019-08-03 10:47:00+05:00
layout: post
permalink: design-smells
title: Design smells
---

In digital product development, the process of turning visual mockups into code is sometimes called ‘translating’ a design. This choice of words highlights the fact that the design-to-code stage is not a rote formula that takes in pixels and spits out code, but an interpretation of meaning from one language to another. A translator must be proficient in both languages if she is to effectively convey meaning from one to the other. Therefore, it is the job of an interface developer to be fluent in the languages of both design and code.

If you’ve ever learned a foreign language then you will know that words cannot simply be exchanged like-for-like in order to translate a phrase. (You will also know this if you’ve ever heard a joke that begins with [“in Soviet Russia”](https://en.wikipedia.org/wiki/Russian_reversal)). Translation requires knowing not just vocabulary but word order, idioms, pronouns, conjugations, etiquette, punctuation and more.

The middle ground between any two languages is meaning, and that meaning exists in the mind of the translator. Translation requires unearthing meaning so it can be reconstructed in another language.

{{< figure src="/post_images/translation-fail.jpg" caption="Translating words but not their meaning: the bread and butter of clickbait sites since 2007" alt="A Filipino sign that reads 'Manok ng ina mo', with an English translation below it which reads 'Chicken of your mother'" >}}

To find the meaning within an interface design, a developer must look beneath the surface of the mockups and identify the rules and patterns that govern how the interface should behave in different contexts. Does the layout follow a grid system? Which values are fixed and which are fluid? What is the typographic hierarchy? The better she is at identifying these rules, the better the code will describe the design system.

Describing a design system in code is important because mockups do not paint a complete picture of how an interface will behave. Mockups are frozen in time, but a user interface must be capable of responding to an infinite combination of browsers, devices, screen resolutions, zoom-levels, and content. Code that effectively describes a design system can fill in these gaps and makes the interface more robust.

Building an interface is a translation from a simple language to a much more complex one. But no matter how skilled a developer is at building an interface, the first step must be always be to understand it. The only way to do that is to become bilingual.

---

Programmers sometimes talk about “code smells”: surface-level indications that something about a program isn’t right. Sometimes a code smell is just a hunch; not something that can be identified straight away, but a loose thread that reveals a structural flaw when pulled. Much like the nasal assault that any parent of a small child is familiar with, a good programmer knows a foul smell indicates something dirty has happened and must be cleaned up sooner rather than later.

In the same vein, an interface developer should have a nose for smells in the design she is working with. Just as a good linguistic translator would not translate mistakes between languages, a good interface developer should not recreate design flaws in her code.

Design smells often manifest themselves through the need to write one-off rules that only apply to a fixed set of circumstances, instead of code that is more universal and flexible. If a mockup specifies page margins of 80 pixels instead of the usual 60, does that mean that the default page margins should be updated everywhere? Is there something special about this type of page that means others like it should also have an 80 pixel margin? Or is it simply a mistake that should not be translated into code at all?

Design smells are often the result of mistakes made by designers, or at least indications that a design is unclear and needs further thought. But having a nose for these smells is not about picking holes in other people’s work, it’s about fixing small problems early so they don’t become bigger problems later on. Contrary to the ancient wisdom of the playground, it doesn’t matter who dealt it, as long as someone smelled it.
