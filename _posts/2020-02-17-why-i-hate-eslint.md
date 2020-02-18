---
layout: post
title:  "Why I Hate ESLint - and How I Learned to Love It"
date:   2020-02-17 00:00:00 -0500
categories: eslint linting airbnb standardization javascript
---
I'm old enough to remember coding in the "bad old days".  I remember when a great portion of code was written in Notepad (not even Notepad++).  I remember when every aspect of coding "style" was a *suggestion*, or a "best practice".  As you can imagine, I've seen *a lot* of really ugly code.  For example, you don't need to explain to too many coders why the following snippet is ugly as hell:

```javascript
let dogs = ['boxer','bloodhound','doberman'];
for (let i = 0; i < someLimit; i++) {
for (let j = 0; j < dogs.length; j++) {
let thisDog = dogs[j] + '(' + i + ')';
let stepsWalked = 0;
while (stepsWalked < 10) {
console.log(thisDog + ' has walked ' + stepsWalked + ' steps');
stepsWalked++;
}
}
}
```    

It doesn't take a genius to see that there are "layers" to this snippet.  And the human eye is not easily prone to see those layers unless additional formatting clues are provided to future coders who are forced to troubleshoot it.  For this reason, one of the first things we are taught (by the Greatest Programming Instructor Ever Known - i.e., the internet), is that these different "layers" should be indented on their own level so as to make it easier for other coders to read the nested loops of logic.

## The Birth of "Standards"

Back in the "bad old days", the desired formatting was "enforced" by coding standards.  Of course, those standards were rarely written down anywhere.  Even when they were written down, we had almost no tools to enforce them (other than other coders spotting the ugly code before it reached production).  More often than not, if these "standards" were even enforced at all, it was typically done through *code shaming*.  

Another coder would look at the snippet above and say, 

> "*WTF??*"

  In the worst-case scenario, the offending code would never get caught, it would stretch over hundreds of lines of code in a single sprawling file, and subsequent coders were forced to either A) visually parse through the mess, and/or B) waste time that should be devoted to their main task so that they could properly reformat the jumbled mess.  

Of course, even if the dev team agreed that *some* things were simply unacceptable (i.e., writing nested code with no indentation), there was still plenty of room for argument.  Should the opening `{` be on the same line as the loop condition or should it be on its own separate line?  Should the code be indented with tabs or spaces?  (The ultimate coding Holy War.)  If indented with spaces, *how many spaces* should be used in each indent?  The list of possible styling choices goes on and on...

Those who've been in application development for even a few years can attest that these styling arguments stir great passion - and can linger for weeks, or even months.

## Linting Tools to the Rescue

With the advent of better IDEs, we also started to see more effective plugins for those IDEs.  One of the most effective innovations amongst all IDE plugins is the linter.  By installing this simple tool - and by ensuring that the configuration of the linter is included in the code repository, we can now start to *enforce* the coding style that is desired by any given team.  Taking it a step further, we can even ensure that our deployment tools (e.g., Jenkins) are set to check the submitted code against the linter - and to even **fail the build** if the code doesn't comply with the rules configured in that linter.  

This is, admittedly, a quantum leap from the "bad old days".  And I would certainly welcome almost *any* set of linting rules as opposed to allowing some junior dev to push the offending code listed at the top of this article.  But this incredible advancement is not without its downsides...

## The Advent of the Style Guide (and the rise of Code Nazis)

When I first joined a team that was making religious, formal use of ESLint (and the subsequent Jenkins hooks), I admittedly saw it as a blessing and a curse.  On one hand, it was easy to see the utility in stopping someone from pushing a branch that contained, say, no indented code.  That shit's annoying.  And if a junior dev tried to submit unindented code, I'd immediately admonish him and tell him to correct it.  

But I quickly realized that ESLint can be used to enforce a *massive* set of truly arbitrary styling rules.  I don't pretend to be a seasoned master on all of ESLint's configuration options (or those of the many competing linting tools, for that matter).  But you can spend *days* working through all of the potential checks that can be used to forcibly prettify a team's code.  

If you want to get a feel for the extensive degree to which these rules can be configured, you only need to look as far as the (in)famous [AirBnB Style Guide](https://github.com/airbnb/javascript).  This guide attempts to answer nearly *every* styling decision that a coder might otherwise be forced (or be free) to decide on their own.  It doesn't just say, "Those nested conditions must be indented."  It tells you *how* they must be indented (with two, *and exactly two*, spaces - and don't even think about using a `TAB` character).  It tells you where your curly braces *must* be placed.  It tells you *exactly* how many empty lines you must have before `return` statements, and around functions, and at the end of code files.  The list goes on - but it basically tries to ensure that every single code file follows the *exact* same styling guidelines down to a finite degree of control. 

To be fair, AirBnB is far from the only major organization to post an extensive set of their own styling guidelines (I'm looking at *you*, Google).  And, in theory, I applaud any organization that decides to take a proactive approach to the standardization of their own code.  But the publication of these massive styling tomes (with their associated ESLint configuration files) led many smaller organizations to just decide that they would use the AirBnB Style Guide as their own, and they would deploy group ESLint files to force all of their coders to adhere to the same standard.

Of course, any time that an organization (or a person) decides to adopt a massively-circulated de facto standard, such as the AirBnB Style Guide, it also encourages the people working in that organization to (lazily) adopt the position that their chosen style guide is dogmatically *correct* - and that any dissenting voices are clearly and obviously *wrong*.  

Once these widely-circulated style guides became de rigeur, it wasn't long before every dev team had at least one pedantic jerk who was eager to shout you down if you proposed even the slightest alteration to the ESLint configuration files that were handed down from god (AirBnB) on stone tablets.  In other words, these style guides became tangible evidence for the Code Nazis to shout about any time your code failed even the slightest ESLint rule.

## The Lost Beauty of `warn` vs `error`

None of this is the "fault" of the ESLint team.  They undoubtedly realized that some styling "choices" should be seen by the broader dev team as *wrong* - and should throw an outright `error` if they're encountered.  For example, if someone can't be bothered to indent their code - *at all* - I perfectly understand that it will probably throw an `error` in ESLint.  And it should.  

But in my experience, across many organizations and on many dev teams, it seems that few (if any) of the linter rules are set to `warn`.  They're almost *all* set to `error`.  In other words, these organizations have decided that, if your code doesn't perfectly satisfy every single one of the ESLint rules, it should **fail the build**.

Now, I understand that there's reasonable debate about exactly which rules should be set to `warn` and which ones should be set to `error`.  And I don't pretend that this debate is easily or quickly resolved amongst all dev teams.  But the (extremely lazy) option that seems to have taken root, in lieu of even having that debate in the first place, is simply to set *all* of the rules to `error`.  In theory, this should force "perfect" code standardization.  But there's a significant cost that "perfection".

## The Tyranny of Code Standardization

You may be thinking, 

> "Why *wouldn't* we want to enforce perfectly-standardized code??"

  Well... I'm glad you asked.

Many devs have acquired their individual coding "styles" as the result of years of hard-fought trial and error.  Some of these style choices were crafted from many past coding/troubleshooting mistakes.  So it's more-than-jarring when you come into a new dev team and you realize that aspects of your "style" will now cause the build to **fail**.  Consider this example:

```javascript
const myObject = {
   foo : 'bar'
   ,uno : 'dos'
   ,some : 'thing'
   ,another : 'element'
};
```    

This is how I always used to write an array or an object that had a comma-separated list of values.  *You see what I did here?*  The comma that separates every property in the object is placed at the beginning of each new line - as opposed to the end.  I did this because, back in the "bad old days" of programming, the following code snippet *would not compile*:

```javascript
const myObject = {
   foo : 'bar',
   uno : 'dos',
   some : 'thing',
   another : 'element',
};
```

It wouldn't compile because there's an "extra" comma after the last property in the object.  So if you wanted to keep the commas at the end of each line, but you still wanted to it to compile, you had to do it like this:

```javascript
const myObject = {
   foo : 'bar',
   uno : 'dos',
   some : 'thing',
   another : 'element'
};
```    

In other words, you had to remember to avoid placing a comma after the last property in the object.  If you didn't, it wouldn't compile.  Of course, when you're troubleshooting, or adding new features, it's not uncommon that you have to add new properties to the end of this object.  So if you had all your commas at the end of each line, you first had to remember to add a comma to the *previous* line before creating your new property on the next line.  

Furthermore, if you ever forgot to add one of those commas on any line that contained a property, it was very easy to visually spot the flaw, because the left-aligned commas were all sitting in a nice, neat, vertical column, and it was very evident to the naked eye that one of the properties was missing the required comma.

To be perfectly clear, I fully realize that neither of these approaches (comma at the beginning of the line, or comma at the end) is really that big of a deal.  Any seasoned dev should be able to spot the problem fairly quickly.  But I just found, over many *years* of dev, that it led to fewer bugs and less time spent writing new code if I could simply left-align all my commas in front of each new line.

Now, you may be thinking, "But modern languages now allow for the superfluous last-comma, placed after the last property in the column."  To which I'd say, "Sure.  Okay.  That's *mostly* correct.  But consider this example:"

```sql
SELECT
   column1,
   column2,
   column3,
FROM
   someTable
```

In many database engines, *this example still doesn't compile*.  Because many database engines still have not added support for that superfluous trailing comma in the result set.  And even if a given database engine adds such support, most tech stacks are far quicker to update their version of the programming language long before they think about updating their version of the database engine.

So this means that if I'm a "full-stack developer" (and most of us who've been in this game long enough are just that), I can no longer use a single standard between, say, my JavaScript code and my SQL queries.  If I'm using the AirBnB ESLint rules, I have to *remember* to use the trailing commas in my JavaScript code, but I still must *remember* to not add the final trailing comma in my SQL queries.  And I'm a firm believer that, if your "standard" requires devs to flip from one style to the next, as they flip from frontend-to-backend code, then your standard has some potential flaws.

## Rising Above the Pedantry

If you're still reading, and you're now convinced that this is a post about whether you should use leading- or trailing-commas in your code... **STOP**!  That is *not* my point!  You see, I really couldn't care less how you choose to write your arrays/objects/results/etc.  If you write your objects with leading commas like this:

```javascript
const myObject = {
   foo : 'bar'
   ,uno : 'dos'
   ,some : 'thing'
   ,another : 'element'
};
```

Then... yay!  I applaud you!

If you write your objects with trailing commas like this:

```javascript
const myObject = {
   foo : 'bar',
   uno : 'dos',
   some : 'thing',
   another : 'element',
};
```

Then... yay!  I applaud you!

If you prefer to write your objects on a single line, whenever feasible, like this:

```javascript
const myObject = {foo : 'bar', uno : 'dos', some : 'thing', another : 'element'};
```

Then... yay!  I *still* applaud you!

You see... I really couldn't care less how you write such an object in your code.  There are a few, semantic scenarios where I would argue that one approach *might* be, nominally, "better" than the other.  But for the most part, I really don't care.

I've got a lot of shit to get done in any given day of coding.  Enough shit that I *totally* can't be bothered to argue with you about where you choose to place the commas in your object definition.  

But ESLint cares...



## The Automated Code Nazi

The first time I worked on a team that utilized an aggressive ESLint configuration, I ran into a problem very similar to the one I just outlined above.  I was defining some silly little object in my code and, as I was wont to do, I placed each property of the object on its own separate line.  And then... I committed the unspeakable sin of putting a leading comma in front of each of those lines.  (*The HORROR!!!*)  

I wasn't completely blind to the "error" that was awaiting me.  I saw the little squiggly line in my IDE that was caused by the linter recognizing my blasphemy.  But at first, not having confronted the scenario before, I was honestly pretty confused by it.

I knew that my code ran just fine.  It compiled in the browser when I ran it on localhost.  All my unit tests passed with flying colors.  So I just decided to shrug it off.  You see, I didn't look closely enough at the linting message in my IDE and I made the cardinal mistake of assuming (ass -> u -> me) that the linter would throw a `warning` and not an `error`.

I pushed my code and created a pull request.  None of the other devs caught my "error" (nor did they really *care*), and it was approved to be deployed to the QA environment through Jenkins.  You probably know what happened next.

A short time later, I received one of those automated Jenkins notices stating that my build had **failed**.  I was honestly pretty confused by the failure at first.  In fact, I was so flummoxed by it that I had to ask another dev to look at the failure report to help me determine exactly *why* my build had failed.  (Even amongst the most seasoned devs, Jenkins failure notices can, at times, be a bit... *cryptic*.)  So I was doubly confused when I realized that my build had actually **failed** because of my dastardly insistence on using leading commas.

## A Time to `warn` and a Time to `error`

I didn't really mind so much that my local instance of ESLint might *flag* my unthinkable use of leading commas as a `warning`.  I mean...  *I get it*.  If your team has decided that, in general, you want to use trailing commas, then fine.  Throw a `warning`.  Let me, as the developer, see the `warning`, so that I, *with my 20+ years of experience*, can decide whether the `warning` is a real problem - or not.  But to flag this "problem" as an `error`???  *C'mon, man...*

You see, there *is* a place to throw an `error`.  And there *is* a place to throw a `warning`.  And if your dev team hasn't made any real attempt to think about the difference (and the *utility*) between the two, well... that's just *lazy*.

Maybe you're thinking, based upon this pedantic rant, that I just don't care about the coding practices of the rest of the team?  Maybe you're thinking that I just want to code everything in my own chosen style - general coding practices be damned?  But this is *not* the case.  

The question you should be asking yourself is, 

> "If a developer used a different style, is it truly *harmful* to the
> overall work of the dev team?  And should this 'issue' be flagged as
> an outright `error` (meaning that no one can ever go against it), or
> should it be flagged as a `warning` (meaning that it can ultimately be
> left up to the developer's discretion)?"

If you think I'm being dogmatic about this, please consider the following example:

```javascript
const legacyObject1= {
   foo : 'bar',
   uno : 'dos',
   some : 'thing',
   another : 'element',
};
const theNewObjectThatIveInserted = {
   foo : 'bar'
   ,uno : 'dos'
   ,some : 'thing'
   ,another : 'element'
};    
const legacyObject2 = {
   foo : 'bar',
   uno : 'dos',
   some : 'thing',
   another : 'element',
};
```

In this example, I can fully understand why someone might deem my newly-inserted object to be "wrong" (or at least - poor coding practice).  Because, in this example, there's legacy code that was following the trailing-comma standard, and I've gone right into the middle of it and inserted new code *that doesn't match the prevailing style in the file*.  

In this example, I've created a bit of a logical incongruency inside a single code file by using mismatching styles.  In this scenario, I would fully understand if someone else (presumably, during code review), looked at this code and said, 

> "Umm... you should really alter the style of your new object to match the style of the other objects in the rest of the file."

I *get* that.  There are many valid reasons for maintaining a consistent coding style *within a given code file*.  But if I'm writing an entirely new file of code, is it so blasphemous to think that this new file might have leading commas when other files in the codebase use trailing commas??

## The (Completely Lame) Code-Reading Excuse

Here's where many devs will start screaming,

> But... BUT!!!  Code *reading* is the largest part of a developer's day!!!

Okay... yeah.   I get that.  It's a really lazy excuse,  But yeah... I get it.

If you've been coding for more than a couple years, you've seen the studies.  The vast majority of a coder's day isn't spent actually *writing* code.  The majority of a dev's time is spent *reading* existing code.  If you're troubleshooting, nearly *all* of your time is spent reading existing code while you try to isolate the problem.  Even if you're doing green-fields development, you still end up spending vast amounts of time reading the code that's already been written/committed by you or other members of your team.

But here's the thing:  If you open one code file, and it has trailing commas.  Then, later, you open another code file, and it has leading commas.  And *if this somehow breaks your brain*, or significantly increases the time needed for you to "grok" what is happening... then you're in the wrong career field.  

I mean... c'mon.  How many times have you been perusing a bunch of trailing-comma code, then you open some rogue-file that contains leading-comma code, and you thought, "Oh... man.  I can *barely* understand what the previous dev was even trying to do here"???  If that's you, then you should seriously reassess what you're doing for a living.  If that's you, and you're a member of *my* team, I gotta really wonder if I still want you on my team.  

At the top of this post, I showed an example of aberrant "styling" (or, if you will, a complete *lack* of styling), that could truly delay a future developer's ability for them to grasp the logic in the code.  The complete lack of indentation makes it significantly more difficult to quickly read the logic and understand what it's doing.  But if trailing-or-leading commas gives you the same delay, then you need to consider cross-training.

So if you're ever perusing the ESLint file and you're wondering whether a rule should be set to `error` or `warn` (and I hope that, at some point, you *do* actually assess the linter's config file), you need to ask yourself, 

> "Would a lack of compliance with this rule really degrade our team's ability to swiftly debug/extend the functionality in a given code file?  Or is it just something that should give the original developer some pause before he/she submits the code?"

If it's the latter, then the rule should be set to `warn`, and not `error`.  Because you shouldn't be **failing builds** just because someone decided to add leading commas to their objects/arrays.

## So... ESLint is *Evil*, Right??

Umm... not so fast.

In aggregate, linting tools are definitely a net *good*.  You don't have to be old enough to remember the "bad old days", like me, to understand that:

    almostAnyStylingStandardAtAll >>> aCompleteLackOfStylingStandards

I would never want to return to the time when the only code-styling standards were those that were enforced in a single developer's head.  Even in the most rigorous of environments, coding... *aberrations* will inevitably slip through the cracks if there are no automated tools in place to flag the outliers.  

Even if the dev team consists of only seasoned professionals, a rigorous linter is a great "first line of defense" to ensure that everyone knows how they "should" code and is aware when they've stepped outside those boundaries.  But the seeming disregard for `error` vs. `warn` is a growing headache that, IMHO, is only getting worse with the increasing proliferation of coding pedantry.

As much as I've railed against the blind adoption of *other* organizations' standards (i.e., the AirBnB Style Guide), I'd be the first to admit that I'd rather operate under those (ridiculously rigorous) standards as opposed to operating in an environment devoid of *any* formal/defined standards.

## Linting Tools to the Rescue

Perhaps the best way to highlight the inherent value of ESLint (or *any* shared linting utility), is to highlight a recent case where I had no linter.  You see, the linter can be your best friend when it comes to the (unfortunately) nitpicking nature of *some* dev teams - especially during pull requests / code reviews.  I hope to write an entirely separate post about the joys-and-sorrows of code reviews, but for now, let me outline what happened, only months ago, at a *huge* dev shop in town.

I was contracting for the largest health insurance provider in Jacksonville, Florida.  (I don't want to devolve into name-calling here, so if you really want to trace that one down, I'm sure you can utilize your epic Googling skills to figure out who I'm talking about.)  The team I was assigned to was, like *so many other teams* in *so many other organizations*, convinced that they just had *so much* work, and *so few* people, that they couldn't possibly be bothered to spend the time to outline any code-styling standards for their devs.  Their only "standard" was:  

> "Look at the rest of the codebase, and craft your code accordingly."

As you can probably guess, their existing codebase was a case study in contradictions.  Did they want leading-or-trailing commas in their objects/arrays?  Well... there were conflicting examples in the existing codebase.  Did they want methods/functions separated by blank lines?  Well... there were conflicting examples in the existing codebase.  In fact, for nearly any code-styling choice you might make, you could look at the legacy codebase and say, 

> "Well... over *here*, they did it one way.  But over *there*, they did it another."

So what's a dev to do??  Well, I did the only thing that I *could* do.  I tried, as best I could, to "match" the legacy (non)standards.  Then, with my tests written and my code working properly in my local environment, I committed/pushed the branch, created a pull/merge request, and waited for the rest of the devs to either approve the request... or to pick apart what I'd written.

And, oh boy, did they have a fun time picking things apart.

They didn't like the fact that I'd coalesced a variable into a `Boolean` with:

```javascript
const someVar = !!comparedVar;
```

They wanted me to instead use:

```javascript
const someVar = Boolean(comparedVar);
```

*Even though*... there were examples in the legacy codebase where a double-bang had been used.

They didn't like the fact that I'd used:

```javascript
render() {
   return (<SomeComponent style={{fontSize : '1.2em'}} />)
}
```

They wanted me to instead use:

```javascript
render() {
   return (<SomeComponent className={'someSingleUseCssClassThatWouldNeverBeLeveragedAnywhereElse'} />)
}
```

*Even though*... there were examples in the legacy codebase where inline `style` attributes had already been added to existing React components.

And it wasn't just me.  Another, *very* senior dev, also found his pull requests getting constantly picked apart for arbitrary style "standards" that were defined *nowhere* and couldn't even be confirmed by mirroring the "standards" used in the legacy codebase.

You see, this dev shop couldn't be bothered to deploy any kind of linting file.  They couldn't be bothered to define any of the "rules" that they wanted to see in their code (especially since, even *they* couldn't define their own rules).  All they could do to enforce their "standards" was to arbitrarily pick apart pull requests based on the whims of whomever happened to be commenting on the request at the time.  Of course, these arbitrary (and completely *undefined*) "rules" were also enforced (on the pull requests) by the tech lead.

## The Power of a Linting "Standard"

After this horrific experience, I now have a new, personal "policy" with regard to pull requests.  If you want to pick apart my pull request based solely on code-styling alone, I expect one of the following:

 1. Show me, in your linting configuration file, where my chosen style has broken one of the "rules".  (Of course, if you can't be bothered to actually use any kind linting utility at all, then this entire expectation is null-and-void.)

 3. Explain to me how my chosen coding style will lead to negative repercussions in the application.  (And no, you can't just tell me, "Well... this is the way that we did it *over here*...")

If you can't point to a linter rule that I've broken (which you obviously cannot do if you can't be bothered to use a linting utility at all), and if you can't provide even a nominal explanation of how my chosen style is, in any way, *detrimental*... then I'm not changing the code.  

I'm dead serious.  You can fight me on this, if you like.  You can fire my ass.  I really don't give a shit.  But I'm not going to waste time bull-fighting over some arbitrary code-styling standard that you can't consistently back up with the legacy codebase, or one that's not flagged in the linter.

So you see, in some respects, a linter can be your best friend.  It can serve as a "source of truth" when one dev looks at your pull request and decides that they'd like to see your curly braces on their own separate line, but you've always been putting them on the same line as the loop/if condition.  It can provide you with some sort of backing when one dev wants to see you use an old-style `function` declaration, but you've chosen to use an arrow function.  In other words, the linter helps you to override the pissy little battles that some devs want to engage in when they feel like you haven't coded in their chosen style.

## The Linter Is Not Inviolate

What I just wrote above may sound a bit... *combative*.  As though I'm just going to point to the linter rules and say, "Screw you, bro - it passed the linter, so I'm not changing it."  But that is not my intention at all.  There are many perfectly-valid reasons to "ding" someone's pull request, even if it "passed" the linter.  *Some* of those reasons (but certainly not *all* of them) include:

 1. **Errors in business logic**:  Obviously, the linter won't catch most (or *any*) of the outright flaws in your logic.
 2. **Performance concerns**:  It's easy for something to "pass" the linter - but still be written inefficiently.
 3. **Readability concerns**:  The linter may be "satisfied" with your code - but it may still be downright confusing.  
 4. **Consistency within the code file**:  If my code passed the linter, but it's inconsistent with the code directly above/below it *in the same file*, it's perfectly understandable that someone may ask me to change it.  But if my code is consistent with the rest of the code *in this particular file*, and it passes the linter, and you still want to "ding" me over some arbitrary code-styling concerns, then screw you.  I'm not changing it.

So, in summary, the linter does not "shield" you from the valid concerns of other devs who may have spotted problems in your pull request.  But a rigorous linter can save you time when some pedantic idiot wants you to change your code simply because it doesn't comply with their "in-my-head" standard.
