

## **Critical Infrastructure Needs to be Cyber-proof**

There has been an increasing trend of critical infrastructure (emergency call centers, grid line controls, power plants, etc.) migrating service operations to the cloud. This migration leaves certain infrastructures vulnerable to cyberattacks. A[ European Union study](https://ec.europa.eu/echo/sites/default/files/recipe_guidelines.pdf) highlights the need for a more organized approach toward securing critical infrastructure, similar to what is seen in technology companies. The report shows that a systemic approach to protecting institutions and organizations critical to a larger population must be considered from the ideation phase. Cybersecurity considerations thus become operational requirements – it is a crucial part of any business or endeavor.

With cloud adoption rising, the associated risk of being attacked is also increasing. There are many types of issues in software that can be exploited by hackers – as developer tooling and experience rises, so does the number of new developers and hackers. Armed with knowledge of which attack is most popular, we can better prepare for a security incident.

The list of top ten important vulnerabilities for 2021 is available on the[ OWASP website](https://owasp.org/Top10/A00_2021_Introduction/), along with in-depth analysis and context behind each of the vulnerabilities depicted below and the methodology behind how this list was calculated.

![alt_text](images/image1.png "image_tooltip")

Fig 1.[ OWASP](https://owasp.org/Top10/A00_2021_Introduction/) Top 10 Vulnerabilities Shift 2017 to 2021


### **Consequences for Poor Cybersecurity**

With the need to protect critical infrastructure comes the need to immunize infrastructure (or at least have a backup plan) against the most typical vulnerabilities. Broken access control can lead to disaster scenarios such as[ losing control over nuclear reactors](https://www.bbc.com/news/world-middle-east-11414483) or[ leaking](https://outpost24.com/blog/top-10-of-the-world-biggest-cyberattacks) millions of credit card information or a billion users’ passwords online. All these attacks exploited one or more of the known, popular vulnerabilities.

In this introductory article, we will take a look at some of the more popular and recently talked about attacks from around the world. First, we will review the recent attack mitigated by[ Azure Cloud](https://azure.microsoft.com/en-us/blog/business-as-usual-for-azure-customers-despite-24-tbps-ddos-attack/). We’ll follow with another[ Microsoft company](https://www.csoonline.com/article/2130877/the-biggest-data-breaches-of-the-21st-century.html), LinkedIn, which fell victim to an attack that leaked[ 700 million users’ data](https://www.forbes.com/sites/leemathews/2021/06/29/details-on-700-million-linkedin-users-for-sale-on-notorious-hacking-forum/), only two months after a breach that leaked 500 million users.

We will then examine a leak of 1.1 billion users’ information from[ Alibaba](https://www.bloomberg.com/news/articles/2021-06-16/alibaba-victim-of-huge-data-leak-as-china-tightens-security), where a malicious actor was scraping the platform’s data containing sensitive information over a period of eight months. The last piece will show an infrastructure attack on npm (Node Package Manager) by publishing a package with[ crypto-mining malware](https://www.bloomberg.com/news/articles/2021-06-16/alibaba-victim-of-huge-data-leak-as-china-tightens-security).

The need to protect critical systems will become more prevalent in the systems that engineers create. Consider the current possibility: an attack on your local home server running your IoT doorbells can lock you out of your home; imagine what can happen if a nuclear power plant is hacked.

We hope to never know.


### **Azure Cloud Mitigates 2.4 Tbps DDoS Attack**

![alt_text](images/image2.png "image_tooltip")


Fig 2. UDP bandwidth mitigation timeframe by[ Azure](https://techcommunity.microsoft.com/t5/azure-partner-community/business-as-usual-for-azure-customers-despite-2-4-tbps-ddos/m-p/2865945)

In the last weeks of August, Microsoft’s Azure service was able to save a customer hosting his data in Europe – it was the biggest attack to date in terms of volume, with over 70 thousand hosts sending requests. The inbound traffic was 140% larger than the impressive attack from 2020, also mitigated by Azure.

Though the blog post covering the incident does not share details,[ other news outlets state](https://thehackernews.com/2021/10/microsoft-fended-off-record-24-tbps.html) the attack was a type of DDOS known as UDP reflection.


    _“Reflected amplification attacks are a type of denial of service attacks wherein a threat actor takes advantage of the connectionless nature of UDP protocol with spoofed requests so as to overwhelm a target server or network with a flood of packets, causing disruption or rendering the server and its surrounding infrastructure unavailable.” _ – _thehackernews report_

Azure was able to fend off this attack due to the massive scale of the cloud, applying specific logic that could siphon the huge data wave before it ever arrived at the customer service. The solution was implemented behind the scenes, with customers experiencing no issues during the attack.

With services delivered over the internet, the risk of disruption is high – especially for high-risk targets. The abundance of IoT devices that form new botnets is such that protection against denial of service attacks must be considered when working on a critical system.

It is not an easy task, as DDoS mitigation happens at a very low level – not every company is able to invest in precautions. Even fewer companies are able to build in-house solutions to handle data floods of such volume.


### **Slow Yet Thorough – How to Scrape a LinkedIn Profile**

The news of the attack came via[ email from a concerned author at PrivacyShark](https://www.privacysharks.com/exclusive-700-million-linkedin-records-for-sale-on-hacker-forum-june-22nd-2021/), who saw a list of LinkedIn user data for sale on a hacker forum. Due to the hack, private emails and phone numbers were hosted online, available to malicious actors for spam and identity theft.

The issue of identity theft is serious, as it leads to losses on the order of[ 56 billion USD](https://www.cnbc.com/2021/03/23/consumers-lost-56-billion-dollars-to-identity-fraud-last-year.html), as reported by CNBC. The total number of US citizens hit by an identity fraud attempt is on the order of 45 million. If there is one thing we can take for certain, it is that data in circulation is being put to use by criminals at ever faster rates. Furthermore, attackers are using new approaches to access user data, which may occupy a legal grey area, such as automated scraping.

This activity does pose some interesting legal questions. LinkedIn is[ currently involved in a Supreme Court case](https://techcrunch.com/2021/06/14/supreme-court-revives-linkedin-bid-to-protect-user-data-from-web-scrapers/?guccounter=1&guce_referrer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8&guce_referrer_sig=AQAAAJyT8urbx-tHjXqgbeogejVIsA_UAecjQS3zsiFIWqnoH2wiIK6LOjRhAe1p-2mqfmQmP2cYnqas2hQURa0Qsz5GqOZvrY8NcGJZJon6UruXtRrs491RGKlQv8hQcmEi22b5czv2zuZYY3R9S_CrqsAFjssNOv0iXXKf_H25HSf0) that seeks to define online scraping as illegal. If the ruling is in LinkedIn’s favor, scraping their or other social websites could be deemed as criminal activity.

![alt_text](images/image3.jpg "image_tooltip")

### **An Alibaba Hack Leads to New Laws in China**

The attack on Taobao, part of Alibaba, had led to criminal prosecution and jail for the attacker as well as his employer. Personal data was siphoned out of the system for over eight months by an employee of a consultancy firm.

The data was supposedly not sold online. The judge ruled jail terms of three years, with fines totaling 70K USD. In the aftermath of this case, China introduced new data protection laws, granting the state the ability to shut down services at will or fine companies found mishandling _core state data_.

Subsequently, a personal information protection policy is also in the works as the government is heavily invested in IT infrastructure. This law will give immense power to officials running the country.

It is worth noting that security issues can lead to significant changes in federal and global laws. With IT security being considered at legislative levels, cybersecurity is an increasingly important subject for lawmakers to understand. After all, if those crafting and implementing new laws do not understand what they are doing, how can they make an informed decision on the matter?


### **npm Hosting Crypto Mining Malware**

With over six million weekly downloads, UAParser.js is a popular package used by developers all around the world. However, malicious versions of this package[ entered the registry](https://github.com/advisories/GHSA-pjwm-rvh2-c87w), likely through a hijacked account.

All computers running the package version served as open hosts to malware and trojans, starting a vicious cycle of infestation – this was an attack placed deep in the supply chain.


    _ “The malicious versions were found to steal data (including passwords and Chrome cookies, perhaps much more) from computers or run a crypto-currency miner.”[ Hackaday](https://hackaday.com/2021/10/22/supply-chain-attack-npm-library-used-by-facebook-and-others-was-compromised/)_

_ _The response to the attack was[ immediately put to public attention](https://thehackernews.com/2021/10/popular-npm-package-hijacked-to-publish.html?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+TheHackersNews+%28The+Hackers+News+-+Cyber+Security+Blog%29), and users could mitigate the issue once seen. It’s not yet clear how big of an impact this caused in the real world.

The important takeaway from this story is that supply chain attacks that lead to ransomware are easier than ever (remember[ Kaseya](https://edition.cnn.com/2021/07/06/tech/kaseya-ransomware-what-we-know/index.html)?) and do real harm. It only shows that even developers, who supposedly know a thing or two about security, can be vulnerable too.

An important element of this story is that once the attack was confirmed, the npm registry pulled all infected packages. Swift action can be a deciding factor in how well cybersecurity issues are resolved and how companies recover.


## **Conclusions**

Data safety, compliance, and security for sensitive information are prime topics for every industry touched by digital transformation. To create a secure ecosystem, it is important to know not only the systems we create but to also understand the attacks and outcomes for end-users. It’s crucial for users and designers to tread carefully when securing a system.

A leaked email may be relatively mild on the scale of hacking worries. Leaking credit card data or social security numbers, on the other hand, has real-world implications. Since the pandemic and the global drift toward remote work, hackers have developed new methods of stealing user data and money with each passing month.

Several organizations were not prepared to move toward digitized platforms and the predators lurking in the network. With cyberspace full of technologically advanced attackers, it is ever more important to stay on the safe side, with multiple layers of protection and strong IT practices.

The next entry in the Security Monthly series will describe ransomware attacks, as well as new attacks that use AI – stay tuned!
