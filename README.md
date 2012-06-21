#SAQ.COM Analysis, Why & how to fix it.

## Prologue


There are some things in this world you have no choice to lives with, for us people from the Quebec province, the SAQ is one of those. You see in Quebec selling alchool is illegal for normal citizen, only the government can do that. As you can guess, since they are the only one selling imported wines and hard liquors, they have all the market, meaning they don't have to care, you will buy their product either way, garanteed.

Just to put you in context, they pocketed in 2011 1 billion (you heard that right) in profit. You would think that with that money they would hav a decent website... Well you would have guessed wrong, saq.com is a combination of bad user interaction, bad design, and refreshed sections that looks ok but does not fit with the overral design.


### How did we got there?

While the SAQ is public and we even have access to their annual reports, I can only guess what is hapenning internally that make them so change resistant. But like any big organization (more than 5000 employes) changes is slow, I can certainly picture the endless lines of directors, project managers & vice presidents meetings just to change a wording on the website.

It is also mind boggling that a company that probably got a graphic norms book of more than 100 pages got content like [http://www.saq.com/webapp/wcs/stores/servlet/CatalogSearchResultView?searchType=700&viewTaskName=NouvelArrivageResultView&langId=-2&storeId=10001&catalogId=10001](this page) that are totally off their general brand (maybe in that case lapresse paid for it since it match their branding better than the one from SAQ.)

Their website is surpringinly nothing like their brick and mortar store. There they innovate a lot faster implementing new concepts each year. When you enter an SAQ store you feel nothing like entering a creppy place, it is always hip and cool.

SAQ also introduced in 2009 the taster profile. Basically it revolve around wine types associated to a color that they stick on the bottle.Nothing too fancy, still the promotion worked and sold 14% more wine initialy compared to other compaigns they did. Profiles are illustrated below (french sorry).

![Pastilles](http://www.touchephd.com/blog/wp-content/uploads/2009/10/SAQ-Pastilles-350x287.jpg)

### They also got it right elsewhere

They "recently" lanched an iPhone and Android native application, it si pretty good with food matching suggestions.
![Iphone SAQ APP](http://www.saq.com/wcsstore/saqcom/images_produits/divers/app_mobile/scrn_iti_fr.jpg)

### Let's dive in

I divided this guide in each important section where I think the website is severely lacking clarity and good user experience, by importance order.



## Search Form

The SAQ search form is certainly a weird one, it is comprised of one search field with 5 different select tp help you categorise your search, which sound like a not to shabby idea at first glance. 

One thing will probably jump right in your face looking at the screenshot below, not only the selects look downright weird and unaligned, they also do not have the expected behavior. Once you popup that select option you will be greeted by a weird javascript popover. I can see why they needed that drilled down functionality but not like this.

Before going in details on each problem let's try to make a small list that represent evrything that is wrong with that form.

* The Text is too small, specially on hi res screens, my father would not be able to read what is written there (it is a global problem too)
* The select box are not aligned correctly and does not look like a native browser element.
* When you click on the select to drill down your search you are greeted by a weird popup that align itself to the left instead of down (like the arrow cue tell you it will be)
* Dropdowns do not adapt depending on other choices, for example, whiskies starts at 40$ but the price dropdown stop exactly there, 40+
* There are 2 buttons Search which can cause confusion and lead you to think you can't do a text search & a drilled down search (You actually can't but that's just stupid).

How do we change that? interestingly I think the housing industry & small ads got search right, and there is a lot of similar problem where we can draw lots of knowledge.


### Add a smart autocomplete

When done right, an autocomplete can really help our users define precisely his search. Obviously we need to show wines, but don't forget adding brands identity. An example would be looking for Jonny walker, we shoud have 2 clearly defined separtion in the autocomplete for actual Jonny walkers bottle bot also for general brands that match it.

Obviously bottles must have priorities, but chance are, if the guy is looking for Johnny Walker he wants the full lists and is not sure which one he is looking for. Having 2 brands at the top plus 5 to 10 bottles below could be a ncie idea.



### Popover Select Options

The first thing we want is to change that select for something more representative


#### Let the user define their terms

The price selection range is ridiculous, while it certinaly apply to wines in general, it is out of touch with hard liquors. Adding more options there is a ncecessity but even better, let the user define it itself as an advanced feature.



#### Simplify

When you have 5 selects, I think we can safely assume that most people wont use all of them and that it create more noise tha it help peoples.



## Search Result



