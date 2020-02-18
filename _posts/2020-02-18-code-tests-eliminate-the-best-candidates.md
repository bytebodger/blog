---
layout: post
title:  "Your Coding Tests Are Probably Eliminating Some of Your Best Candidates"
date:   2020-02-18 00:00:00 -0500
categories: code tests interviewing assessments whiteboarding hiring
---
There's something beautiful (and potentially ugly) about the career fields associated with application development.  As a greybeard in the field, I've had the chance to see the beauty and the ugliness firsthand.  This dichotomy is centered upon the inherent quantifiablity of what we do.

## The Dream of Quantifiability 

On one hand, application development is somewhat unique amongst many other professional careers in that it's inherently *quantifiable*.  What I mean by this, is that you don't have to just take someone's word to assess their coding prowess.  When done properly, you can actually *see* whether candidates truly have the skills that they claim on their (infinitely malleable) resumes.  

If someone looks (on their resume) to be an amazing project manager, it can be extremely challenging to suss out whether they truly have the skills to properly manage *your* projects in *your* environment as they would interact with *your* team.  Their resume is undoubtedly filled with all the bits of alphabet-soup that you typically look for in a good project manager.  But anyone with a smidgen of savvy can simply *type* those acronyms on their resume.  And then it's up to you, presumably during the interview process, to figure out if they're really an ace project manager possessing the skills and the experience that they claim.  

But application development feels... *different*, right??  I mean, if someone claims to be a top-notch developer in a given language (or languages), and they swear that they've already written ***all the codes*** that you want, in other environments for other employers, then you should be able to *see* the work they can produce, *right*???  I mean, at the end of the day, you should just be able to tell them, "OK, then *show* me..."  In theory, we can just *watch* someone code - preferably, in real-time - to determine if they're really the coder that they claim to be.

This ability to physically demonstrate one's coding prowess is, in theory, only bolstered by modern tools.  We can assign coding tests administered by third-party sites like HackerRank or Codility (or many others).  Or we can do screenshares and ask them to demonstrate their coding skills right as we watch.  Or, in the most "old school" of approaches, we can drag them into a physical office where we can ask them to whiteboard solutions - presumably with other trusted developers in the room to assess and critique their work.  Regardless of the precise approach taken, we should have all the tools we need at our disposal to quantifiably assess someone's coding talents before we ever even consider an extending an offer...

*Right???*

Well... sorta.  

## The Perils of Whiteboard Interviews

A lot of companies that I've interviewed with in my career depend heavily upon the whiteboard interview.  They haul you into their office, set you up in front of a whiteboard, and ask you to code some kind of nominal solution.  All while their internal devs observe and critique the process/outcome.

This approach isn't entirely *bad* or *wrong*.  In fact, it can lead to spectacularly-successful hires.  But it's also strewn with potential landmines if the employer is not extremely careful.  Some (but not all) of these landmines include:

 - **Many great coders are poor interviewers.**  
If they were great interviewers, they probably wouldn't be in application development.  They'd be in HR.  Or they'd be recruiters.  But they're not in HR and they're not recruiters - because their primary skill set is coding - not talent assessment.  Many devs that I've seen pulled into these interviews can be downright surly, and this can turn a promising candidate into a nervous wreck.  (There's a *reason* why they spend their whole lives staring at computer monitors and interacting minimally with other living souls.)  Other coders I've met can actually be *too* forgiving when they're conducting whiteboard interviews.  They offer an endless series of ridiculously-leading questions that a savvy candidate can successfully "answer" without properly knowing the core issue being tested.  I've even seen where an interviewer will walk up to the whiteboard and basically code the solution *for the candidate* - and then will say after the interview, with a straight face, that the candidate "passed".

- **Whiteboard interviews can foster pedantry.**  
"Real" coders tend to live in their IDEs.  They've become accustomed to the shortcuts and code completions that are built into their chosen environment.  So when you put them in front of a whiteboard and ask them to just scrawl out some code, even the best devs can sometimes write some very, umm... *incomplete* code.  Does this make them a *bad* coder or a *poor* candidate??  Almost certainly not.  And this analog restriction is fine... as long as the interviewers are understanding (and even, *compassionate*) in what they're asking the candidate to do.  But I've seen too many scenarios where a highly-qualified candidate is passed over because some aspect of their whiteboard scrawlings wouldn't *compile* if it were dropped into an IDE.  In most scenarios, such a strict compliance with **perfect syntax** is just downright *unfair* to the candidate.  If the offered solutions is logically sound, but it's missing a few semicolons here or there, this should be no reason to eliminate a candidate.  But often, it *does* serve as a basis for elimination.  The key question you should ask yourself, when a candidate is whiteboarding a solution, is, "If this person were sitting at a full-fledged development environment, is it reasonable to assume that the minor flaws in their syntax would be quickly highlighted by the IDE - and fixed by the candidate?"  If the answer is, "Yes," then it's a waste of everyone's time to eliminate the candidate solely on this basis.

- **Whiteboard interviews are too-often a test of whether the candidate knows/prefers to code *in the company's chosen style*.**  
Whiteboard interviewers (often, developers who already work in the company) are frequently focused on *the specific way* that they've already chosen to write code for the company.  And they're often skeptical of anyone who hasn't already chosen to code in that particular style.  For example, a JavaScript team may ask a candidate to code a solution and, when the candidate starts writing their answer on the whiteboard, it may become apparent that the candidate chooses to write their functions in the "old school" JavaScript format - as opposed to using arrow functions.  In many frontend-developer whiteboard interviews, this can be a kiss-of-death for the candidate.  The existing devs, accustomed to seeing nothing-but-arrow functions, start huffing under their breath that this candidate sucks.  And everything in the interview from that point forward is nearly pointless.  Because the company's legacy devs have already decided that this candidate just can't cut it.  To be absolutely clear, if a candidate starts writing nothing but "old-school" function declarations, it's perfectly valid to ask them: *Have they used arrow functions before?  Do they understand them?  Could they use them if asked to?  Is there a particular reason why they chose to use "old-school" function declarations in this particular solution?*  But too many times, these questions are never asked.  The existing dev team just looks at those "ugly" function declarations, chortles under their breath, and tells the hiring manager that this candidate should be eliminated.

- **Whiteboard tasks are often assigned with confusing/ambiguous verbal instructions.**  
No modern dev team that I know of wants to receive their specs solely as a set of verbal instructions.  But they can be perfectly happy foisting such verbal instructions on a nervous candidate fidgeting at the whiteboard.  They might ask something like, "Write an immutable function that accepts an array A consisting of integers X...n that will return an array of X...n in which all integers occur equal-to-or-less-than Y (assumed to be 1) times."  Of course, the simpler way to state this is, "Write a function that de-dupes an array of integers."  But too many times, the snarky in-house devs prefer to use the first description.  Then they sit back and chortle as the nervous candidate tries to properly *grok* exactly what was just asked of them.

## Effective Whiteboard Interviews

Does this mean that whiteboard interviews should be abandoned??  Of course not.  They're a powerful tool.  But here are some tips to assure you are not eliminating otherwise-valuable candidates:

 1. **Spend at least a modicum of time *training* your existing devs on how to ask effective interview questions.**  
They may not *like* it.  But an untrained interviewer is often a liability.  Teach them to avoid leading questions.  Train them on how to assess the candidate's *mental process*, rather than focusing on semantic details.  Teach them how to make candidates (reasonably) comfortable - because nervousness is rarely a valid reason to eliminate a candidate.

 2. **Have the coding exercises written down before the candidate(s) arrive.**  
You probably don't take kindly to oral-only instructions.  So don't expect your candidate to perform flawlessly with only oral instructions.

 3. **Make every attempt to provide a workstation, with a pre-installed IDE upon which the candidates can demonstrate their solutions.**  
 No one codes in Notepad anymore.  And they don't code on whiteboards.  So don't use this handicap as an excuse to eliminate quality candidates.
 
 4. **Encourage candidates to *talk* through their solutions.**  
Are you fixated on the idea that they can write perfectly-compilable code on a whiteboard that perfectly achieves the goal in an artificially constricted time frame?  Or are you more concerned that the candidate has a solid (and *repeatable*) mental process that can be used to code *any* potential solution??

 5. **Encourage candidates to write *language-agnostic* solutions.**  
In other words, it's usually effective to say, "Write this Function X... *in any language that you're comfortable in*."  Some people balk at such a liberty.  Some people insist that, "We're hiring for someone who will write in Assembly language, that will connect to a React frontend, and will communicate with a MongoDB via GraphQL - so we need to see the solution coded with those exact tools."  But such restrictions are an arrogant folly.  You shouldn't be looking for devs who happened to have mastered *your exact tech stack*.  You should be looking for hot-shot developers.  Period.  *If some dev has spent 20 years mastering every aspect of C#, and C++, and Python, and Oracle, do you really think he's incapable of (quickly) picking up the TypeScript that you're using in your current environment??*

## The Perils of Coding Tests

The last decade-or-so has seen a proliferation of online tools that can - *supposedly* - be used to assess a candidate's dev skills.  And, *in some cases*, these can be extremely helpful.  But I've noticed that soooooo many of these online coding tests are **complete and absolute garbage**.  

The first fault of these online tools is that they usually depend upon some kind of artificial timer to limit each individual question.  On one level, this is understandable, because if I ask you to, say, de-dupe an array, your solution (and there are many different ways to achieve that goal in many different languages) shouldn't take you *days* to complete.  But I've seen so many sites where such a question is posed with a timer that is limited *to mere minutes*.  

Maybe you're thinking, 

> "Well, if you can't de-dupe an array in minutes, then you're not a good candidate for our team."

OK, fine.  You can take that view.  But consider this:  There are many complex, fairly esoteric functions that I can write for you *in minutes*.  Can I write those functions so quickly because I'm a *Coding Deity*??  Hardly.  I can write them so swiftly *because I've been exposed to them before*.  The mental work is already done and filed away in my brain.  So when you ask me to write that function, my effort would look, to the uninformed bystander, quite impressive.  But it's not "impressive" due to my incredible coding prowess.  It only *seems* impressive because I can regurgitate solutions that I've already worked out at some point in the past.

Conversely, I sometimes take an hour-or-so to solve what, to some people, seems like a rather "simple" problem.  It takes me more time simply *because I haven't been exposed to that exact solution before*.  And I know I'm not alone in this.

In other words, many of these timed coding tests aren't measuring your inherent brainpower.  They're only "measuring" whether you're already familiar with the problem.  And that's usually a poor basis upon which to advance/eliminate a candidate.  Furthermore, for many people, there's just something about watching that (artificially limited) timer count down that materially impairs their ability to provide a solid solution.  

Look... We all have to deal with deadlines in our jobs.  And I understand that, in *rare* circumstances (like, for example, a live bug in production), it might, *occasionally*, be imperative to know that someone can code swiftly.  But more often than not, we're not focused so much on *speed* as we are on *quality*.  If Developer A spits out a "marginal" solution in 15 minutes, but Developer B takes a few hours to craft a robust solution - with unit tests, that accounts for multiple edge cases, that's purposely written in a way that's easier to read and follow by the other devs - *do you really wanna eliminate Developer B and move Developer A to the next phase of the interview process??*

As if this weren't bad enough, I've encountered several scenarios where the coding test was simply, outright ***wrong***.  It's not incredibly common - but it happens.  

Years ago, I was interviewing for a remote contracting gig with a company that purports to only hire "top talent".  After passing the initial screenings, they put me on a live screenshare with one of their senior guys and they gave me two tasks, each limited to 15 minutes.  I passed the first one just fine.  For the second, I submitted my solution, and he told me that it was *wrong*.  To be honest, I was kinda flummoxed and didn't know what to say, because I was fairly certain that my solution was *not* wrong.  But by that point, it was too late.  They'd already deemed my solution to be "wrong" and the interview was over.  

But it bugged me enough that I remembered the exact task that was given to me and I made a point to google it afterward.  It's not that I couldn't accept the idea that my solution was "wrong" - but if it was, I wanted to know *why* it was wrong.  In other words, *I wanted to learn from it.*  So... after googling it from about 10 different angles, I finally realized that I was, in fact, *right*.  Not that it mattered at all with regard to my interview.  I was already, summarily, eliminated.  But you can imagine how frustrating the experience was for me.  

Nowadays, most of these automated coding tests aren't even viewed, in real-time, by an interviewer.  But I've found several other scenarios where the task that was marked as "wrong" by the automated system was, in fact, ***right***!

Of course, automated tests aren't necessarily limited to live-coding samples.  They can also include multiple choice questions.  And... oh boy.  *Lemme tell you.*  Many people do **not** know how to craft an effective multiple choice question.

Sometimes, the questions are outdated.  Sometimes, they're worded ambiguously, such that multiple answers could be "correct", depending on the context.  But my pet peeve is the IQ Test/Question that parades as a Skills Test/Question.  Consider the following putative question that has nothing to do with coding:

    As a lawyer, someone walks into your office and demands to know the contents of the 
    conversation that you just had in the previous hour with another client.  You should:
    
    A) Call 9-1-1
    B) Threaten to kill the client
    C) Politely inform him that conversations with other clients are legally-protected 
    and encourage him to either change the subject or find another laywer
    D) Tell him that such inquiries can only be handled via "street justice"
    E) Inform him that you can only divulge the conversation "for the right price"

I'm going to assume that, if you're reading this post, you're not a lawyer.  I'm also going to assume that, with no legal training whatsoever, you can discern that the correct answer is C.  

In other words, the question isn't even testing your knowledge of the law.  It was (poorly) crafted in such a way that it's only testing whether you have any got-dang common sense.

This may feel like an odd diversion, but I've seen sooooo many multiple choice questions (in tech, and otherwise) that are worded in such a way that they're not testing anyone's actual knowledge.  They're only testing someone's basic IQ.

As a *much* better example, consider the following question:

    By default, HTTPS requests, encrypted with SSL, are transmitted on which port?
    
    A) 22
    B) 80
    C) 82
    D) 443
    E) 448

If someone has no experience with HTTP requests and default ports, they have a poor chance of simply *guessing* the correct answer.  To someone with no knowledge of the subject, there is really no data in the question (or in the answers) which will allow them to easily surmise the correct response.  Sure... there's still a 1-in-5 chance that they will simply guess correctly, but the question (and the provided answers) do nothing to point the "layman" to the right answer.


## Effective Code Tests

So should we throw out all automated code tests?  Hardly.  They can be extremely useful.  But here are some key points to consider if you feel compelled to use these automated testing tools:

 1. **Don't choose a code-testing utility unless you can manually specify the time limits that are placed on each question.**  
And be liberal with it.  Don't make blanket assumptions that "everyone" should be able to solve this question in X minutes.  A quality coder will sometimes invest extra time to ensure a robust, quality solution - and they shouldn't be punished for that.  And don't underestimate the discombobulating effect that can be placed on your candidates by watching that cold, unfeeling timer count down.

 2. **Don't choose a code-testing utility unless you can manually choose *exactly* which questions are presented to the candidate.**  
It's patently unfair to allow a random algorithm to assign questions A, B, & C *to me* - while questions X, Y, & Z are presented *to another candidate*.  The potential randomization of questions ruins any ability you have to make an apples-to-apples comparison between candidates.  Also, some of the "stock" questions provided by these code-testing utilities are worded in confusing-and-obtuse ways.  Your "test" shouldn't be whether the candidate can decipher the question's obtuse language.  The question should be testing someone's basic mastery of coding techniques.

 3. **Be very careful with multiple choice questions.**  
If a complete novice can easily eliminate *any* of the potential answers, then the multiple choice question is poorly formed.

 4. **Don't throw the coding test blindly at all candidates.**  
Quite frankly, it can be a little insulting for senior devs.  I understand that it may be a "blind" tool that you throw at any of the anonymous applicants who filter in through your web site or from the job boards.  But if one of your existing devs has highly recommended a friend with a wealth of knowledge and experience, you can completely turn off the candidate by sending them a basic-skills test.  You can "stick to your guns" if you want, and you can demand that *every* candidate - even those personally recommended by your own trusted employees - first completes the coding test.  But you'll also find that some of those senior, hot-shot devs simply can't be bothered.  They already have a good job.  They have side projects that they're working on.  They have... *options*.  And they don't need to jump through all your hoops just to be considered for a job that they might, at the conclusion of the process, not even want after all.

 5. **Be respectful of your candidates' time.**  
If you think that each coding task should take 30 minutes, and there are 10 tasks to complete, you're expecting a *lot* of unpaid labor from people you don't even know.  In such a scenario, who will have the wherewithal to complete the entire test?  The junior devs.  The ones without... *options*.  The ones who may need a lot of hand-holding if they manage to survive the interview process.  They don't have a good job.  They'll do anything you ask.  But the hot-shot coders?  They'll see your coding test for the time-drain that it is - and they'll just take a pass.

 6. **Get your *existing* devs to take the test (if they didn't take it already as part of *their* interviewing process).**  
That's right.  They may already be hired - but it can be a fabulous benchmark to ask *your own* dev team to "eat its own dog food".  I'm not saying this because you should be looking to *remove* the members of your team that are (presumably) already thriving in your environment.  I'm saying this because it should give you a much more realistic perspective on exactly how *hard* - or maybe, how *easy* - your "standard" coding test is for prospective devs.  It could be a real eye-opener when you've been eliminating all those candidates who "only" scored 50% on your coding test - but your *existing devs* (the ones who are presumably doing good work for you already) are routinely scoring "only" 50% on the same test.

## The Perils of "Demo" Apps and Coding Exercises

If you're not easily equipped to navigate the pitfalls of whiteboarding interviews (which can be especially true for remote/distributed teams), and if you're also wary of the automated code-test solutions that are out there, what's left??  Well... for many companies, it's the coding *exercise*.  

Under this rubric, the company says, 

> "OK, we think you're a solid candidate.  So to make sure that you can do what you say you can do, we just want you to code up this teeny-tiny little app."

On the surface, this makes perfect sense, *right*??  I mean, this usually implies a more liberal completion time.  It's less prone to the biases of surly devs who've been forced to sit through a whiteboard interview that they may have little interest in attending.  It's a more "real life" test of the candidate's skills.  So this must be the *ultimate* solution...

*Right???*

Umm... not exactly.

To be clear, there is much to love about the take-home coding exercise.  It puts far more control in the candidate's hands - so they're less likely to feel unnecessary pressure under the watchful eye of a real-time exercise.  It can be crafted to be more applicable to the employer's environment.  It's a more "realistic" representation of what a coder can *really* do (without penalizing such activities as googling for answers).  So what's *not* to love??

Unfortunately, take-home coding exercises seem to be one of the most abused cudgels deployed by prospective employers.  They can be used to shift almost the entire burden upon the candidate, while also fostering arbitrary decisions when making a hiring decision.  Why do I say this??  Well, consider the following:

### Coding "Exercises" Almost *Always* Take Far Longer Than Promised

Here is a very-literal example of a coding exercise that I was recently asked to complete just so I could *apply* to a given job:

    You can choose any programming language and web development framework, database, and 
    web server you like. The web application you need to build is a basic todo list application 
    with the following requirements:
    
    -   Users can view their todo lists.
    -   Users can add, remove, modify and delete todo entries.
    -   Each todo entry includes a single line of text, due date and priority.
    -   Users can assign priorities and due dates to the entries.
    -   Users can sort todo lists using due date and priority.
    -   Users can mark an entry as completed.
    -   Users can reorder todo entries via drag-n-drop.
    -   You don't need to spend time on UI/UX design, if you do, it will be a bonus.
    -   Provide a GraphQL API which will allow a third-party application to trigger actions on 
        your app (same actions available in the app).
    -   Provide authentication and authorization service for both the app and the API.
    -   As a complementary item to the last requirement, you should be able to create users in 
        the system via an interface, eg a signup/register screen.
    -   If users have not registered, they must be able to use the app as a "guest".

Now you may be thinking, 

> "Well... *I* can throw up a basic CRUD application very quickly - and we want our devs to have the same ability."

But let's break down the layers in this coding exercise:

 1. **There are at least *two* CRUD layers**  
One layer to CRUD the lists, and another layer to CRUD the individual todo items in each list.

 2. **Each todo requires priority *and due date***  
And if you're doing dates with anything other than a modern datepicker, your app is gonna look pretty *janky*.  And as soon as you start throwing dates in there, it requires at least a slight complication in the sorting mechanisms. 

 3. **You must be able to reorder the items *via drag-n-drop*.**  
Umm... *WTF??*  To be clear, implementing drag-n-drop via React is no Herculean task.  But why is that a requirement *for a demo application*??  I mean, if some prospective dev isn't already familiar with the React drag-n-drop libraries, and he has to spend a bunch of time familiarizing himself with them, is that really what you want to use *as a selection criteria*?  

 4. **You *must* use GraphQL.**  
Now, I have nothing against GraphQL.  It's a fine tool.  But you're telling me that, if I had an amazing demo app already built that "only" used REST, *you're gonna eliminate me from contention*??  Lemme put this another way.  If you have a candidate who is basically a Programming God, *but*... for whatever reason, he hasn't yet used GraphQL, you don't at least want to talk to him a bit further to see if he *might* be a good match for your company/environment/team??  *C'mon, man...*

 5. **You must have authentication services for both the app and the API.**  
Can you *feel* my eyes rolling at this point???  Cuz they're *sooooo* rolling at this point.  You want me to build this demo app, with an implied data layer, and GraphQL (*not* REST!), and an authentication layer?  Umm... okay.

 6. **And as a "complementary item", you should be able to create/register users or let them maintain state as a "guest".**  
Now... read the rest of this spec.  Does that "throw in" suggestion really feel complementary to you?  I mean, sure, you could just ignore it.  After all, it's "complementary", *right*??  But if they're so fixated on the specific API format you're using, and if they're so fixated on drag-n-drop, do you really believe that they're gonna be satisfied with any submission that doesn't include the "complementary" aspects??

But here's my favorite part of this inconsiderate request:

> "You don't need to spend time on UI/UX design, if you do, it will be a bonus."

So lemme get this straight:  They're totally *fixated* on the specific API language used (GraphQL), and they feel it's *imperative* that you implement drag-n-drop, but... I don't need to spend time on UI/UX design??  Umm, yeah... *right*.  

Is it possible to throw up something like this in a mere matter of hours?  Sure.  I *suppose* it is.  If... you're already schooled in GraphQL.  And, if... you're already crazy-familiar with the various drag-n-drop libraries at your disposal.  And, if... you spend almost no time worrying whether the app looks like a hot, buttered, cow-pie.  

But if you actually take pride in what you're doing, and if you want this "simple" demo app to be a reasonable representation of the care that you take in your *craft*, there's simply no way that you'll be able to just spin up an app like this in any reasonable period of time.  

You see... "requests" like this are completely *disrespectful* of the candidates' time.  Sure, they might be able to throw up some minimally-functional app that meets these requirements in some fairly modest time-frame.  But if the candidate "throws something together", the nature of the requirements implies that the employer will reject it.  So the candidate has a daunting proposition:  Either give in and do a whole bunch of *completely-free* "demo" work (that will never actually be *used* in any functional sense) - or be eliminated from contention.

### The Best Coders Can't Be Bothered to Jump Through Your Hoops

I know that there are some overworked hiring managers out there who are thinking,

> "We have to sort through sooooo many candidates.  So it's imperative that we have a coding exercise like this to weed out the unqualified candidates before we waste all of our time evaluating them."

OK, fine.  You're busy.  *I get that.*  *You're* busy.  *I'm* busy.  *Everyone's* busy.  You're not the only person in corporate America with a full calendar of meetings and deadlines.  Maybe you're thinking that this is a genius way to clear *your* calendar and shift some of this endless hiring burden back on the candidates?  But I would respectfully ask,

> "Have you considered what this is doing to your pool of prospective candidates???"

I imagine that you don't want to hire just any bloke off the street, *right*?  You usually want "the best of the best", *right*?  So think about this, for a minute, from the perspective of those "top tier" candidates...  *Are they champing at the bit to complete your coding exercise??*

As far back as I can remember, the market for coders in America has been pretty tight.  It may not be too difficult to find the script kiddies who are desperate for their first "real" job.  But how do you find the real "hot shot" coders?  Are they combing through the (digital) want ads?  Are they knocking down your door for a job??  

Most of the "hot shot" coders that I've ever met (and I've been privileged to work with a great many of them) are rarely *looking* for a job.  They're constantly being *recruited*.  They're being wooed from one job (where they've presumably grown bored) to another.  These "superstars" aren't interested in spending hour-upon-hour on some throwaway demo app.  They're already sitting in some nice, high-paid job.  And even if they might *want* to find another employer, they don't *have to* find another one.  They have... *options*.

These top-tier coders already have a high-paying job.  And even if they *want* to find another one, they're not *desperate* to find their next gig.  In fact, many of them already have *multiple* gigs.  A "day job".  A few ongoing contract gigs that swell their bank accounts.  They have families.  And hobbies.  They have... *a life*.  And for those types, they're gonna take one look at the long list of requirements in your demo app - and they'll take a hard pass.

So you might think that you're doing an amazing job of separating the "real" coders from the pretenders with your onerous "take home assignment".  But what you're really doing is cutting off a huge segment - the highest, most qualified segment - from your candidate pool.

### Coding Assignments Often "Test" For Semantic Factors

Even if we assume that your next Hot Shot Coding Hire actually *wants* to complete your coding assignment, think very carefully about *what* that assignment is actually testing for.  In the example above, the employer isn't testing so much for whether you have overall coding expertise.  They're testing for whether you have specific experience with GraphQL, and drag-n-drop, and other subtle specifics of their environment.  The problem with this approach is that it's *shortsighted* - and it's *lazy*.

It's shortsighted because Your Next Great Coding Hire might have a ton of expertise in solving most of your coding problems.  But he may not have specifically worked with GraphQL or drag-n-drop.  But you're gonna eliminate him because the alphabet soup on his resume doesn't match - precisely - the alphabet soup that's represented *in your particular tech stack*??

It's lazy because the specifics in the coding assignment lend themselves to the mindless elimination of (otherwise qualified) candidates.  It's so easy to imagine someone reviewing the submitted assignments and saying/thinking, "Well damn, this is one of the finest coding solutions I've ever seen... but they didn't use GraphQL.  So... ***they're eliminated***!"  If your dev culture is so narrow-minded that you can only fathom hiring someone who's already worked *in your exact tech stack*, then your dev culture is garbage.

### The Asynchronous Nature of Coding Assignment Can Foster Resentment

Many dev hiring managers love code assignments because it essentially shifts much of the burden of coder assessment *off* of the employer, back *onto* the candidates.  The logic is really quite simple:

> "We can't possibly sift through all of these faceless candidates, so we'll require them all to submit some onerous "assignment".  Many won't complete the assignment at all - so that effectively weeds out the candidates for us.  And even for those who completed the assignment, we can then sit back and pick-and-choose the best-possible response(s).

Sounds perfect to the overworked hiring manager, *right*??  But aside from the (previously covered) fact that they're silently eliminating many *highly-qualified* candidates, another problem comes in the ever-growing resentment that this attitude will foster in the marketplace.  To illustrate this idea, let's refer again to the example given above.

Like many highly-experienced candidates, I rarely even bother to complete (or even attempt) such assignments.  Like many of my colleagues, I'm blessed to rarely *need* a job - and my free time is far too valuable to sink into some anonymous coding assignment for a putative job that I may, when all is said-and-done, not even want anyway.  

But despite this privilege, I actually completed this coding assignment.  For a number of reasons that I won't bore you with here, I actually *wanted* to do it.  So despite my usual reservations, I coded the whole thing up.  Put it on github.  Submitted it to the employer.  And... waited.  Unfortunately, the response was every bit as soul-sucking as I feared it would be.

For a while, I heard absolutely nothing.  In fact, I don't believe that, under "normal" circumstances, I ever would have heard *anything* from the potential employer.  (Which is, quite frankly, downright rude.)  But through a few odd coincidences, I ended up talking with someone who knew the CEO of the company requesting the coding assignment.  Here's what they told me,

> "They didn't really like your submission because you coded the backend in PHP."

Now, I implore you, please scroll up and look through those requirements again.  And please point out - *anywhere* in the requirements - where it said which language should/must be used for the backend?  To be absolutely clear, my solution had a React frontend that used GraphQL to submit its queries to the API.  The API (yes... written in PHP) was also designed to accept-and-process queries specifically submitted in the GraphQL format.  The persistence layer was handled through MySQL.  (Again, the specs said nothing about exactly which data engine should be used.)  The frontend utilized drag-n-drop to allow for visual sorting of todo items.  

In fact, my solution satisfied *every single requirement* in the assignment.  But the employer had further "requirements".  *Unspoken* requirements.  *Undocumented* requirements.  And because I didn't meet those *unspoken*-and-*undocumented* requirements, they chose not to respond to my application at all.

Think about that for a minute.  A very senior dev decides to complete your expansive coding assignment.  But because they didn't complete it in a way that perfectly matches your in-house tech stack (a tech stack that was never properly spelled out in the requirements), you're gonna just throw their application aside???  

Quite frankly, I find that to be shameful.

## Effective Coding Assignments

So... I personally *hate* coding assignments, and I believe they're always evil, *right*???  Umm... not exactly.  Like the other techniques discussed in this (long) post, coding assignments can be extremely useful.  But it's imperative that both sides in the equation have a little respect for each other.  So here are some key items to consider:

 1. **Coding assignments should almost *never* be a part of your initial screening process.**  
 Despite the (one) exception  shown above, if I see a job posting for something I *might* be interested in, but I must complete a coding assignment to even *submit* an application... I'm moving onward.  *Your* time is valuable.  *My* time is valuable.  And I'm not going to spend numerous hours (or days) trying to code up some uber-specific solution in the mere hopes that you'll talk to me.  There are plenty of script kiddies out there with marginal resumes who'd be happy to jump through all your hoops in the off chance that you'll move them along in the interview process.  I'm not that guy.  And most of the extremely-experienced, extremely-talented colleagues I know will refuse to jump through those hoops as well.

 2. **Get over yourself.**  
 Obviously, there are *some* companies out there that will put up such large barriers-to-entry as a hyper-specific coding assignment before they will even *consider* you.  Those companies have names like Amazon.  And Google.  And AirBnB.  They pay *handsomely*.  They have tremendous *clout* in the developer community.  They get *thousands* of applicants every year.  They can easily afford to be so choosy.  Chances are, if you're reading this, you are *not* with one of those companies.  You probably believe that your early-stage, venture capital, startup is The Next Unicorn.  But the most talented devs out there have been around the block a few times.  And they know better than to burn their nights and weekends meeting all the nitpicky requirements of your demo app.

 3. **Convert your coding assignment into *live* sessions.**  
 Do a screenshare with the qualified applicants that you've already identified, give them an open-ended coding assignment, and ask them to code it in front of you.  Yes... this will require more *time* on your part.  Time that will yield *far better devs*.  There's literally no limit to the scope you can ask for.  You can ask them to, from scratch, recreate Facebook.  Will they finish it during your screenshare?  Of course not.  What's important is that you will see, in real-time, how they go about the process of building-and-architecting an application.  And what if they don't choose to use the exact tools that exist in your chosen tech stack?  Who the hell cares??  Don't get bogged down in the specifics of your particular tech/alphabet soup.

 4. **Set a hard limit on the live, screenshared, coding assignment.**  
 I personally recommend two hours.  Tell the candidates, upfront, that they won't necessarily be expected to complete the assignment and that they won't be asked to code any longer than the previously-communicated time limit.  If you can't tell, after two hours of watching someone live-code a potential application, whether or not you'd like to hire them, then forcing them to spend 10 more hours of their own time won't answer the question for you.  And when you approach coding assignments in this way, it communicates to your next potential Coding Rock Star that you actually have some respect for their time and their talents - and that if they were to accept a job offer from you, they can expect the same respect once they're officially onboard.

 5. **Do NOT abandon *anyone* who submitted an assignment.**  
 This one is *huge*.  If someone has agreed to do all that free work just for the purpose of (hopefully) demonstrating their worth, the most disrespectful thing you can possibly do is to simply ignore them.  Every single submitted exercise deserves at least *some* level of earnest feedback on *your* part.  If you think you can't possibly fulfill such a requirement, then **stop soliciting code assignments**.  *Seriously*.  Stop it.  *Right.* ***Now***.  Think about it like this:  Imagine agreeing to work *for free* for someone, for an entire day, in the hopes that they'll extend you a formal job offer.  Then, at the end of the day, not only have you not received an offer, but no one in the company will even *talk* to you.  They've disappeared.  If you did anything "wrong", or even just "suboptimal", there's no way to know it, because the jerks who agreed to let you work for free for the day can't be bothered to give you *any* meaningful feedback.  They just got in their cars and went home and left it to you to find your own way out.  That's what it's like when you pass out all these take-home coding assignments - and then you don't bother to give any thoughtful response to the submitted effort.  It's a ridiculous slap in the face.

 6. **Throw out your tech stack.**  
 If you have a React shop, but someone can wow you with their ability to code up an amazing application in Angular, should that really count against them??  Do you really want to eliminate someone who's a Coding Rock Star - but doesn't happen to have specific experience in your narrowly-defined tech stack?? Think about that for awhile...

