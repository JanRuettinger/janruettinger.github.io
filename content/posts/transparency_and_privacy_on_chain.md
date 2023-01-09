---
type: "post"
title: "On-chain Transparency & Privacy"
date: 2023-01-08T00:10:22+01:00
draft: false
---

This essay is about a topic which doesn't get enough attentation in the public debate about blockchains - the accessibility of user data. What data should be public and what data should be private? Should summarises or snapshots of user data be public? How do we prevent fraud? Blockchain technology is still in its infancy. We can still actively decide in what direction we want to go since all players in the field are still small. For now the most promising use cases for blockchains are in the financial space. In the future we could trade, borrow & lend, receive our salary and make payments on-chain. That's why I will limit the scope of this essay to financial data.

<!-- 
At the beginning of the essay, we will make a quick jump back in history and explore how (financial) privacy became a thing. Then we will look at the current state of technology with a focus on Zero Knowledge Proofs before we will closer inspect some real world examples of countries that have chosen different paths when it comes to privacy and look at how that influenced their societies. At the end I will come back to the concrete problems in the blockchain space and tease different scenarios of how the future of on-chain data can look like.  -->

## Types of financial data
There is financial data which is tied to individuals and other data which belongs to organisations. Here is a list of the different types of data and a short description who has access to it.

### Individuals
- Salary: known by employer, government and individual
- Payments: known by user, business and payment processors such as Visa/Mastercard who sell the data in anonymized datasets
- Tax/wealth: only known by the government and the citizen itself

### Organisations
- Revenue: known by the business owner, the government, the public if company is public and financial organisations such as Hedge Funds or payment processors that have often good estimates
- Tax: known by the business owner, government and the public if company is public

## Current state of the debate about accessibility of financial data
In my opinion we are stuck in a local optimum in the debate about how transparent or private our financial data should be. For years now the EU is pushing strongly for more privacy (right to forgot & GDPR) of personal data. This direction is dominating the debate and makes it difficult to start experiments around sharing data more transparently. Therefore, today we still heavily rely on whistelblowers to uncover tax fraud. Why are we pushing back against transparency so much? Let's go through a few cases where transparency has a positive impact.

<!-- . Companies like Apple who can afford it since their business model doesn't depend on user data are happily jumping on the train as well. The transparency side seems to be lose out. We still have no way to train ML models on large scale healthcare datasets because of privacy issues and we are still relying on  -->

### Salary data
Traditionally, employers don't want employees to share their salary info with others as it makes salary nenotiations more difficult for them. With public salary data employers have a hard time to trick employees into accepting a lower salary than the average. Some professions have figured out a system to share salary data and put the power back into the hands of employees. In tech there is a website called [levels.fyi](www.levels.fyi) where people constantly post their salaries anonymously. For example at Google for an L3 (junior engineer) the average starting salary is $183.329 which is shown in the image below. When you enter a salary negotiation at Google you know roughly what to a reasonable salary is. That's especially valuable for women and minorities who still lack significantly behind men in terms of their salary. This level of transparency is ideal but only works if the group of people who are willing to share their data is big enough.
![Vitalik Transaction](/images/transparency_privacy_on_chain/levelsfyi.png)

I think sharing your salary data anonymously is strictly positive for society. It would be valuable for two reasons. First, other people can see which job professions pay more and can change positions. Public salary data would create a more efficient labor market. Second, it would help especially minorities with few professional connections to better judge what their work is worth. 


### Public tax records
Since more than 200 years everyone’s personal tax return is made public in Norway. This allows media to easily create lists of the wealthiest people in the country and display their tax records. Sverre Solberg, Manager of a co-working space in Norway, says: "We want the press to be able to tell us if someone makes more money than they're trying to communicate through their own channels. It’s also a question of equality, as a social democracy we don’t want there to be a huge gap between the rich and the poor. An open tax return policy shows everyone how big that gap is, making it easier to discuss and address." Right now, most countries don't publish tax data on an individual level which makes it difficult to have public debates about it. There is a saying you can't improve what you don't meassure. 

I think making tax records public is again strictly positive for society.


### Public revenue info 
The Securities Exchange Act of 1934 established the SEC as a response to the stock market crash of 1929. The act was intended to increase transparency in the financial markets. It gave the SEC the authority to require publicly traded companies to disclose certain financial and other information such as executive salaries to the public. This lead to better informed investors and consequently more efficient markets. As soon as one company found a product which generates significant revenue and has healthy margins other companies can start offering competiting products to drive prices down. That's exactly what happened to the Cloud Computing market. Google, Microsoft and other companies saw how profitable AWS is and started to enter the space. 

I think making revenue data of large cooperations public as again strictly positive for society.


## Blockchain data is public by default
The three cases I just described won't be implemented anytime soon in the real world. But they are more or less the reality on most blockchains. Today, on Ethereum all transaction data is public. When you send money from one wallet to another wallet all metadata such as the address of the sender, the address of the receipient and the amount is publicly available. However, public data doesn't imply transparency. Let's look at an example. The wallet with the address `0x220866B1A2219f40e72f5c628B65D54268cA3A9D` currently has around $320 Mio worth of Ether. Just by looking at the address we don't know who this wallet belongs to. But since we know that the wallet received $320 Mio from an address that belongs to Vitalik Butherin (see image below) we can be pretty sure that `0x220866B1A2219f40e72f5c628B65D54268cA3A9D` also belongs to him. Otherwise why would he transfer all his assets to that address?

![Vitalik Transaction](/images/transparency_privacy_on_chain/vitalik_tx.png)

You can use the public transaction data to check how much a person received in on-chain salary payments, how much other gains a person made with trading. The same is true for businesses, you can see at every moment in time how much revenue an on-chain business has generated. 

<!-- Using a blockchain offers you anonymity but only as long as nobody knows your wallet address after which your data is fully transparent. As shown in the image below, on Ethereum your data is either public & anonymous or public & transparent.
![Data Attribute Matrix](/images/transparency_privacy_on_chain/data_attribute_matrix.png) -->


### What are the consequences of public by default data?
Let's look at a couple different situations where you use your wallet and see what consequences arise. 

#### Customized user experience
Whenever you use a website in web3 you have to connect your wallet to get access. Below you can see an example of the website of AAve which is one of the most popular DeFi applications.

![Connect Wallet](/images/transparency_privacy_on_chain/connect_wallet.png)

As soon as you connect your wallet the website knows your entire transaction history. Based on your transaction history the website knows stuff like: 
- Your balance
- How many and which NFTs you have
- How much you typically spend when using similar services
- ...

In the traditional world this data is only known by credit card companies. They anonymize your data and then sell it in packages for billions as described [here](https://www.fastcompany.com/90490923/credit-card-companies-are-tracking-shoppers-like-never-before-inside-the-next-phase-of-surveillance-capitalism). This type of data is very valuable since it's used to make accurate predictions about how much money people are going to spend on what services. Blockchain data is free. There is no gate keeping. 
In theory, the website can use the data to tailor the user experience to each user. Imagine you log into a trading website and the website knows that you have already done 1000 trades. The website can then show you a much more advanced trading interface. Similary, ads in web3 can be targeted a lot better. A downside is that the same information can be used against you by e.g. showing you a higher price since your balance shows that you are wealthy and can afford it. Companies like [Spindl](https://www.spindl.xyz) are betting on that future. They help companies get as much information as possible about their users. The founder Antonio worked at Facebook before and built out the Facebook ads marketplace. 


#### Fraud
When tax records were made public for one year in 1924 the Nebraska Senator Robert Howell said "Secrecy is of the greatest aid to corruption". At that time making tax records public made it easier to find corruption cases. The same is true on blockchains. Corruption and fraud happens but traces of it are stored on the blockchain forever. At some point people start looking closer into the transaction history and will reveal the fraud. [Here](https://twitter.com/jconorgrogan/status/1612163116317409284?s=20) is one example where a twitter user figured out that FTX was creating artificial trading volume on the Serum exchange to make it look bigger that it actually was. 

<!-- #### Payments
The initial primary use case for blockchains was peer to peer payments. I am confident that we will never see large scale adoption of payments with a native cryptocurrency like Bitcoin or Ethereum since their value is too volatile. Instead I am bullish on stablecoin payments. What is the impact of data being public on payments? Companies have to decide between two methods to collect payments. They can either accept the fact that everybody knows exactly how much revenue the business generates or they can use a new wallet for every payment to not reveal their wallet address. Even if a business uses a new wallet address for every payment. They have to be very careful when they collect all payments into bigger chunks. I still remember the early days of the trading analytics website Nansen. Nansen used a single wallet to accept payments. You could see in real time how popular their product was. Soon after they switched to Coinbase Commerce as a payment provider which creates a new wallet address for every payment. I think full transparency about how much revenue each business generates would lead to a more efficient market and thus to a better situation for consumers. Businesses, however, will prefer privacy and willdo everything they can to not reveal more data than they need to. -->



### Zero Knowledge Proofs open up the data sharing design space
Zero Knowledge Proofs (ZKP) are a mathematical construct which allows one party to prove to another party that they know a certain piece of information, without revealing any information about what that piece of information is. ZKP are at the core of how blockchains will scale to 10000s of transactions per second. Besides scalability, they also open up the design space of how data can be shared on blockchains. Let's go through a few applications of ZKPs.

#### Proof of solvency
After the centralized exchange FTX went bankcrupt Vitalik published an article where he introduced the concept of [proof of solvency](https://vitalik.ca/general/2022/11/19/proof_of_solvency.html). Proof of solvency describes a concept how one party, e.g. an exchange, can proof that it has sufficienlty large funds to cover all user deposits.
The concept can be generalised to a proof of claim. An organisation or a party can make a claim and verify that claim with a ZKP without revealing all transaction history. For example you can proof that your income was between $30k and $40k last with a ZKP and then show that proof to the IRS. The IRS can verify the proof and then assign you a tax bracket. The issue with ZKP attestations is that they are only as good and specific as the proof itself. When you see all transactions of a person you know exactly what happened whereas when you only know the result of the ZKP attestation you only know that that particular claim is correct. The user might have found a way to do fraudulent acivity which is not detected by the claim.

#### Privacy Mixers
Privacy Mixers are ZKP based smart contracts which allow users to send money from one wallet to another wallet without creating a connection between these two wallets. The most popular privacy mixer is Tornado Cash which was banned by the US government because it limits the ability of the government to oversee transactions and track criminals on-chain.

#### Aztec Network: private DeFi
Aztec is a DeFi rollup which allows you to shield all transaction metadata. This means you can make payments, borrow and lend money without another person knowing it's you. 
This solution gives you full privacy and makes it impossible for others to track what you are doing. This comes closest to the initial idea of blockchains to create a way to send money around without government inference. It's not clear to me yet how authorities can have an oversight in such a system to find bad guys. The compliance tools by the Aztec Network are rather minimal. There is a block and a daily deposit cap which makes it impossible to transfer large amounts of money into Aztec. This is probably not satisfactory for the government in the long run.


## No real world adoption by ignoring compliance 
I think it will be difficult to get any large scale real-world adoption without proper compliance tools since not many governments will accept it. Honestly, I don't fully understand why many in the blockchain ecosystem are obsessed with privacy and are willing to sacrifice governmental oversight for it. Our economy and therefore our life would look a lot different without transparent well functioning markets. 

## Let's start a debate
This marks the end of the essay. I hope it came accross that transparency can also be a value worth fighting for. Now, I invite you to contribute to the debate on the future of blockchain data. Here are a few questions that can be used as a starting point:
- What financial information do we want to be public and transparent and why?
- What financial information do we want to be private and why?
- In what cases can ZKP attestations be used as a compliance tool and where do they fail?
- What other compliance tools are necessary for web3 to achieve mainstream adoption?



<!-- ## Contrarian bets by VCs
I think it's int

Data startups: Dune, Flipside, Spindle
Marketing startups: 

Privacy chains:
Aztec

Issue: we need a more nuanced discussion around it and be open for experiments. Blockchain opens up the design space. We are still early.
What I am surprised is that we have to different groups in the blockchain community who have completely contrarian views but don't at all argue with each other. I think the ecosystem should form a debate and the following paragraphs should be a first step in that direction.

I would love to see a debate between Dune/Spindl whose business strive with as much public data as possible and Aztec/Aleo on the other side which try to allow as much privacy as possible. 
 -->


<!-- 
Data privacy vs function privacy

What other solutions are on the horizon?
- Hybrid: Private DeFi + private social/DAO
- Full privacy: how do you know that people are telling the truth: ZKP attestations proof of solvency
 -->









<!-- ####
In 1924 Congress decided to make individual taxpayers' information public to help fight corruption. Newspapers like the New York Times began to publish tax returns of celebrities and wealthy people. Journalists soon began to note the curious absence of some conspicuously wealthy people from the lists of top taxpayers. "Secrecy is of the greatest aid to corruption" said Nebraska Senator Robert Howell. Is was a high time for tax transparency. However, President Calvin Coolidge hated that tax information was public and convinced Congress again to reverse the decision arguing that public tax information was doing more harm than good. Since then tax records were never made public again.  -->

<!-- ### Security through obscurity
In software development there is a principle of security through obscurity. The idea is that you try to obfuscate security critical parts of your code as much as possible to make it difficult for attackers to find security bugs. The ideal version is to make your code private and not share it. In reality this is most of the time a bad idea. Attackers will find your code and then exploit it. Instead it's better to be fully transparent, share your code with as many people as possible so that as many eyeballs as possible can check your code for bugs before it goes live. This is now a best practice. I think it would be worth a try to apply the same principle to tax records. We can hope that it works or we can make them public so that it's easier for everybody to check when things look fishy. Indeed that idea was tried in 1924 which is discussed in the next paragraph. -->




<!-- ## Strong case for Privacy -->

<!-- 
### China healthcare  -->




<!-- ## 1. Brief History of Financial Privacy (in the US)

### U.S. Constitution in 1789
The U.S. Constituation came into effect in 1789. The world looked completely different back then. There were no cellphones and no internet. If you wanted to find information about a person you had to physically search them. The 4th Amendment provided some protection against that.
> The right of the people to be secure in their persons, houses, papers, and effects, against unreasonable searches and seizures, shall not be violated, and no Warrants shall > issue, but upon probable cause, supported by Oath or affirmation, and particularly describing the place to be searched, and the persons or things to be seized.

Today the situation looks more complicated. You can't go about your life without constantly giving up information to third parties. If you write a message to your friend, it goes through Facebook servers. If you use a navigation app, Google will know about your trip. To get this information nobody needs to invace your physical space anymore since it's all stored digitally.

### Law Review Article: Right to Privacy
In 1890 Louis Brandeis and Samuel Warren and wrote one of the most influential essay in American legal history. It's considered the first publication in the U.S. to argue for the right to privacy. Warren and Brandeis explain that the law needs to adapt to recent inventions namely instantaneous photography and the widespread circulation of newspapers. They write:

> The press is overstepping in every direction the obvious bounds of propriety and of decency. Gossip is no longer the resource of the idle and of the vicious, but has become > a trade, which is pursued with industry as well as effrontery. To satisfy a prurient taste the details of sexual relations are spread broadcast in the columns of the daily > papers. To occupy the indolent, column upon column is filled with idle gossip, which can only be procured by intrusion upon the domestic circle.

They argue that privacy deserves to be recognized as a right on its own to provide better protection for citizens. They defined privacy as following:
- publication of one’s thoughts and feelings
- publication of information about one’s private life
- publication of images of oneself, and facts about oneself that are not immediately obvious, such as a speech impediment or difficulty with spelling 

Their article "Right to Privacy" kickstarted the discussion and led to many legislative changes. -->

<!-- ### Establishment of the FTC
The Federal Trade Commission Act (FTCA) of 1914 established the Federal Trade Commission and outlawed unfair or deceptive commercial practices. Since the 1970s, the FTC has been the leading federal agency that is most often involved with privacy issues, regulations, and enforcement.

### Tax returns made public in 1924
The Revenue Act of 1913 introduced a modern income tax system which is similar to the system we have today. In 1924 Congress decided to make individual taxpayers' information public to help fight corruption. Newspapers like the New York Times began to publish tax returns of celebrities and wealthy people. Journalists soon began to note the curious absence of some conspicuously wealthy people from the lists of top taxpayers. "Secrecy is of the greatest aid to corruption" said Nebraska Senator Robert Howell. Is was a high time for tax transparency. However, President Calvin Coolidge hated that tax information was public and convinced Congress again to reverse the decision arguing that public tax information was doing more harm than good. Since then tax records were never made public again. 

### Foundation of the SEC in 1934
The Securities Exchange Act of 1934 established the SEC as a response to the stock market crash of 1929. The act was intended to increase transparency in the financial markets. It gave the SEC the authority to require publicly traded companies to disclose certain financial and other information like executive salaries to the public.  -->



<!-- ### Ways to keep your privacy with public wallets

### Privacy Mixers



## Is transparency really that bad?

Parts in society where transparency works


This is the weird world of crypto today. 

 -->




<!-- 
### U.N Declaration of Human Rights
Proclaimed by the United Nations General Assembly on December 10, 1948, the U.N. Declaration of Human Rights (UDHU) was drafted by representatives from all over the world with a variety of legal and cultural backgrounds. Article 12 states that 

> No one shall be subjected to arbitrary interference with his privacy, family, home or correspondence, nor to attacks upon his honour and reputation. Everyone has the right > to the protection of the law against such interference or attacks.

### Supreme Court Rulings Related to Privacy

- Griswold v. Connecticut (1965) was a landmark Supreme Court case involving a Connecticut “Comstock law” that prohibited all forms of contraception. By a vote of 7-2, the Supreme Court ruled against the law on the basis of the “right to marital privacy,” laying the foundation for the right to privacy with regard to intimate practices.

- Katz v. United States (1967), a landmark decision the Supreme Court, extended Fourth Amendment protections against unlawful searches and seizures beyond citizens' homes and property to anywhere a person has a reasonable expectation of privacy.

- Eisenstadt v. Baird (1972) was a U.S. Supreme Court case that guaranteed the right of unmarried people to possess contraception. The ruling was based on the right to privacy established in Griswold v. Connecticut and the Equal Protection Clause of the Fourteenth Amendment.


### Privacy Act of 1974

Enacted December 31, 1974, the Privacy Act of 1974 is a U.S. federal law establishing a Code of Fair Information Practice on federal agencies’ collection, maintenance, use, and dissemination of personally identifiable information.



### EU Data Protection Directive 1995

Adopted by the European Union in 1995, the Data Protection Directive regulates the processing of personal data within the EU. In comparison to the United States, the right to privacy is a more highly developed field of law in the EU. The Data Protection Directive was superseded by the General Data Protection Regulation (GDPR) in 2018.

### Gramm Leach Bliley Act 1999

The Gramm-Leach-Bliley Act (GLBA), or the Financial Modernization Act of 1999, is a federal law requiring disclosure by financial institutions of how they share and protect private customer data. The law requires financial institutions to explain how customer data is shared, provide an opportunity for customers to opt out of having their info shared, and protect private data with a security plan created by the institution. 


### State Data Breach Notification Laws 2003

In 2003, California was the first state to implement data breach notification laws. The new legislation required businesses and state agencies to disclose when Californian’s personal information was exposed in a security breach. Most other states in the U.S. and some jurisdictions abroad have modeled their data breach disclosure laws after this legislation.

### EU Right to be Forgotten

The European Commission in 2012 released a draft European Data Protection Regulation that would supersede the EU Data Protection Directive. The law allows EU citizens to submit requests to search engines to have personal information delinked from the results of searching their name.

### GDPR 2018

The General Data Protection Regulation (GDPR) is a law dealing with data protection and privacy that went into effect in the European Union (EU) and the European Economic Area EEA) on May 25, 2018. It also applies to the transfer of personal data outside of the EU and EEA.



### CCPA 2020

The California Consumer Privacy Act (CCPA) is a state statute intended to regulate how businesses handle the personal information of residents of the state of California. The CCPA was signed into law in 2018 and went into effect on January 1, 2020.

On March 2, 2021, Virginia’s Governor signed the Consumer Data Protection Act into law. Following California, Virginia became the second state to enact major privacy legislation of general applicability in the United States. The CDPA will come into effect on January 1, 2023.

On July 8, 2021, the state of Colorado officially enacted the Colorado Privacy Act. The law goes into effect on July 1, 2023.  -->

<!-- 
the desirability and necessity that the common law adapt to recent inventions and business methods—namely, the advent of instantaneous photography and the widespread circulation of newspapers, both of which have contributed to the invasion of an individual's privacy. Warren and Brandeis take this opportunity to excoriate the practices of journalists of their time, particularly aiming at society gossip pages:

    The press is overstepping in every direction the obvious bounds of propriety and of decency. Gossip is no longer the resource of the idle and of the vicious, but has become a trade, which is pursued with industry as well as effrontery. To satisfy a prurient taste the details of sexual relations are spread broadcast in the columns of the daily papers. To occupy the indolent, column upon column is filled with idle gossip, which can only be procured by intrusion upon the domestic circle.


Their main point is that privacy is already common law and judges use property and contectual rights to protect privacy to some extend. 


law review article published in the 1890 Harvard Law Review

The first three paragraphs of the essay describe the development of the common law with regard to life and property. Originally, the common law "right to life" only provided a remedy for physical interference with life and property. But later, the scope of the "right to life" expanded to recognize the "legal value of sensations." For example, the action of battery—a protection against actual bodily injury—gave rise to the action of assault—fear of actual bodily injury. Similarly, the concept of property expanded from protecting only tangible property to intangible property.  -->



<!-- This essay is meant to kick-start an 

 before looking at the current state of blockchain technology and it's outlook for the future. Here, I will discuss in depth the strengths and shortcomings of Zero Knowledge Proofs. Then we will look at 

different approaches to privacy accross

Every few years

By default all blockchain data is pubThe topic is transparenct vs privacy.

Every few years a new technology comes around 


Every few decades new technology allows us to question existing power structures.
- Books with Martin Luther King
- Online education vs expensive tuition only for the elites
- Social media: how is a star? Media companies are losing power

Now: transparenct vs privacy. What information should be public

https://www.nytimes.com/2019/04/13/opinion/sunday/taxes-public.html

History of privacy
- good for normal people in dictatorship
- good for elites in democracy -->


<!-- # One of the most underrated debates: transparency vs privacy
# or can we have both with ZKP attentations?
# ZKP attestations
## - can they be faked, manipulated? (the don't show the full picture)
## 

# Norway tax
# Security through obscurity doesn't work in software

# patents exist for a reason - will full transparency harm innovation
# view keys - what are they
# why is there no discussion? invite to kick it off
# Does DeFi need public information? Fragmented liquidity
# Companies make different bets: Aztec vs Dune vs Spindl
 -->
