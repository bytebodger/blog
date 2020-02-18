# The `class` Boogeyman in JavaScript

JavaScript, and its evil nemesis object-oriented programming, have experienced some remarkable role reversals in the last 10+ years.  I'm old enough to remember when JavaScript was little more than a toy.  It's only real use was to dump some useless bit of real-time functionality in the middle of a web page.  (*Oh, look!  I've added a timer to the bottom of my page!*  Or... *Oh, look!  I built a calculator on my page - yeah, just like the one you already have on your desktop... but with fewer features and more bugs.*)

I'm also old enough to remember when the programming world was dominated by developers who would openly scoff at you if your weren't writing your code in a "real" language.  And when they said "real" language, they always meant - a compiled, object-oriented, strongly-typed language.  To be even more specific, most people preaching about "real" languages in the 90s and the early 00s were really just talking about *one* language - Java.  Starting from the mid-00s, C# soon became included in the hallowed pantheon of "real" languages. 

Server-side scripting languages definitely did not qualify as "real" languages.  But even the guys writing in server-side scripting languages looked down their noses at the dweebs playing around with JavaScript.

## A Tectonic Shift

Obviously, the "heavyweight" OO languages, like Java and C#, are still massively used and their influence only continues to expand.  But it's pretty interesting to see how JavaScript has almost flipped the tables on the snobs who used to dismiss it as a worthless toy.  Nowadays, some of the juiciest job postings are for devs who can write most - or all - of an application entirely in JavaScript.  With tools like Node and Express and MongoDB, there's not even any need to confine your JS skills purely to the frontend.  

With the "rise" of JavaScript, it was perhaps inevitable that all those young, new coders - the ones who didn't have to spend years writing Java/C# when those were the only jobs paying any real money - would start to reassess (and even scorn) the principles that originally made Java/C# great.  Specifically, I'm seeing a huge trend whereby JS devs aren't shy about openly badmouthing any-and-all of the core tenets of object-oriented programming.

If I sound biased in favor of OO, trust me - I'm not.  In many use cases, I believe that OO is a bloated mess.  But I also believe that almost any programming tool is just that - a tool.  You wouldn't decide to build your house - or *all* houses - with nothing but a hammer.  Because there are times when a hammer is the flat-out wrong tool for the job.  Similarly, I'm convinced that, in many cases, OO is also the wrong tool for the job.  But just because the hammer is not always the best tool for the job, that doesn't mean that you chuck your hammer in the garbage.  Sometimes you *need* that tool.  When you have a "hammering" job, it's just silly to attack it with a screwdriver. 

But just as the Java snobs from the 90s and the C# snobs from the 00s tended to dismiss *any* valid use for JavaScript, I find now that many JS devs tend to dismiss *any* valid use for OO.  Many of my JS colleagues talk about OO like it did something wrong to them in their childhood.  I've found myself wanting to show them a doll of the OO Demon and say, "Now show me where the bad man touched you."

##  The Ambiguity of `class`

For the most part, these functional-vs-OO language debates are purely academic.  When you take a new job, or you're placed into a new (to you) project, most of the tech-stack debates have already been long-since settled.  For example, if you begin working as a "Senior Frontend Engineer", where you'll be expected to work in any particular flavor of JS, the odds are that you never need to have much of an argument - with anybody - about whether you should use a functional or OO approach.  If the entire legacy environment is written in JS, then it's almost certain that any new coding you do in that environment will be done in JS, and there won't really be any room to debate whether you should throw some Java or some C# into the mix.  

But then, JavaScript introduced the `class` keyword...

Now, JS devs could craft code that ostensibly *looked* like OO - even if it was never *truly* OO.  If you've already been ingrained in the OO world, this might have felt quite natural to you.  OO devs *think* in terms of classes.  It's the core building block of your mental architectural process.  If you weren't already ensconced in that mindset, it wasn't much of a problem either.  Because JS never *forces* you to use `class`.  It's just a new keyword that you can reach for - if you see fit.

By my reckoning, this didn't seem to cause too much of a stir when the `class` keyword was first introduced.  Some JS devs embraced it.  Others just shrugged.  Because all of the "old" JS approaches to objects were still perfectly valid.  

But in the last several years, there seems to be a growing backlash amongst the "luminaries" of JS development against any use of `class` in JS code.  There are long, sometimes vitriolic posts made by the JS snobs (and they *are* sounding more and more like snobs) about why the `class` keyword is just plain *evil*.

Although the anti-`class` brigade can be found in all corners of JS fandom, it seems to be particularly recalcitrant in the React community.  As soon as React started gaining massive adoption, there was an entire wave of senior JS devs that were wringing their hands over how to solve the `class` "problem" that became more firmly entrenched with React - because the original implementation of React almost assumed that most/all of your application would be encased in classes.  (To be clear, even with the first publication of React, you were never *required* to use classes - but most of their documentation assumed that you would be using them, and the practice became an increasing point of contention for the anti-`class` crowd.)

##  Lame Arguments

The reasons why some senior JS devs hate classes are too numerous to list here.  But here are some of the major points that I've gathered:

 - **JavaScript is *not* an OO language, so we shouldn't be using language constructs that mirror OO functionality.**  
 I find this to be borderline-laughable.  If your devs don't understand the difference between a "true" OO language and a language that uses prototypical inheritance - they shouldn't be your devs.  You shouldn't hire them.  There are plenty of keywords that mean one thing in a given language, but mean something slightly - or entirely - different in another language.  That's just part of the game if you've chosen to learn multiple programming languages.  

 - **I worked on this really horrible project once that made a mess of OO and it made my life hell.  So we should never use the `class` keyword because it reminds me of that horrible experience.**  
 For example, many of these anti-`class` rants center on the mess that can be created by working in an OO project that has made over/poor-use of inheritance.  *But guess what??* Even many OO devs acknowledge that inheritance is a fickle beast that should only be used with caution.  That doesn't mean that we should run screaming anytime someone proposes the use of a `class` keyword in our codebases.  Any seasoned JS dev can give you horror stories about a legacy JS codebase that he had to muck through.  That doesn't mean that JS's language constructs are "bad".  It just means that you can write crappy code - in *any* language - regardless of the chosen set of keywords.  
 
 - **As a functional language, JS programming should be focused on the creation of *pure* functions, and classes go against that model.**  
 OK, sure.  I agree with that.  But here's the deal:  Show me any large, enterprise-level JS application where *every single bit* of business logic is encapsulated in a pure, stateless function.  If you can show me that, I will show you Santa Clause and the Easter Bunny.  Because they simply do not exist.  Sure, you can write a component - or a simple utility - that qualifies as a *pure* function - or a collection of *pure* functions.  But once your app grows to a "certain size", it's inevitable that you're gonna start writing some functions that most definitely are **not** "pure".
 
 - **Classes slow down some of the tools that we use for code optimization.**  
 OK, so let me get this straight.  You have additional tools that you've packed on top of your chosen library, and those tools can't properly handle the language constructs that are (for quite some time) native to the language itself.  So your "solution" is to rail against the use of the language constructs themselves???  *C'mon, man...*  Did it ever occur to you that maybe - just *maybe* - you need to improve the bolt-on tools that you're using, rather than trying to code-shame people who are using the language's core constructs??
 
 And here's the one that really gets me:  It's on the ReactJS site, where they explain the use case for hooks.  It says, verbatim:

>  "Classes confuse both people and machines"

Umm... *what???*

If you're a dev who's *confused* by the mere concept of classes, well... you might want to consider a new line of work.  If you go into a job interview - even a job interview based purely on JS, and you say, "Well... I can't really answer that question, because classes just confuse the hell outta me," you can pretty much bet that the interviewers will be cutting the session short, thanking you for your time, and throwing your resume in the garbage.

## Syntactic Sugar

Here's where, IMHO, all of the anti-`class` crusaders just miss the whole point.  In JavaScript, the `class` keyword... wait for it... doesn't actually *do* anything.  The introduction of `class` to the ECMA spec didn't add a single piece of new functionality.  All `class` "does" is it provides you with a shorthand way of doing *the exact same thing that you could always do in JavaScript from the beginning*.  Consider these two examples:

```
    // Example A
    const myObject = {
       someProperty : 'foo',
       anotherProperty : 'bar',
       printToConsole : value => console.log(value),
    }
    console.log(myObject.someProperty);  // 'foo'
    console.log(myObject.anotherProperty);  // 'bar'
    console.log(myObject.printToConsole('foo bar'));  // 'foo bar'
```

Or:

    // Example B
    class myClass {
       someProperty = 'foo';
       anotherProperty = 'bar';
       function printToConsole(value) {
          console.log(value);
       }
    }
    const myObject = new myClass();
    console.log(myObject.someProperty);  // 'foo'
    console.log(myObject.anotherProperty);  // 'bar'
    console.log(myObject.printToConsole('foo bar'));  // 'foo bar'    

Functionally speaking, what's the difference between A and B??  *Absolutely nothing.*  So here we have two different syntactic approaches to achieve *the exact same result*.  But some would have you believe that A is somehow... "good".  And B is somehow... ***evil***.  Hmm...

Now I can hear some of the readers screaming,

> "But... BUT!  What about the evils of inheritance (`extends`)?!"

Yeah, umm... you could do all of that in "old school" JavaScript as well.  Again, the `extends` keyword, like the `class` keyword, *doesn't provide a single bit of new functionality* in JavaScript.  It only gives you a shorthand method to achieve the same effect.  In fact, using plain old "legacy" JavaScript, you could even create private class members - by using closures.  So you see, these new keywords (which aren't so new anymore), just give you a way to do the same functionality *that you could always do*, in a slightly different syntax.

Now, if you want to tell me that examples A and B are *both* somehow "bad", well... I wouldn't agree with you, but at least your argument would be logically consistent.  But if you want to tell me that Example A is somehow "good", and Example B is somehow "bad"... then you're just being dogmatic about your *personal*, *chosen* syntax.

##  The Sacred Order of JavaScript

Whenever a new language is launched, its first challenge - if it's to gain a valid foothold in the marketplace - is to foster a growing *community* of people who are trying to solve real-world problems with that language.  These can be professionals and/or hobbyists and/or academics.  Once people really dive in and start *using* the language, they're gonna run into edge cases where they can't figure out how to solve a particular problem in this particular language. 

So they start googling...  And those searches, eventually, lead to forums dedicated to others trying to answer the same problems.  They start finding answers on Stack Overflow.  They start sharing "tips and tricks".  And, if the language is to grow, so too does the community that's supporting that language.  In this respect, JavaScript is no different than any other language that's gained widespread adoption.  The community is wide and deep - and that's a very good thing.

The next step in a language's maturation is the rise of its "Sacred Order".  This is a step beyond mere "community".  If the language keeps growing, eventually there will be certain luminaries who drive the perception of everyone else who considers themselves to be part of the community.  About a decade ago, JavaScript started to attain its own Sacred Order.  This isn't a knock against JavaScript.  There's a Sacred Order of Java, a Sacred Order of C#, etc., etc...

In general, Sacred Orders, like the embryonic "communities", are a net-good for the language.  They foster the "thought leaders" who drive the language forward.  But Sacred Orders also have a downside...

Once the Sacred Order is established, their edicts tend to be taken as gospel.  This can be a very *good* thing.  But it can also have negative side effects when the Sacred Order's *preferences* start being adopted as unquestioned dogma.  

The Sacred Order of JavaScript seems to be flogging this idea that "classes are bad, mmmkay??"  Because they're the Sacred Order, most of the "lesser" devs just seem to fall inline.  After all, what junior-to-midlevel dev wants to be railing against the edicts of an established luminary like, say, Dan Abramov?  I mean, if you don't have that kinda clout, who are you to question the latest trend that's being foisted upon us by the acknowledged thought leaders?

But even "thought leaders" have biases.  *Faults*, even.  There are some things that they rail against purely because they don't personally *like* them.  And when this happens, everyone else tends to fall in lockstep behind them.  The `class` keyword definitely falls into this category.  The Sacred Order says classes are *bad*.  Therefore, it must be so, *right*??

I've already covered how `class` is just a bit of JS syntactic sugar.  So let's look at something else that's *also* syntactic sugar - but the Sacred Order loves it.  I'm talking about arrow functions.

What's the difference between these two code snippets?

    // Example A
    const myfunction = function() {
       console.log('it ran');
    }
    console.log(myFunction());  // 'it ran'
Or:

    // Example B
    const myFunction = () => console.log('it ran');
    console.log(myFunction());  // 'it ran'

Obviously, there is no functional difference.  *They do the exact same thing.*  You see, arrow functions are nothing more than syntactic sugar.  They allow you to do the exact same thing that you were always doing in JavaScript, in a slightly different syntax.  Yes... an arrow function is generally seen to be "cleaner".  But there's nothing *wrong* about declaring your functions in the old-school format.

So does the Sacred Order of JavaScript rail against arrow functions the same way that they rail against the `class` keyword??  Of course not.  They *love* arrow functions.  You can't get through any modern JS tutorial without having a proper understanding of arrow functions.  But there are plenty of modern JS tutorials that go to great lengths to purposely avoid the `class` keyword.  Why??  Umm... because the Sacred Order says that the `class` keyword is *bad*. (Mmmkay...?)

My point here is not to tell you that arrow functions are, in any way, "bad".  Arrow functions are awesome!  But it's silly to reject the `class` keyword - that does the exact same thing as "old-school" JavaScript, but to wholeheartedly embrace arrow functions - which also do the exact same thing as "old-school" JavaScript.
 
##  Stop Focusing on Keywords

I'm not trying to argue that JS doesn't have its share of *good* practices and *questionable* practices.  *Every* language has numerous examples where inexperienced devs created horrific code that leveraged a given keyword.  That doesn't mean that the keyword was somehow "evil".  It just means that the code sucked.  And no amount of hand-wringing over the `class` keyword will ever remedy that.

Just consider the `while` keyword.  Nearly every language has the ability for you to create a `while` loop.  In general, `while` loops are always at least a little bit tricky, because the loop doesn't have any built-in assurance that it will stop after a given number of iterations.  If you've never created code that launched an infinite `while` loop, then you haven't done much coding.

Does that mean we should remove the `while` keyword from the language?  Of course not.  Does that mean we should code-shame anyone who feels comfortable using a `while` loop?  Of course not.  The vast majority of your loops should *not* be `while` loops.  But there are places where a `while` loop is absolutely the right choice.  The "answer" to this problem isn't to banish the `while` loop.  Nor is it to rant against its use.  The simple fact is that the `while` loop, although it may have disadvantages, is still a valuable tool to have in your tool belt.  The answer isn't to throw the tool in the garbage.  The answer is to hire/train devs who understand the pros-and-cons of every tool so that they may make wise choices going forward.

And with JavaScript's `class` keyword, the approach should be exactly the same.  Don't throw out the tool because of some dogma that you learned when you were coding in 2007.  Instead, endeavor to understand the tools at your disposal and make the best possible choices going forward.
