---
layout: post
title: Fuss Free Property Analysis in Japan
---

Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml]({{ site.baseurl }}/images/config.png)

[Visualization Tool Here](https://japan-property.herokuapp.com/)


template per portfolio post
	- Motivation
		A seamless investment experience, to instantly spot opportunities and call your broker/agent. Think of comparing computer specs side by side - why can't we do the same for properties, or investments per see?

	- Problem
		Most of websites show the basic filters - set a desired min/max price, yield, and area. This gives you a bunch of listings, true. But it does not tell you exactly which ones you should be looking at, based on your exact investment criteria.

	- Desired Result
		If you are a yield investor, pre-set investment criteria such as your budget, and desired break-even time.

		If you are looking for a home, setting a few locations you like, and seeing how certain metrics compare side-by-side. 


	- Planning
		First principles. We want to see our desired listings in one glance - however, there are multiple ways to look at investments. It is important we define them, isolate what is most important, and start building.

		Criteria:
			a) Break Even Time vs Upfront payment. This is to find which are the investments giving you the best ROI in one glance. Find one as close to the bottom left as possible (but not negative!)
			
			b) Yield: Compare Gross Yield and Price Psm
			
			c) MgmtEfficiency: Compare the efficiency of the building by comparing Maintenance Fee and Potential Annual Rent
			
			d) FloorLevel: Compare if the floor level has a higher price per square metre
			
			e) Walking Time to nearest station vs Price per square metre, or Gross Yield
		
		    Comparing d) and e), we can ask: Do properties command higher yields even if they were nearer to a station? This implies property prices increasing the closer they are to a station, yet rents may or may not be high in relation to the distance.

		    This is the result:

	- Model

		We want to determine "true rental income". This is the cash put into our wallet, after all possible fees, deductions, taxes. This is what makes a rental investment attractive in the first place. Let's dissect this piece by piece.


	- Cashflows from Rent
	
		We need a model to project cashflows of the rent into the future - some listings provide a 'Potential Annual Rent', but this figure may be too high (inflated perhaps). Nevertheless, that is up users to check directly with the agent. For those missing the rent data, we apply a 2.5% yield based on an survey of Japanese and expat investors in Tokyo. The value hovers at 3% for central tokyo, and much less the more central you are (Shibuya, Shinjuku)


	- Operating Costs

		These are....
		Real estate taxes, about 1.8-2% combining the 'national' level real estate and municipal level tax

		Insurance
		Maintenance fees

		Repair Expenses

		Borrow interest

		Realtor management fee

		Property management fee

		Accounting fees


	- Deductibles

		The good news is that as an investor, you can deduct a all/a large portion of the operating costs. Additionally, these numbers can also be deducted:

		Depreciation (of the useful life of a property). Some property types get special treatment (bad, if its regarding a fixed zoning law).

		Special deductions, if your annual rental incme is below
		300000 yen and the value of the property after depreciation is less than 1 million yen.


	- Now that we have identified the major variables, we can write a model to simulate true rental income

		





	- Taxes


	    Interesting. We have a scatterplot, but what are the listings? How do I access the broker's information? Simple. What if we display the results in order of the metric we are concerned about? Rank sorted, this is what it looks like:




	- Where most of time was spent:
		1. Waiting for bokeh to reload. I wish there was a REPL somewhere for a faster iteration


	- Learnings
		1. A set of questions chained into more questions, enabling us to peer closer at the data and find new, interesting insights

		2. Free hosting is cheap - but please use a dedicated server for lookups!


	- Tech:
		Python: pandas, numpy, bokeh
		Cloud: heroku+git


	- Building further
