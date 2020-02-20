# The Snobby Demonization of PHP

I'm probably older than you.  My beard is grey.  My experience is long.  I've had the chance to witness many coding _trends_ over the last 20+ years.  I've seen languages come _into vogue_ (looking at you, _Ruby_), and I've seen some of those same languages become _villified_ (looking at you, _ColdFusion_).  So it's been kinda curious to me to see how PHP is currently treated in the marketplace (and has been treated for quite some time).  

## The First "Web" Language

I started throwing up web pages in 1995 (yeah... I'm _that_ old).  My first website was hosted on Geocities (yeah... I'm **_that_** old).  By 1998, I was frustrated by the limitations of the "static" web and I was already looking for other solutions.  Wayyyy back then, your options for creating a truly-dynamic website were _extremely_ limited.  In fact, when I _first_ got into this game, I had only **two** options:  Perl or PHP.  

To be clear, I have a lot of respect for Perl.  It's a fine language.  And, in some respects, it stills fills a valid niche on the "modern" web.  But back in the 90s, Perl could be extremely problematic.  Because back in the 90s, hosting providers hadn't yet figured out how to properly deploy _containerize_, _virtualize_ environments.  (In fact, the first hosting company that I used in 1998 was one of the first hosting companies _on the web_ to offer virtual hosts).  

Back in these "bad ol' days", most of the shared-hosting providers gave you only two options:

1. You could create a completely-static site by uploading your completely-static HTML files into their shared-hosting environment.
1. Or you could create dynamic code, driven by Perl, that would be executed in the `cgi-bin`... _but_, before your code could be deployed, you had to _pay_ the hosting provider an hourly fee to review your code before they would allow it be uploaded to your `cgi-bin` folder.  (This onerous - and _expensive_ - restriction was completely understandable.  Becuase they didn't have the virtualization tools to properly "wall off" your site from the others in the shared host.  So if you wrote some really crappy code, you could destroy not just your own site, but every _other_ site in the shared-host's directory.)

So... with the help of virtualization, PHP became possibly the first programming language that was readily offered _to the masses_ to create dynamic web pages.  Because once virtualization gained a solid foothold, a lotta folks who were signing up for their first virtual hosting environment found that the "server" came preinstalled with PHP (and the embyronic beginnings of MySQL).  

Now I understand that if we're to adhere strictly to literal timelines, Perl preceeded PHP - by a good bit.  But I would stridently argue that PHP was the first "truly-internet" language that fostered widespread adoption of dynamic HTML.  To put it another way:  The first "script kiddies" didn't cut their teeth on Perl.  They got their feet wet in PHP.

So I dove in.  _Somehow_... I made it work.  I wrote a _crap-ton_ of thoroughly-embarrasing code.  But somehow, some way, I managed to make it all "work" at the time.

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

1. I was interviewing for a React position and I was doing a screensharing coding test with two of the company's senior devs observing my actions.  When they gave me the instructions, I launched my IDE - JetBrains' PHPStorm.  One of their devs immediately exclaimed, "_PHP_ Storm???"  He sounded like I'd just proposed scrawling the answers to their coding test directly on my monitors - in feces.<br/><br/>His exclamaition was quite silly.  I wasn't going to _write_ any of the answers to their coding test in PHP.  I wasn't going to _run_ any of my completed code in PHP.  I was only using an IDE that had "PHP" _in the name_.  And this was enough to give this guy the creeps.  (If you're wondering: I pay for the full JetBrains suite and I actually _could_ have opened _Web_ storm, which presumably woulda made this guy much happier.  But I didn't have Webstorm configured locally and when you're in an interview, you don't have much time.)<br/><br/>They did not offer me a job...<br/><br/>
1. I was completing a coding assignment with all kindsa hairy requirements - far more than you would normally find in a coding assignment of "acceptable" length.  Nevertheless, I _did_ the entire assignment.  It had a React frontend end, with authentication, and drag-n-drop, and GraphQL, and session management, and... a whole buncha crap that was wayyyyy more than any reasonable employer should ever ask for a coding assessment.  But I did it anyway.  I met _every_ requirement.<br/><br/>Some time after I submitted the code, I learned that they didn't like my submission because I built the backend API... in PHP.  Their requirements never said which tools should be used to build the API.  They didn't say that I _must_ use any particular tech stack.  They didn't say that I _couldn't_ use PHP.  They just said that I had to include a GraphQL API.  And I _did_ that... in PHP.  I did it in PHP because it was the fastest, easiest way to spin up an API with my local tools.  I did it in PHP because I had already sunk a huge amount of time into the frontend functionality and I just needed a backend _that worked_.  Nevertheless... they didn't like the fact that I'd used PHP to build the backend of this silly demo app.<br/><br/>They did not offer me a job...<br/><br/>

If this sounds like some whiny defense of the language, believe me, it's not.  
