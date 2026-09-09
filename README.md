# Tomplay -> Back-End Developer take-home exercise

**Design a "Recommended for you" system.**

Please read the "How we assess this" section before you start. It will save you time.

---

## The task

We want a **"Recommended for you"** section on two surfaces: the Discover screen of the Tomplay app, and the account page of tomplay.com. Design it.

To save you guessing: it recommends **scores**, it shows **10 to 20 of them**, and it is fine if the list only changes once a day. Everything else is your call, and we will ask why.

## Our constraints

These are real, not simplifications.

- **One MySQL database that four applications read and write.** Nobody owns the schema.
- **A Laravel website and a framework-less PHP API.** Both need this feature.
- **Solr already indexes the catalogue.** Redis and memcached are available.
- **~2 million users across 157 countries.** Each user has one or more instruments, a difficulty level and a play history.
- **It renders on the Discover screen when the app opens**, so it has to be fast.
- **Plenty of users have no play history at all.**

We left out catalogue size, traffic and latency targets on purpose. Ask if you want them.

## What to cover

Seven points. Please address all of them, even if briefly.

1. **Data model** -> tables, columns, indexes.
2. **Where the work happens** -> request time, batch, hybrid. And why.
3. **Cold start** -> what a brand-new user sees.
4. **Caching and invalidation** -> what you cache, for how long, and what busts it.
5. **The interface** the rest of the system calls.
6. **What you would measure** to know it is working.
7. **What you ship in week one** if that is all you get.

## What to hand in

**A couple of pages of prose, plus scaffolding.**

Scaffolding means interfaces, class names and a sketch of the tables. Leave the method bodies empty, **except one**: pick the method you think is hardest to get right (the request-time read path is a common choice) and write it out in plain PHP. It does not need to run. We will read it together on the call.

Any format that is easy to read -> Markdown, PDF, a Google Doc link. Whatever you already work in.

## Two hours

**Please stop at two hours.** Reading this and asking us questions don't count. We mean it literally, and we would rather have an unfinished two-hour document than a polished six-hour one.

**We are not asking for a running system and we will not reward one.** If you find yourself trying to make something run, you have gone past what we are asking for.

## AI

**Use whatever AI tooling you normally use.** We use it daily ourselves and we would rather see how you actually work than watch you pretend otherwise.

Please end the document with a few lines on how you used it -> what you asked it, what you kept, what you threw away, and anywhere you disagreed with it. We will talk about this on the call.

---

## How we assess this

Worth being explicit, because it changes how much effort is worth spending.

**The document is not the assessment.** The document is what we talk about on the call. We will push on your choices, argue the opposite of some of them, and ask what would change your mind. That conversation is the assessment.

So a design you can **defend and explain** beats a design that looks impressive. A couple of clear pages about choices you actually made will serve you far better than a comprehensive document you would struggle to justify under questioning.

**We will not tell you how our current recommendations work, on purpose.** We want your thinking unanchored by ours. You will find out at the end of the call, and one of the questions we will ask is what you would keep and what you would throw away.

**A few things that genuinely help:**

- Ask us questions before you start if something is ambiguous. Wanting to know how big the catalogue is or how much traffic there is before designing is a good instinct, not a delay.
- Say where your design is weakest. Volunteering it reads far better than us finding it.
- Boring and shippable, with the clever version parked as phase two, is a legitimate answer and often the right one.
- "I don't know, here is how I would find out" is a perfectly good sentence.

## Timing and next step

- **Deadline:** five days from when you receive this.
- **Then:** a 60-minute call with Daniel and one of our backend developers. We discuss your design, read your one method together, and you ask us whatever you want. Nothing to prepare beyond the document.
