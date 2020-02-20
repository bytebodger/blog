
# The Snobby Demonization of PHP

I'm probably older than you.  My beard is grey.  My experience is long.  I've had the chance to witness many coding _trends_ over the last 20+ years.  I've seen languages come _into vogue_ (looking at you, _Ruby_), and I've seen some of those same languages become _vilified_ (looking at you, _ColdFusion_).  So it's been kinda curious to me to see how PHP is currently treated in the marketplace (and has been treated for quite some time).  

## The First "Web" Language

I started throwing up web pages in 1995 (yeah... I'm _that_ old).  My first website was hosted on Geocities (yeah... I'm **_that_** old).  By 1998, I was frustrated by the limitations of the "static" web and I was already looking for other solutions.  Wayyyy back then, your options for creating a truly-dynamic website were _extremely_ limited.  In fact, when I _first_ got into this game, I had only **two** options:  Perl or PHP.  

To be clear, I have a lot of respect for Perl.  It's a fine language.  And, in some respects, it stills fills a valid niche on the "modern" web.  But back in the 90s, Perl could be extremely problematic.  Because back in the 90s, hosting providers hadn't yet figured out how to properly deploy _containerize_, _virtualize_ environments.  (In fact, the first hosting company that I used in 1998 was one of the first hosting companies _on the web_ to offer virtual hosts).  

Back in these "bad ol' days", most of the shared-hosting providers gave you only two options:

1. You could create a completely-static site by uploading your completely-static HTML files into their shared-hosting environment.
1. Or you could create dynamic code, driven by Perl, that would be executed in the `cgi-bin`... _but_, before your code could be deployed, you had to _pay_ the hosting provider an hourly fee to review your code before they would allow it be uploaded to your `cgi-bin` folder.  (This onerous - and _expensive_ - restriction was completely understandable.  Because they didn't have the virtualization tools to properly "wall off" your site from the others in the shared host.  So if you wrote some really crappy code, you could destroy not just your own site, but every _other_ site in the shared-host's directory.)

So... with the help of virtualization, PHP became possibly the first programming language that was readily offered _to the masses_ to create dynamic web pages.  Because once virtualization gained a solid foothold, a lotta folks who were signing up for their first virtual hosting environment found that the "server" came preinstalled with PHP (and the embryonic beginnings of MySQL).  

Now I understand that if we're to adhere strictly to literal timelines, Perl preceded PHP - by a good bit.  But I would stridently argue that PHP was the first "truly-internet" language that fostered widespread adoption of dynamic HTML.  To put it another way:  The first "script kiddies" didn't cut their teeth on Perl.  They got their feet wet in PHP.

So I dove in.  _Somehow_... I made it work.  I wrote a _crap-ton_ of thoroughly-embarrassing code.  But somehow, some way, I managed to make it all "work" at the time.

## Evolving Past PHP

Of course, the interwebs constantly evolve.  And as they did, PHP became more of an embarrassing side-note for any of the "real" programmers.  We got JSP (which is, honestly, a complete shit-storm in its own right).  We got JavaScript - but back then, JavaScript couldn't really _do_ anything useful.  We got other server-side scripting tools, like (the forever-dying language of) ColdFusion.  Eventually, we even advanced to the point where we could write "real" enterprise-level apps, first in Java - then in C# - that would make the haughty OOP crowd nod in approval.  But along the way, a _funny_ thing happened.  PHP never really went _away_.  It just kinda... lingered in the amateurish shadows - refusing to die, but refusing to properly evolve.

Even the largest PHP fan will probably admit that its resilience is, in large part, attributable to WordPress.  The WordPress team chose PHP - and, in turn, that fortuitous decision solidified a permanent place for PHP in web-development lore.  Whether any of the "real" programmers wanna admit it or not.  

We've all seen the web statistics to back it up.  At any given time, there's an insanely-disproportionate number of public sites that are running on PHP.  Of course, those "in the know" understand that those statistics are massively skewed by the bloggers and other amateurs' sites which are, _technically_, running on PHP - even if the sites' webmasters (yeah... remember _that_ term?) couldn't write a line of PHP to save their life.

## Personal Evolution

Given my (long, greybeard) history, you can probably guess that _I too_ have "evolved" beyond PHP.  I moved to ColdFusion/MS-SQL, then to Java/Oracle, then to ASP/C#, then to jQuery/Knockout/Angular/React.  Like most people who are in the "long game" of app-dev, I've managed to get my grimy fingers into a stunning array of technologies - even if I'm still struggling to master _any_ of them.  

But I never really _quit_ PHP.  It's been installed on my local machines for decades.  I've rarely ever been _paid_ to write PHP - because, let's face it, most of the PHP jobs out there just don't pay.  (Do I want to be your WordPress Administrator for $50k/year??  Umm... no.)  But it's been an invaluable tool for those (many) times when I want to write some quick coding utility at home.  Even as I've moved ever deeper into frontend development, I find myself often reaching for PHP because it's a quick-and-easy way to spin up a backend API.

## The Shaming of PHP

Even though I still write some PHP in my spare time, I've known for a _loooong_ time that being a PHP dev is usually best kept as a type of "dirty little secret".  You can do PHP, but you should only do it when you're at home.  Alone.  With all the blinds closed.  And for godsake, no matter what you do, never _tell_ anyone that you actually write (and - egads! - _enjoy_) PHP.  It's like the fetish porn of software development.  There are plenty of people out there doing it, but if you wanna be accepted and respected by the "real" developers out there, you'd best keep that shit to yourself.

This point was driven home to me recently during two incidents when I was involved in a job search.  

1. I was interviewing for a React position and I was doing a screensharing coding test with two of the company's senior devs observing my actions.  When they gave me the instructions, I launched my IDE - JetBrains' PHPStorm.  One of their devs immediately exclaimed, "_PHP_ Storm???"  He sounded like I'd just proposed scrawling the answers to their coding test directly on my monitors - in feces.<br/><br/>His exclamation was quite silly.  I wasn't going to _write_ any of the answers to their coding test in PHP.  I wasn't going to _run_ any of my completed code in PHP.  I was only using an IDE that had "PHP" _in the name_.  And this was enough to give this guy the creeps.  (If you're wondering: I pay for the full JetBrains suite and I actually _could_ have opened _Web_ storm, which presumably woulda made this guy much happier.  But I didn't have Webstorm configured locally and when you're in an interview, you don't have much time.)<br/><br/>They did not offer me a job...<br/><br/>
1. I was completing a coding assignment with all kindsa hairy requirements - far more than you would normally find in a coding assignment of "acceptable" length.  Nevertheless, I _did_ the entire assignment.  It had a React frontend end, with authentication, and drag-n-drop, and GraphQL, and session management, and... a whole buncha crap that was wayyyyy more than any reasonable employer should ever ask for a coding assessment.  But I did it anyway.  I met _every_ requirement.<br/><br/>Some time after I submitted the code, I learned that they didn't like my submission because I built the backend API... in PHP.  Their requirements never said which tools should be used to build the API.  They didn't say that I _must_ use any particular tech stack.  They didn't say that I _couldn't_ use PHP.  They just said that I had to include a GraphQL API.  And I _did_ that... in PHP.  I did it in PHP because it was the fastest, easiest way to spin up an API with my local tools.  I did it in PHP because I had already sunk a huge amount of time into the frontend functionality and I just needed a backend _that worked_.  Nevertheless... they didn't like the fact that I'd used PHP to build the backend of this silly demo app.<br/><br/>They did not offer me a job...

Not that any of this really shocks me much.  I've already known, for many _years_, that when I'm talking to other senior software engineers - in "real" jobs - that even _mentioning_ PHP is a liability.  You can be having a great conversation with a bunch of serious coders.  And you can all be getting along fabulously.  But if you let "PHP" escape from your lips, everyone gives you that awkward look like you just dropped an off-color joke into the mix.  

## A (Deservedly) Bad Reputation

If this sounds like some whiny defense of the language, believe me, it's not.  I've been around PHP long enough to sorta regard it as my kid.  My ugly overweight kid who never did much in school, has been working dead-end jobs for years, and has had numerous run-ins with the law.  You still love your kid.  You still hope for nothing but the best for your kid.  But after a certain time, even the most devout parent's gotta see when their kid has some... _problems_.  

The 3.x versions of PHP were too experimental to critique.  And most coders today have never actually _seen_ a 3.x installation of PHP.

The 4.x versions were, in retrospect, a disaster.  Much of the language's scorn arises from the 4.x versions.  Magic globals, crappy database constructs, conflicting libraries, inconsistent syntax.  All the warts were right there in the open for anyone to see.

The 5.x versions did, incrementally, improve the language.  Granted, the road through the 5.x versions was _far too long_, and PHP's Release Candidate community seemed to bog down for quite a while.  But they did, eventually, get through that wilderness.

The 7.x versions are... pretty damn good.  There.  I said it.  You can laugh at me if you want.  Have they fixed _every_ potential headache in the language??  Of course not.  But what language doesn't have at least _some_ quirks that drive its developers nuts?  But overall, I really kinda... _enjoy_ writing backend functionality in PHP 7.x.  

Of course, many of the knocks against PHP don't come directly from the language itself.  They come from the _community_ that's associated with its use.  Specifically, many of PHP's haters have been jaded by the droves of hobbyists and dabblers that come along with WordPress.  WordPress itself can be a Coding Beast From Hell.  And then when you add in all the weekend warriors who are mucking it up because they're just trying to put up a basic site for their kid's soccer league?  Well... you can run into some really amateur stuff.

## The Irony of the JavaScript Code Shamers

There will always be people who (irrationally) love _their_ chosen language and (irrationally) hate _your_ chosen language.  I get that.  It's an attitude that's as old as programming itself.  But I can't help but notice the particular irony of _JavaScript programmers_ looking down their noses at PHP.  

For the first 10+ years of JavaScript's existence, it was little more than a programming _toy_.  There wasn't much of value that you could actually _do_ with it.  And even when you figured out how to create something meaningful from it, most of the "real" coders dismissed it entirely.  For many years, being a "JavaScript programmer" was seen as a contradiction in terms, like "jumbo shrimp" or "compassionate conservative".  

So it's quite rich, nowadays, to see the blatant snobbery with which many JS devs heap scorn upon PHP.  They obviously have no sense of coding history - or irony.  Quite frankly, I don't think they care.  The JS community has, over the last decade, become increasingly elitist, and this can really be highlighted when you observe their overall attitude toward PHP.  Few of the JS devs I've met fully grasp the incongruity at play when the JS community tries to treat PHP like PHP is somehow "lesser", while acting as though JS is somehow "greater".

## Coding in the Shadows

So what's the "answer" for PHP devs?  Sadly, I don't know if there is much of one.  Trying to shift the attitudes of many _thousands_ of JS/Java/C#/Python/etc devs is probably impossible.  Any chance to radically improve the language's "social standing" probably passed a long time ago.  Not that I'm telling you to _abandon_ PHP.  It's a great tool (for certain jobs).  There's nothing "wrong" with having that tool in your tool belt.  But... you might to make sure that it's tucked deep into a pocket where no one else is likely to catch you with it.
