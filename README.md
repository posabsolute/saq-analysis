#SAQ.COM UX overview, Why & how to fix it.

## Prologue


There are some things in this world you have no choice to live with, for us Quebec citizens, the SAQ is one of them. You see, in Quebec selling alcohol is illegal, only our government can do that. As you can guess, since they are the only one selling imported wines and hard liquors, they have all the market, meaning they don't necessary have to care, you will buy their products either way, guaranteed.

Just to put you in context, they pocketed in 2011 one billion (you heard that right) in profit. You would think that with that money they would have a decent website... Well you would have guessed wrong, the SAQ.com is a combination of bad user interaction, bad design, and refreshed sections that looks  ok but does not fit with the overall brand.

The website would (obviously) need te be scraped & rebuild, but in this guide I will only highlight the what the saq does worst and how to at least fix it fast. 

![ISAQ](http://i.imgur.com/ja94I.png)

### How did we got there?

The saq.com has a long history and it is pretty hard to make sense of it all, it was first managed by Cognicase at a cost of 7,6 millions from 2000 to 2006. Why all that money? Well they integrated e-commerce. In 2006 Nurun got the contract for a whooping 2,6 millions. The goal? Make the online inventory in real time. That's a lot of bacon, but hey at the very least the site still works. 

While the SAQ is in the public domain and we do have access to their annual reports, I can only guess what is happening internally that make them so change resistant. But like any big organization (more than 5000 employes) changes is necessary slow. Having work on a 1 million contract I can picture easily the endless lines of directors, project managers & vice presidents meetings just to change a wording on the website.

![ISAQ](http://i.imgur.com/Zzmc6.png)


It is also mind boggling that a company that probably got a graphic identity standards book of more than 100 pages got content like [http://www.saq.com/webapp/wcs/stores/servlet/CatalogSearchResultView?searchType=700&viewTaskName=NouvelArrivageResultView&langId=-2&storeId=10001&catalogId=10001](this page) that are totally off their general brand (maybe in that case "La Presse" paid for it since it match their branding better than the SAQ.)

### There is hope

Their website is surprisingly nothing like their brick and mortar store. There they innovate a lot faster implementing new concepts each year. When you enter an SAQ store you feel nothing like entering a creepy place, it is always hip and cool.

The SAQ introduced in 2009 the taster profile. Basically it revolve around wine types associated to a color that they stick on the bottle.Nothing too fancy, still the promotion worked and sold 14% more wine initially compared to other campaigns. Profiles are illustrated below (french sorry).

![Pastilles](http://www.touchephd.com/blog/wp-content/uploads/2009/10/SAQ-Pastilles-350x287.jpg)

They also successfully launched an iPhone and Android native application, it is pretty good with food matching suggestions for your romantic dinners, wines store specific emplacement on a map, nice one big picture promotions, and even more.

![Iphone SAQ APP](http://www.saq.com/wcsstore/saqcom/images_produits/divers/app_mobile/scrn_iti_fr.jpg)


### What about an api

A SAQ api would be out of this world, we would probably have very nice apps around it, and with a bit of luck a cleaner alternative website too. Unfortunately there is little insensitive for the SAQ to develop one. Like I said, they control the entire market, there is not much to gain from driving out customers from the official website and apps. They will also probably never offer a referral programs (not even sure that would be legal) which would greatly cut the enthusiasts of such api.

There is of course the good old web scraping technic, I'm sure a couple of guys already did it. Problem is you will never be able to have a popular project with that content. You are going to be shutdown at the minute they know about it.

### Let's dive into it

I divided this guide in each important section where I think the website is severely lacking clarity and where the experience is severly broken. I will admit, the saq.com is an easy target, and it is also exactly why I chose it.

I tried to keep it simple, the solutions here involve some work but never an actual rewrite. The idea is to get clues on possible solutions to implements to achieve a better experience.


## Search Form

![Current search form](http://i.imgur.com/yMKOn.png)

The SAQ search form is certainly a weird one, it is comprised of one search field with 5 different select to help you categorize your search, which sound like a not to shabby idea at first glance. 

One thing will probably jump right in your face looking at the screenshot above, not only the selects look downright weird and unaligned, they also do not have the expected behavior. Once you popup that select option you will be greeted by a weird javascript popover. I can see why they needed that drilled down functionality but not like this.

Here a small list that represent the general problems with that form.

### Issues

* The Text is too small, specially on hi res screens, my father would not be able to read what is written there (it is a global problem too)
* The select box are not aligned correctly and does not look like a native browser element.
* When you click on the select to drill down your search you are greeted by a weird popup that align itself to the left instead of down (like the arrow cue tell you it will be)
* Dropdowns do not adapt depending on other choices, for example, whiskies starts at 40$ but the price dropdown stop exactly there, 40+
* There are 2 buttons Search which can cause confusion and lead you to think you can't do a text search & a drilled down search (You actually can't but that's just stupid).


### Recommendation: Simplify the flow

We can safely assume that most people won't use the 5 selects and that it create more noise than it help, specially in that crowded space. We also do not need 2 search buttons. Let's remove the most unsused parameters, and if needed he will be able to use a more advanced search in the search results page.


![Simplified Search flow](http://i.imgur.com/FQA7g.png)

The example above shows the recommendations:

* Added icons to create visual cues associalted with the options (reused in the search result)
* Remove most unused options
* 1 global search button
* Changed arrow orientation to reflect real behavior

#### Recommendation: Let the user input what he wants

We cannot list every regions imaginable of wines in the js popover, to that end, as an addition of the popover, let the user define himself what he wants (just use a normal text input). That way wine experts  can easily refine their search without harming the experience of the normal customers.

### Recommendation: Add a smart autocomplete

When done right, an autocomplete can really help users define precisely their search. Obviously we need to show wines, but don't forget adding brands identity. An example would be looking for Johnny walker, we shoud have 2 clearly defined separation in the autocomplete for actual Johnny walkers bottle bot also for general brands that match it.

![Smart Autocomplete](http://i.imgur.com/7m18t.png)

The information shown is subject to user testing, understanding what users are looking for is essential when executing an autocomplete.


### Recommendation: Make clearer the popover Select Options

The popover themselves are not bad. Adjust the text to be bigger and have a clearer definition of sub-tree items (change colours, or font size).


## The products page

The products page should be one of the website core. When you click on that page you should be teased about new products, even better suggest  wines from what users have look for before. 

Instead you are greated with this boring page:

![ISAQ](http://i.imgur.com/GbBhG.jpg)



### Issue: Online products is selected by default

When you are in the products page, only the *online* inventory shows up in your result with the default setting. This is the only place, in all the website where this behaviour happen.

It is even hard to realize taht this option is on, and for good reasons, it blends very well with the page. The online button at the top is not even in a selected behaviour, it's exactly the same as the outlet products button.

![ISAQ](http://i.imgur.com/ahhwR.png)

That creates an issue where you can't shop for both at the same time, it"s either online or outlet. We need to make this clearer, we  need to remove the default selected option & add a third option, *All Products*.

### Recommendations

Frankly this page is the hardest to improve in my mind, you don't want to overcrowd the space, you want the user to find what he wants faster. One thing for sure, like the  js popover the text is too small and the definition of sub-tree items should be clearer.

Beside that since this is just an oveview it would go beyont the scope of this documents to recommends a totally different approach for this page.


## Search Results

The search results page is where users will spend most of their time on. Like the search form, it is somewhat usable, but is clearly missing finesse. It looks like an internal product inventory application (which is probably not far from the truth).

![ISAQ] (http://i.imgur.com/l0bvs.png)


### Issue: Advanced options are not helping

If you drill in one category, like white wine, you will be greeted with a link that is in fact a changeable option. That Changeable option only apply to the Region and sub region you are looking for (not the price or taste profile). 

It's also interesting to note that your last drill cannot be changed as you are now greeted by a breadcrumb with no link in it.

![Search results] (http://i.imgur.com/ByH5h.png)

If we had some nice permalinks like ( /whitewine/bordeaux/ ) there would certainly have a great use, but in it's current form it is completely inappropriate. Also puzzling is the meal wine category that appear here, it seems to appear by magic and there is no way to remove it.


### Recommendation: Better present the result items

![Search Prototype] (http://i.imgur.com/KBBCR.png)

Key ideas :

* Always let the advanced search available. That will allows the user to have access faster to what he is looking like. Some options will have to reset other options like changing the region will obviously default the sub region.
* Add visual cues (like icons) on properties that differentiate each wine (taste profile, region, etc).
* Make links clearer, buy and outlet are pretty bad wording choice, "buy" does not mean "buy online" for most people, so we need to make this clearer.



### Recommendation: Show the complete taste profile
	
For some reasons they decided to only show the colour of the profile taste. I guess the idea was I already know the taste profile I like, but personally I never remember those colours meaning.

### Recommendation: Add notes & experts reviews

Expert reviews is the one of the most helpful thing that can help the average user  choose a wine. If a wine has a score of 50, clearly most people will not buy it, buying the one with a score of 75 instead for the same price. Contact experts, compile their notes, links to their blog reviews, other websites has now been doing this for some time.

While adding external reviews this would be a big project itself, I think it would also be one of the most beneficial addition to the site. It's hard to find notes for wines you want because if you go on other websites, chances are the wine they just review the SAQ do not carry it.

Imagine having all François Chartier notes and reviews right at your fingertip in the results page. Awesome.

### Recommendation: SAQ suggested pick

If you are just browsing through wines without a precise pick you will probably be interested by suggestions from the SAQ. It can help user obtain the information they want quicker (a good wine for tonight).  

## Product Result Page

Beside being not very appealing visually I find this page well construct for the most part. Information is clear, direct online availability is also a nice touch.

![ISAQ] (http://i.imgur.com/ohC5C.png)


### Recommendation: Remove anchored links from details

For example when you click on wine and food pairing your browser jump to that line. You loose for a second the website and you do not even notice that the section you clicked on is now open.

### Recommendation: Add reviews link 

Already explained in the result page. Reviews can  be added to the product page itself with a selection of the most recent.

### Recommendation: Availability near you

Using HTML5 Geo-location, ip, or even the user address if he is logged on, it would be a nice idea to add availability near you with 2 or 3 outlets that got the product.

## Conclusions

Obviously it does not take a genius to see that the saq.com needs a complete makeover, The design is very outdated, the text is very small & the interface should be consistent all this to help the user to accomplish it's goal without getting in the way.

This conclude my small analyze of SAQ product and search pages, I could go even further in the matter but I think it compile the most frustrating elements of the website and how to fix them without created a complete new interface. It's been a fun way to vent my frustration at the site and hope it can be useful to someone, somewhere at the SAQ!
