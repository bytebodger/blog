# The Snobby Demonization of PHP

I'm probably older than you.  My beard is grey.  My experience is long.  I've had the chance to witness many coding _trends_ over the last 20+ years.  I've seen languages come _into vogue_ (looking at you, _Ruby_), and I've seen some of those same languages become _villified_ (looking at you, _ColdFusion_).  So it's been kinda curious to me to see how PHP is currently treated in the marketplace (and has been treated for quite some time).  

## The First "Web" Language

I started throwing up web pages in 1995 (yeah... I'm _that_ old).  My first website was hosted on Geocities (yeah... I'm **_that_** old).  By 1998, I was frustrated by the limitations of the "static" web and I was already looking for other solutions.  Wayyyy back then, your options for creating a truly-dynamic website were _extremely_ limited.  In fact, when I _first_ got into this game, I had only **two** options:  Perl or PHP.  

To be clear, I have a lot of respect for Perl.  It's a fine language.  And, in some respects, it stills fills a valid niche on the "modern" web.  But back in the 90s, Perl could be extremely problematic.  Because back in the 90s, hosting providers hadn't yet figured out how to properly deploy _containerize_, _virtualize_ environments.  (In fact, the first hosting company that I used in 1998 was one of the first hosting companies _on the web_ to offer virtual hosts).  

Back in these "bad ol' days", most of the shared-hosting providers gave you only two options:

1. You could create a completely-static site by uploading your completely-static HTML files into their shared-hosting environment.
1. Or you could create dynamic code, driven by Perl, that would be executed in the `cgi-bin`... _but_, before your code could be deployed, you had to _pay_ the hosting provider an hourly fee to review your code before they would allow it be uploaded to your `cgi-bin` folder.  (This onerous - and _expensive_ - restriction was completely understandable.  Becuase they didn't have the virtualization tools to properly "wall off" your site from the others in the shared host.  So if you wrote some really crappy code, you could destroy not just your own site, but every _other_ site in the shared-host's directory.)

So... with the help of virtualization, PHP became possibly the first programming language that was readily offered _to the masses_ to create dynamic web pages.  Because once virtualization gained a solid foothold, a lotta folks who were signing up for their first virtual hosting environment found that the "server" came preinstalled with PHP (and the embyronic beginnings of MySQL).  

Now I understand that if we are to adhere strictly to literal timelines, Perl preceeded PHP - by a good bit.  But I would stridently argue that PHP was the first "truly-internet" language that fostered widespread adoption of dynamic HTML.  To put it another way:  The first "script kiddies" didn't cut their teeth on Perl.  They got their feet wet in PHP.
