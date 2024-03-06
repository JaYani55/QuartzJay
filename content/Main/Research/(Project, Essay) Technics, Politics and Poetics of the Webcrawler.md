[[webcrawler DevLog]]
[[AI Apaec]]
[[Science & Technology Studies]]

# The Web Crawler

Webcrawlers, also referred to as web spiders or web robots, are foundational to the mechanisms of modern search engines, playing a crucial role in harvesting data from the internet. These tools made their debut in the digital landscape in the early 1990s, with the World Wide Web Worm, developed by Oliver McBryan in March 1994, standing as a notable early example. This pioneering webcrawler endeavored to systematically catalog the web by navigating from link to link, thus mapping the internet in a way that made it searchable and accessible.

For those less familiar with technical jargon, it's useful to conceptualize webcrawlers as diligent explorers of the internet. They methodically visit websites, scan their content, and record the links found within. This process compiles a comprehensive index, akin to a library catalog, allowing search engines like Google and Bing to efficiently locate and retrieve information in response to user queries. The effectiveness and comprehensiveness of webcrawlers are vital for ensuring that search results are both broad-ranging and pertinent, facilitating users in finding the information they need swiftly. These digital navigators are in constant operation, updating their indexes with new data, revising records of existing web pages, and eliminating outdated links.

## Big Data

The intersection of webcrawlers and big data is significant, as webcrawlers play a key role in the accumulation and management of large datasets. Big data encompasses the extensive volumes of information generated daily through various digital activities, including social media use, online transactions, and more. Webcrawlers stand at the forefront of collecting this vast array of data, which is subsequently processed and analyzed for a myriad of purposes, such as market research, trend analysis, and the enhancement of search engine algorithms. The insights derived from the data collected by webcrawlers are used by corporations and state entities for understanding people's behavior, preferences, and sociocultural as well as political trends on the internet. As such, the function of webcrawlers extends beyond search engine optimization to influence diverse areas where big data is crucial for strategic decision-making and development. 

Big data technology has great potential. Both for good and nefarious purposes. Manipulative targeted advertising or political propaganda and disinformation are just two of many examples of big data being used to control populations and mislead individuals.

### What even is data?

However, the key term here is *potential*. Data is an object that generates it's potential in a processual flow through the apparatus that can receive and read it. 
First, data has to be received at all. If no data is received, the data and by extension the data-sending agent might as well not tangibly exist from the perspective of the receiving agent, even though the data objectively exists somewhere out there.

Then, the received data must be readable by the receiving agent. That is, molded into a form that makes 'sense' to the receiving system.

Finally, received data must be analyzed. By combining actual data with past data of the same or a similar category for statistical predictions, for example. This last step is where the potential of data becomes actionable, both for good and bad. But the outcome of analysis also depends on the steps before.

Additionally, any complete analysis will acknowledge that data is nothing exclusive to the digital realm. Consider the breadth of data that is generated every second all around our physical bodies which we don't even realize. Organisms that are so small, they are imperceivable to our eyes, yet they are still there and could make one very sick. And were it not for the invention of the microscope - an apparatus to make microorganisms visible, thus readable and analyzable - we still would be reliant on our superstitious imaginations to protect ourselves from dangerous sicknesses.

To bring my point back to the webcrawler: It is first and foremost a device like the microscope. The webcrawler enables us to perceive data that may be there all along, but is not accessible to us any other way. Maybe because a webpage is not indexed at all and cannot be accessed otherwise. Or because it is just one among so many other webpages that our built-in data processing tools (our brains) are simply unable to keep all this information on it's own.
## **Purpose and Function**

At their core, webcrawlers serve the function of automating the collection of web page data. This automation is crucial for search engines, which rely on up-to-date and comprehensive indexes to provide users with relevant search results. By constantly scanning the web for new content, updates to existing pages, and removing links to pages that are no longer available, webcrawlers ensure that search engine indexes remain accurate and reflective of the current state of the web.

Webcrawlers start their journey from a set of seed URLs, which act as the starting points for their exploration. As they visit these web pages, they identify all the hyperlinks within each page and add them to their list of pages to visit, effectively creating a map of the internet's structure. This process, driven by algorithms that determine which pages to visit and when, allows webcrawlers to cover the vastness of the web systematically.

Critically, the analytical structuring of webpages follows the internal logic of the apparatus that conducts this structuring. In case of Google - or rather Alphabet - a profit-oriented corporation. Webpages are ranked first and foremost by how much they pay directly to google's ad system. But this simple capital for attention model is just the tip of the iceberg. 
## Search Engines

The vast majority of webhosts do not pay Alphabet anything, yet their content is still indexed and displayed by Google. The index ranking is determined by Google's internal and intransparent algorithmic ranking logic as well as Google's requirements for structuring metadata, which is also not always completely transparent and constantly changing. This culminates in webhosts having to do continuous labor for Google and other webcrawlers to structure and design their content in such a way as to gain a favorable ranking position. A whole industry called search engine optimization (SEO) has emerged around this phenomenon.

This indirect power over content creator's behavior is Alphabet's, and other big data companie's, real capital. Much more valuable than the money they receive for advertising. Even though webhosts may run their websites from their own servers, they are still dependant on Google's webcrawler indexing policy in order for them to be perceivable. 
This means that Google is for all practical purposes a platform just like any other social media site or digital distribution system. 
Even though an online shop may run on their own server in the store owner's basement, it's business and existence hinges on the page being indexed by a webcrawler and thus perceivable by potential customers. Were Google the only webcrawler out there, they could extract exorbitant rents on billions of businesses.  
## Platforms and API Practices

More and more, platforms are starting to aggressively capitalize on their data power. Recently, Reddit, a major player in the social media landscape, exemplifies this trend by refining its approach to Application Programming Interfaces (APIs) management. APIs, the conduits that allow disparate software systems to communicate and share data, are pivotal for platforms like Reddit in managing the vast ecosystem of third-party applications, bots, and integrations that contribute to the user experience and platform's growth.

Reddit's journey with APIs highlights the broader shift in platform strategies from open access to more regulated and monetized models. Initially, Reddit's APIs were relatively open, encouraging the development of a wide array of third-party apps, tools, and services that drove engagement and innovation on the platform. However, as the value of data and the importance of controlling how that data is accessed and used became more apparent, Reddit, like many platforms, began to implement more stringent API policies, making actors who want to analyze and repurpose reddit's user-generated content, pay a lot of money for that data. Money, that many institutions and people are unable to afford.

Reddit's example is one among many dangers that platform data monopolism brings as those with power over data may develop a technological ecosystem that relies on said data, only to one day aggressively monetize said data while the users who's business relies on this data, have no choice but to pay.

# Webcrawling DIY

**In order to establish countermeasures against the growing power of platforms, it is neccesary for people to take back the power over the means of data production.**


## Introducing Project Apaec Web Weaver

- Mythological foundations
- Not search engine, framework for webcrawler production
- crawler production through AI
	- Explanation
- Web navigation and Large Action models
	- Selenium IDE
- Contribute by making your crawlers, testing them and uploading them to the datapool
- Roadmap
- Open Source model integration (no OpenAI)
	- Training custom model