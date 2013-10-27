# Sustainable Web Design

A growing number of industries are trying to reduce or at least curtail carbon
footprints and energy use. Emissions standards have been set for the
[automotive][1], [construction][2], and even [telecommunications][3] industries. 
Yet the internet’s carbon footprint is growing out of control: a whopping
[830 million tons of CO<sub>2</sub>][4] annually, which is bigger than that of the 
[entire aviation industry][5]. That amount is set to [double by 2020][6].

It is time for web designers to join the cause.

Right now, at least 332 million tons of CO<sub>2</sub> — 
[40 percent of the internet’s total footprint][7] — falls at least partially
under the responsibility of people who make the web. It needn’t be that large, 
but with our rotating carousels, high-res images, and more, we have been 
designing increasingly energy-demanding websites for years, creating monstrous 
HUMVEE sites where we could be just as well served by slender hybrids or, better
yet, bicycles.

The good news is that we have several methods for fixing obese websites and
simultaneously attacking our industry’s carbon footprint — methods that 
conveniently dovetail with good business practice: mobile-ready design demands a
thoughtful and efficient approach to page design, and increasingly sophisticated
web ROI metrics are already driving businesses to pursue faster and lighter 
sites.

Before getting into the nitty-gritty, let’s first look at how to estimate a
website’s footprint.

## What is the web’s carbon footprint?

Just as we refer to a car’s energy usage in terms of miles per gallon, we can
think about website energy usage in terms of the amount of data downloaded. This,
in turn, gives us a framework for guessing the relationship between page size 
and carbon footprint. Unfortunately, working out a website’s carbon footprint is,
on the best of days, tricky and imprecise. Here’s my shot at it:

* A 2008 paper from the [Lawrence Berkeley National Laboratory][8] suggests 
it takes [13kWh][9] to transmit 1GB.
* According to [EPA figures][10], the average U.S. power plant emits 1.2 pounds 
of carbon dioxide equivalent (called [CO<sub>2</sub>e][11]) per kWh produced 
(other countries have higher or lower averages depending on their energy 
policy).
* If we multiply 13kWh by 1.2 pounds, we get 15.6 pounds of CO<sub>2</sub>e — 
and that’s just to transfer 1GB of data.
* If one million users each download a typical page, which now 
[averages 1.4MB][12], that’s a total of 1,367GB of data.
* At 15.6 pounds per gigabyte, that’s more than 10 tons of CO<sub>2</sub>e. 
* Mobile data, with its reliance on [3G/4G][13], is up to five times more 
polluting — 77 pounds CO<sub>2</sub> per gigabyte.
* If a million mobile users on 3G download a 1.4MB page, that’s 1,367GB times 
77 pounds, which totals 52 tons of CO<sub>2</sub>. 

Based on these figures, we can estimate that a site [the size of Tumblr][14],
with 183 million pageviews per day and approximately 10 percent of those from 
mobile, has the potential to be responsible for a staggering 2,600 tons of 
CO<sub>2</sub> daily.

That doesn’t take into account important factors like how much of the data
center’s electricity comes from renewable or fossil fuels or end-user 
electricity usage, both of which could significantly influence the total. But 
these numbers do give us a framework for seeing the relationship between page 
size and carbon footprin-nd make it clear that cutting gigabytes saves 
CO<sub>2</sub>.

The first place to start trimming? In our designs. 

## Reducing CO<sub>2</sub> by tackling page bloat

At 1.4MB, today’s average page is [15 times larger than it was 10 years ago][15], 
primarily due to images (881kB) and script (224kB). Plain old HTML totals 
just 54kB — but when’s the last time you saw [an HTML-only site][16]? This 
average page also makes more than 100 HTTP requests. Whether they fetch a big 
object or a small one, these add up to more delay and [more power wastage][17]. 
The average site is also slow: Alexa’s top 2,000 retailer sites now take an 
average of [more than seven seconds to load][18] — much longer than 
[users consider acceptable][19].

### Budgeting for a lean, mean, and green website

No one intentionally sets out to build a 1.4MB page, but clients often demand
eye-catching images, advanced social features, and plenty of design bells and 
whistles, and that’s pretty much all it takes to get to that size. The best way 
to prevent this kind of obesity is to set a [page size budget][20]: start with a
target page size, and stick to it.

At [MadPow][21], we’ve adopted the page size budget approach to help us chase
better page-load performance, with the holy grail being a page that loads in 
[two seconds or less][22]. Of course, the more page weight we shave off, the
smaller the site’s carbon footprint. To keep track of this, I multiply the page 
size by analytics on user visits to arrive at a rough total for site traffic, 
not forgetting to separate out the more-polluting mobile traffic and account for
caching.

Sticking to the page budget means considering data-weight at each stage of
design:

**Content strategy:** If you are retrofitting a site to reduce page weight, a
quick fix might be to trade higher-weight content for lighter alternatives, like
still pictures instead of video, or text instead of images — so long as the same 
user and business goals are served. Better yet, if you use a 
“[content first][23]” approach, you can bake the size considerations into
your content planning, so as to make content choices that are appropriate for 
the audience and the data budget.

**Interaction design:** The experience definition phase of design is the
perfect time to intercept the more data-hungry site features that threaten a 
page budget. The ubiquitous carousel is a prime offender — a typical one has 
three to six big images, plus the JavaScript needed to make it move, typically 
adding  up to hundreds of kilobytes. The [value of carousels is debatable][24] 
anyway; if you need to make a metrics-driven case for reduction or replacement, 
take the [Brad Frost Carousel Challenge][25]. Other candidates for reappraisal 
include sharing buttons, embedded maps, auto-play video, Flash, ads, and 
syndicated third-party content service-ll of which come with a hefty data 
overhead.

**Visual design:** Images are the largest part of the footprint for most sites
(60 percent on average), and are ripe for data reduction. To start, can you get 
by with fewer images? Many images on the web are also saved in the incorrect 
format, are improperly sized, or are badly optimized. Free services like
[smush.it][26] can optimize your images better than your regular editing tool,
and they’ll do batch processing, too.

Consolidating all the small images on your site by using [CSS sprites][27] or
[web icon fonts][28] will save data and HTTP requests; [pure CSS icons][29]
will be the lightest-weight option, when browser support catches up. And since 
mobile data is so much more polluting than wired data, make sure responsive 
sites use a working responsive images solution. Good optimization could
[shave 72 percent off mobile image weight][30]. 

**Code design:** Front-end optimization is burgeoning with low-hanging fruit:
shrinking scripts, compressing downloads, setting appropriate caching times, and
combining files can all help reduce data overhead and HTTP requests. For a quick
taste, point [Google Page Speed][31] at your site, and it will identify which
techniques could be applied to help speed it up. For a deeper dive, I recommend 
reading “[Web Performance 101][32]”, or [Lara Swanson’s recent ALA article][33]. 

**Green hosting:** Even before you start minimizing your site’s carbon
footprint through design and optimization, you could consider moving to a green 
host. Many of these are powered by renewable energ-articularly in Iceland, 
where data centers have opened to take advantage of cheap geothermal power. 
Green hosting might not be for everyone yet (it can be more expensive, and 
Iceland might be far from your customers), but more local [green hosts][34] are
starting to appear. Some cloud-based services are getting greener, too: Google, 
Apple, and Rackspace get some of their power from renewables, though according 
to Greenpeace, [Amazon Web Services does not][35]. 

**Offsetting the rest:** Even after applying a lean design, optimizing, and
moving to a green web host, your site will still have a carbon footprint. To 
account for that, you can buy an offset, which typically costs $19 per ton,
[depending on the project][36]. Offsetting doesn’t actually take the 
CO<sub>2</sub> out of the atmosphere, and it is a poor substitute for reducing 
emissions. However, many programs have additional benefits, such as funding 
education in the developing world or protecting fragile habitats.

### Persuading people to optimize

Optimizing for lower emissions is tantamount to optimizing for general
performance, so even non-green businesses have several compelling reasons to put
their site on a diet: faster pages make for [happier users][33], especially on
mobile; they [convert better][19] and have [better SEO][37], too.

Adding climate benefit to that list makes an overwhelming case for cutting page
size and data, especially for companies that are already sympathetic to a 
climate case (such as those that have signed the [Climate Declaration][38]).

## The internet as climate hero

Despite its huge carbon footprint, the internet could also be a climate savior. 
The transition of old industries and services to the internet has the 
potential to save [eight billion tons of CO<sub>2</sub> by 2020][39], more than
counterbalancing the projected 1.4 billion ton 2020 internet footprint.

For instance:

As we continue these shifts toward an increasingly online economy, though, 
we’ll also soon be welcoming [five billion new users][40] to the internet. As 
the internet’s overall share of world climate pollution continues to grow, so 
does the climate responsibility of those who architect it. But by building lean 
and clean, we can reduce the damag-nd make happier customers and profitable 
businesses to boot.

Perhaps we’re conditioned to frame environmentally-friendly choices as
sacrifices, but it isn’t so with the web. We can have cleaner, greener websites 
while also making users happier and improving the bottom line. And while the 
problem may be large, as any dietician can tell you, small changes add up. Why 
wouldn’t we get started?

[1]: http://www.epa.gov/otaq/carlabel/index.htm
[2]: http://www.usgbc.org/leed
[3]: http://www.greentouch.org/
[4]: http://www.sciencedaily.com/releases/2013/01/130102140452.htm
[5]: http://www.atag.org/facts-and-figures.html
[6]: http://www.theclimategroup.org/what-we-do/publications/SMART2020-Enabling-the-low-carbon-economy-in-the-information-age/
[7]: http://www.sandvine.com/news/global_broadband_trends.asp
[8]: http://evanmills.lbl.gov/commentary/docs/carbonemissions.pdf
[9]: http://en.wikipedia.org/wiki/Kilowatt_hour
[10]: http://www.epa.gov/cleanenergy/energy-resources/calculator.html
[11]: http://www.woodlandtrust.org.uk/en/why-woods-matter/woods-carbon/Pages/what-does-CO2e-mean.aspx#.Ufv-VWSG0ow
[12]: http://httparchive.org/interesting.php
[13]: http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=6082509&url=http%3A%2F%2Fieeexplore.ieee.org%2Fxpls%2Fabs_all.jsp%3Farnumber%3D6082509
[14]: https://www.quantcast.com/tumblr.com
[15]: http://www.websiteoptimization.com/speed/tweak/average-web-page/
[16]: http://justinjackson.ca/words.html
[17]: http://www.mightybytes.com/blog/entry/http-requests/
[18]: http://www.webperformancetoday.com/2013/03/27/top-ecommerce-sites-are-slower-than-they-were-last-year/
[19]: http://www.websiteoptimization.com/speed/tweak/psychology-web-performance/
[20]: http://clearleft.com/thinks/responsivedesignonabudget/
[21]: http://madpow.com
[22]: http://blogs.keynote.com/the_watch/2009/09/the-new-2-second-website-rule.html
[23]: http://www.lukew.com/ff/entry.asp?1598
[24]: http://www.nngroup.com/articles/auto-forwarding/
[25]: http://bradfrostweb.com/blog/post/carousels/
[26]: http://www.smushit.com/ysmush.it/
[27]: http://css-tricks.com/css-sprites/
[28]: http://css-tricks.com/flat-icons-icon-fonts/
[29]: http://nicolasgallagher.com/pure-css-gui-icons/demo/
[30]: http://timkadlec.com/2013/06/why-we-need-responsive-images/
[31]: https://developers.google.com/speed/pagespeed/
[32]: http://www.webperformancetoday.com/2013/01/31/web-performance-101-developers/
[33]: http://alistapart.com/article/improving-ux-through-front-end-performance
[34]: http://sustainablevirtualdesign.wordpress.com/green-hosting/
[35]: http://www.greenpeace.org/usa/en/campaigns/global-warming-and-energy/cleanourcloud/greenaws/
[36]: http://www.offsetconsumer.org/providers/
[37]: http://googlewebmastercentral.blogspot.com/2010/04/using-site-speed-in-web-search-ranking.html
[38]: http://www.ceres.org/bicep/climate-declaration
[39]: http://www.smart2020.org/publications/
[40]: http://www.cnn.com/2013/04/15/tech/web/eric-schmidt-internet