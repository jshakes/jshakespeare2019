---
date: 2015-10-04 22:46:00+05:00
layout: post
permalink: why-good-agencies-write-bad-code
title: Why good agencies write bad code
featured_image: /post_images/why-good-agencies-write-bad-code.jpg
featured_image_caption: Illustration by Eleanor Shakespeare
---

Any seasoned programmer will have some experience of technical debt, the metaphor used to analogize how corner-cutting and skimping on process early in a project’s lifecycle results in a debt that must be paid off later. It is not necessarily a bad thing, but anyone who has inherited legacy code will know the frustrations of working with an indebted project. Sometimes a development team is able to effectively leverage technical debt to their advantage, sacrificing stability and process early on to achieve fast turn-arounds. Think of this a bit like a shopkeeper who must take out a business loan to buy inventory. They know that if they are able to sell that inventory at a profit they will have the capital to pay off that debt later on, along with the interest it accrues along the way.

I’ve spent most of my career working at small web development agencies. In that time I’ve noticed that code is frequently handed off with a level of technical debt ranging from potentially troublesome to irresponsibly dangerous. Some of those projects have been relatively pain-free to work on, while others have resulted in such horrible messes of code that developers have literally quit their job over them.

I wanted to understand what it, if anything, makes agencies more susceptible to technical debt than other organizations. To do that, it’s necessary to look at how agencies make money.

## How agencies operate

For those unfamiliar with how an agency does business, the lifecycle of almost every project I have worked on at an agency has looked like this:

1. A client approaches the agency with a set of requirements for the product (ie. an app or website) he wants built
2. The designers at the agency design something that meets those requirements
3. After n rounds of client feedback and design changes, the client gives the go ahead for the product to be built
4. The developers at the agency build the product based on the designs
5. After n rounds of client feedback and code changes, the client is satisfied
6. The product is launched and the client pays his bill

There are of course differences from one agency and one project to another, but this is a fairly ubiquitous approach. It’s not inherently tied to a certain timescale so it can be scaled up or down dependent on the project budget or external deadlines. Steps 2-5 can be repeated multiple times throughout the project if the agency in question prefers to work according to an Agile methodology (or some derivative thereof).

Assuming a healthy flow of business it is in a growing agency’s best interest to complete this lifecycle many times and at a reasonably fast pace. Sometimes clients may wish to retain the agency’s services after launch for support and incremental improvements, but if new work is available those resources are better spent working on the next (bigger and better) project rather than maintaining old ones.

This is because rapid project turnaround suits both client and the agency alike. The client wants to receive a quality product as cheaply and as quickly as possible, so an agency that can deliver that product in a short timeframe is attractive. For the agency, fast turnaround means they can win progressively more lucrative contracts more quickly - or simply put, grow faster. Each time a project lifecycle is completed the agency earns exposure and reputation, which may also make their services worth more money. Retainer contracts and long projects may guarantee revenue, but they also represent a plateau in growth.

## Why agencies accrue technical debt

By this logic it is actually more pragmatic for a growth-focused agency to deliver projects with high levels of technical debt. While project constraints may be demanding, there is no long term period in which it will be the agency’s responsibility to repay that debt. The agency knows they can turn out debt-laden code because there’s too short of a development time for it to be a problem for them. This is not to say the end product will be bad, just that the codebase is not optimized for a long life span.

This has an additional benefit for the agency because it means they don't have to hire world-class developers to meet the client’s needs, and that means they can spend less money on salaries. Let's assume that most projects at an average small to medium-sized agency spend less than six months in development. The talent pool of developers who are able to build and deliver a fairly standard website in six months is relatively large and therefore competitively priced. Even if below the surface the website is literally made from spaghetti, it is unlikely it can be complicated enough to cause any of nuclear meltdown if it goes wrong (spaghetti having a relatively long half-life). As long as the website is acceptable to both the client and their users at the time of project handoff, the quality of code is of little concern to the agency from a business perspective.

Consider on the other hand a website that is in development for two years. If the team responsible for building it does not have a good understanding of design patterns, writing tests and documentation, code reviews, refactoring and other best practices, then the end product will most likely be severely marred, if it even gets shipped without one or more developers winding up in an asylum/prison. Hiring a team of people with that level of experience is much more costly, and yet for an agency that bills by a day rate, brings in the same amount of revenue as four six-month projects that can be completed by less experienced and therefore cheaper developers.

This is in not an indictment of agencies, but rather a characteristic of the fact that it generally makes better business sense to focus on growth rather than writing immaculate code for every project. I am also not implying that agencies only need to hire junior developers, simply that it is easier from a technical standpoint to successfully deliver a six month project than a two year one. 

After all, agencies offer a service that is typically expensive but finite, and that makes them well-suited to short project lifecycles. Perhaps the project in question is just a proof of concept so the client can seek further investment. Perhaps the project is time-sensitive, like a marketing campaign tie-in, and will be shelved without anyone touching the code again once it is handed off. 

Whatever the reason, agencies are not _aiming_ to write debt-laden code, nor are they trying to con non-technical clients who don’t know any better. It’s just that the client would usually rather pay less and get the product faster by accepting something that is not optimized for further development.

In other words, the end product is cheaper (or delivered sooner) _because_ it comes with some degree of debt built into it. 

## How agencies accrue technical debt

So far I’ve argued that growing agencies are generally better off taking on short term projects, and that it is acceptable for those projects to be delivered with some degree of technical debt. But what happens when that agency reaches a point at which short projects no longer make financial sense? So far I have used the six month heuristic to delineate projects between simple and complex, so what if an agency lands a year-or-more long contract?

In these cases, technical debt can not be allowed to accumulate at the same rate as shorter term projects. This is for the same reason that compound interest makes people in financial debt get exponentially poorer. The quality and speed of development will curve increasingly downwards until either the codebase is unsustainable or the product is unusable.

There are of course many agencies that undertake projects of vast complexity with contracts spanning multiple years, so what are they doing to minimize technical debt?

In my experience there are two reasons that agencies accrue debt faster than other organizations.

### 1) Biting off more than developers can chew

This is caused by an agency either trying to grow too fast; lack of communication between the team responsible for winning new business and the development team; or both.

If a company is pitching for atypically complex projects, technical debt is going to be a sure thing. In fact, in this scenario technical debt is really a euphemistic way of saying the project will be somewhere on the scale of ‘unacceptably difficult to ‘the client will end up firing/suing you and all your developers will commit seppuku’. It’s analogous to the hungry diner at a buffet having eyes bigger than his stomach and overloading his plate. At first it may be tempting to load up 3 platefuls of tempura, but at some point in the future you're going to be handed a bill to get vomit cleaned out of the back seat of your friend’s Toyota Prius and it will be expensive.

The reason these longer term projects have the potential to cause problems is because the development team will have become accustomed to, and ideally good at, moving fast to meet short turnarounds. If the same approach is taken on a longer term project, the level of technical debt will move past the acceptable limit and some serious issues will arise. Of course the solution to this is seemingly simple - pay off the debt as necessary throughout the duration of the development period. But if an agency has a development team with no experience of dealing with technical debt, this is much easier said than done.

This is an especially common problem at agencies specifically because of the focus on growth that I mentioned earlier. Winning an atypically lucrative pitch can seem like a ticket to the big time. Any gap between the dev team’s current abilities and those required to complete the project are dismissed with vague notions of learning on the job and hiring contractors to fill the gaps, whereas the bottom line is that the agency is promising to fulfill work it is not yet qualified to deliver. This by no means equals guaranteed failure, and at some level every agency will have to make these leaps from time to time under the rallying cry of 'fake it ’til you make it’. But if an agency typically works on short-term projects and out of the blue puts its developers to task on a year long contract, some degree of behavioral shift will be required.

If you consider a leap in project complexity (and thus financial value) to be a form of instant capital that comes at the price of technical debt, then you start to see how important it is to grow at a reasonable rate. The agency can then weigh the lucrative nature of a big contract against potential problems further down the line, and pitch only for projects that will result in an acceptable level of spaghetti code and developer Seppuku throughout the project lifespan. Over time, that duration will increase.

Biting off more than you can chew is a problem with management at the company level. Another root of technical debt at agencies lies in management at the project level.

### 2) Making too many assumptions about client understanding

Everyone knows that assumptions make an ass out of ‘u’ and ‘mptions’. But before I talk about why assumptions can lead to technical debt, I want to clarify what they are.

During a software project (at an agency, startup or enterprise), two types of assumption will be made: reasonable assumptions and lazy assumptions. It’s important to recognize when each type is being made and to reduce the likelihood of false assumptions causing problems later on.

Reasonable assumptions are ones that are either not sufficiently risky or cost too much to test now and so are taken as gospel until it becomes sufficiently inexpensive to prove (or disprove) them later. In software development, knowing that a reasonable assumption exists means code can be written in such a way that will make it easy to change later should the assumption prove to be false.

Lazy assumptions are cheap to test now but are not addressed because of poor management. They can be resolved through something as simple as good, clear communication, but the longer they remain unproven, the more expensive they become. Should they prove to be false at a later date, they can be highly problematic and expensive to fix.

Imagine a designer working on the design for an e-commerce checkout. They get to designing the buttons for progressing through the checkout. In a world free of assumptions, they would already have the user data that says ’the highest checkout completion rates are observed when buttons are pink and have a 4px border radius’, and their job would be a lot simpler. But data at that level of detail is almost never available prior to launch, so the designer makes an assumption about what will engage users and makes the button bright red instead. Later on that button styling may change as more data becomes available about user behavior, but for now it would be too costly and time-consuming to gather that data.

This is an example of a _reasonable_ assumption, and designers use them all the time at agencies and elsewhere. Reasonable assumptions are often made under the Lean Startup methodology, which prioritizes launching an imperfect product faster than a perfect one. Reasonable assumptions can be proved or disproved after the product launches and metrics and data become available that make it cheaper to do so.

Conversely, consider this exchange between an agency project manager and their client:


Client: _“We're noticing the homepage has laggy scrolling on older mobile phones, we need you to fix this right away"_

Product Manager: _“But you asked us to use a canvas animation for the background of that page, older phones don’t have the graphics power to cope with that and scroll smoothly"_

Client: _“Well we didn’t realize that would cause slow scrolling, you’ll have to change it"_


This is an example of an agency making a _lazy_ assumption, in this case one made about the client’s technical knowledge. Had it been established earlier on that the request for an animated background would cause poor performance on older devices, the client could have voiced their concern earlier and the development team could have built a better solution. Instead, they must now go back and retroactively solve this problem.

This kind of assumption is one that agencies are highly prone to making. They often occur because what the client sees at the design stage is an unrealistic portrayal of the end product, or because the project is rushed into the development phase without establishing a specification that everyone can understand and agree to. As I established earlier, this doesn’t necessarily cause problems in projects of shorter lifespans when a client may be happy to skip some of the formalities to get to a working product faster. But for longer, more complex projects, when lazy assumptions are left to fester they can cause big problems later on.

False assumptions are problematic because they have a nasty habit of coming to light later in the project’s lifecycle, when the number of hours remaining on the project does not always allow for changes to be implemented in an optimal way. In some cases, a project may be so heavily based on assumptions that the codebase cannot accommodate a fundamental change should those assumptions prove to be false.

The more false assumptions that must be accounted for late in a project’s development, the higher the likelihood of technical debt accruing.

{{< figure src="/post_images/technical-debt-flow-chart.jpg" caption="The more revisions are made, the greater the likelihood that corners will be cut, as project time and budget are reduced with each iteration." >}}

Avoiding assumptions during a project at an agency means emulating as accurately as possible the end product before construction begins. By capturing the less tangible aspects of a product, such as UX and performance, the client’s vision for the product will align more closely with the agency’s and there will be fewer surprises when the client starts using the product for the first time. Good communication and prototyping are the two things I consider to be most crucial to closing the assumption gap between agency and client.

While reasonable assumption-making can be a valid alternative to early stage research, it is essential that agencies be aware of lazy assumptions they are making too. In particular, assumptions should never be carried into the development phase if they can be proven or disproven simply by better communication with the client. Weighing up the cost of assumptions against their potential to accrue technical debt and other problems later on is an important part of effectively managing any software project, but this is especially important at an agency where the understanding of the developers, users and clients must align as closely as possible.

## Common? Yes. Unavoidable? No.

Ultimately, a development project at an agency isn’t so very different from a development project anywhere else, and for the most part technical debt can be treated the same. While technical debt may be more likely to accrue in an agency environment (especially fast-growing ones) due to the nature of how they make money, it is not unavoidable. Being aware of technical debt and understanding how to reduce and strategically increase it can give agencies a powerful tool in tackling projects. Instead of letting debt spiral out of control and ruin a codebase - and possibly reputation, it can be leveraged in such a way that suits the timescale and complexity of a project for all parties involved.

But avoiding technical debt means being aware of its causes, and it’s worth noting that both the causes I have outlined above are present before a single line of code has been written. The key to avoiding technical debt is understanding the nature and limitations of the agency model. Understanding that because you can win a big pitch doesn’t mean you’re able to complete the work well. Understanding that a little time spent prototyping can save a lot of time in code clean up. Understanding that client relationships require as much communication as possible to stay on the same page.

Understand these factors, and you can understand where technical debt comes from. Understand where it comes from, and you can be free of it.
