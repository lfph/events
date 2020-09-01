# Adoption and Rollout


## LFPH Implementer’s Forum Webinar


### August 25, 2020

A Public Health Authority could build the best exposure notification app in the world, but without a strong rollout plan and good adoption it doesn’t matter. This LFPH Implementer’s Forum event had case studies from countries that have already rolled out their Google Apple Exposure Notification (GAEN) apps where they discussed the specific things they did well to increase adoption, some of the things they wish you had done differently in your rollout, and how they are working to continue to increase adoption post-launch.

Presenters included a European team sharing their real-world examples with the group as well as a public health expert joining us to share his experiences with rolling out public health interventions. We had presentations and live Q&A over the course of the hour. 

As with our last Implementer’s Forum event, we followed [Chatham House Rule](https://www.chathamhouse.org/chatham-house-rule) and the event was only open to teams that already have a GAEN entitlement. 


## Glossary

EN - Exposure Notification

GAEN - Google-Apple Exposure Notification (API)

PHA - Public Health Authority

PHI - Public Health Intervention


# Public Health Expert Presentation



*   Technologists and public health professionals have different lenses through which they look at getting participation in a public health intervention. This presentation focuses on how a public health professional looks at it. 
*   Example: getting glasses to kids who need them - Tech Side
    *   The presenter showed a website that advertises a first pair of glasses free
    *   He then noted that there were several details that were problematic - the free shipping was only for orders over a certain amount and there were a number of terms and conditions to be met
    *   The expected conversion rate for an ad such as this in the tech world might be 1% or thereabouts
    ![GlassesShop Banner Advertisement - First Pair Free](https://github.com/lfph/events/blob/jennydove-adoption-and-rollout/img/glassesshop.png)
*   Example: getting glasses to kids who need them - Public Health Side
    *   Examined a [press release from NY state](http://www.nysed.gov/news/2018/state-education-department-announces-no-cost-childrens-eye-exams-glasses-and-resources)
    *   They had several key activities they did:
        *   Researched high risk groups
        *   Partnered with NGOs and professional societies
        *   Endorsed by the State Education Commissioner
        *   Communications targeted to at-risk groups
        *   Reduced transaction costs
            *   It wasn’t just the glasses that were free; they also provided free eye exams, fitting, and delivery
        *   When they weren’t getting traction with a certain group they did additional outreach
        *   They’ve created a sustained effort - it’s now been 3 years of this program
    *   These are the elements that a PHA considers when trying to spin up a program
*   Standard, classic PHA strategy for getting high coverage
    *   Research to identify high risk groups
    *   Generate strong evidence for safety and efficacy of the intervention
    *   Have independent advisory groups act on that data and provide a recommendation
    *   Get those recommendations endorsed at every level of society
    *   Generate communications materials focused on consumer concerns, largely around safety and build on the safety data
    *   Remove financial costs from getting the service
    *   Reduce transaction costs as much as possible - take away the amount of time it takes to get the service, the paperwork required to access it, etc. Make this easy. 
    *   Have an ongoing cycle of learning - iterate as you learn more
    *   Continuous monitoring and feedback of the program
*   The public health system has a large number of components including community, system, individual elements - ![The wheel of public health interventions](https://www.health.state.mn.us/communities/practice/images/PHInterventions.png)[Source](https://www.health.state.mn.us/communities/practice/research/phncouncil/wheel.html)
    *   Exposure notification apps are population-level, focused on “disease and health event investigation”
    *   Question for implementers: are there more spaces that EN apps should play in? 
*   Example: Increasing flu vaccination coverage at the CDC, clinical trial
    *   [Original study](https://www.cdc.gov/flu/fluvaxview/hcp-coverage_1819estimates.htm)
    *   Asking healthcare workers just to do it voluntarily got ~42% vaccinated
    *   Doing additional advertising increased coverage to about 75%, but they had to re-do these marketing campaigns every year
    *   Having on-site vaccinations (aka lowering transaction costs) also got about 75% compliance, did not require additional promotion or marketing
    *   If there were multiple days to get your vaccination it went up to 83% 
    *   If the employer added some additional constraints, such as requiring a vaccination to get a parking permit compliance went up
    *   To get very high adoption - above 95% - the strategy was to require a vaccination in order to be allowed to interact with patients. Very few participants declined the vaccine when it was tied to their ability to perform the job they wanted to perform. 
        *   This is termed a “coercion” or “incentive”
*   To think through public health interventions, take your categories of intervention tools and score your plan. What are you investing in more of and what are you investing in less of? 
    *   System integration - is the intervention part of the healthcare system already?
    *   Evidence of safety and efficacy - is there proof that this is safe and it works? 
    *   Public communications - is the messaging getting out there in multiple formats? 
    *   Transaction costs - How much work does a person need to go through to participate? 
    *   Level of coercion or incentives - Are there other factors that would influence someone in choosing to participate? 
*   One thing to think about with EN apps - it’s currently unclear how high a priority this is as a society or a PHA. As a result, it’s hard to implement the levers and gain high adoption for the intervention. 
*   Coercion can be many formats - could be linked to a usual activity, an optional activity, or a required activity. 
    *   Usual activity “App required before you ride public transit”
    *   Optional activity “App required to use Uber/eat in a restaurant/etc”
    *   Required activity “App required before you go to school or work”
*   Suggestions to consider for GAEN apps
    *   Establish safety and efficacy
    *   Do good consumer research
    *   Build consumer-focused partnerships
    *   Get PHA endorsements
    *   Link use to essential or desired services
    *   Lower transaction costs, such as no battery drain and minimal hardware requirements
    *   Make it socially unacceptable not to use it
    *   Seek roads to “opt out” rather than “opt in” installation
    *   Garner public consensus on the priority of the app

## European Implementation Team Presentation

The presenter is from a team working for a digital innovation group with a European government. 

*   This country identified exposure notification early as a potential intervention for slowing the spread of Covid-19
*   The government asked for innovative tools from both private and public centers, including universities. 
    *   They did a public call for ideas around how to combat the virus and got thousands of entries
    *   This call for ideas was sponsored by multiple ministers, not just the ministry of health
    *   This meant that they had a task force evaluating the candidates around which EN app to choose, and ultimately chose a local startup to develop their app on the GAEN framework
*   The company built out infrastructure for a large team of volunteers to build and ship the app
*   They took a few key guiding principles that drove through the app and the adoption cycle
    *   Utility - be useful and practical, provide real actionable notifications
    *   Accessibility - Maximize reach through good UX, design, localisation, and tech
    *   Accuracy - Only notify users who have a substantial risk of having contracted the virus
    *   Privacy - Trust is critical, don’t ask for information that isn’t necessary
    *   Scalability - The system needs to work across the whole country
    *   Transparency - Everyone should be able to know the rationale behind the design decisions
*   Key features of their app, given these principles
    *   Privacy preserving - collecting analytics in a careful way so they can assess the efficacy without compromising privacy
    *   Open source - this allows the community to verify that the app actually does what it says it does
    *   Analytics for healthcare system - They have hooked up their analytics to the national healthcare system so that they can capture and assess some epidemiological data
*   Success is dependent on strong communication
    *   They got a PR group to work with them on a pro-bono campaign to promote the initial launch
    *   They’re working now on a “second phase”, targeting smaller communities and municipalities, finding influencers to help get adoption increased. With this, they’ve targeted a few specific areas where they want to see especially high app adoption rates. The goal is to create “safe haven” communities for app users. 
    *   Timing - push the app heavily at the initial launch, take advantage of the earned media as much as possible. 
*   Key issues with the rollout
    *   A lot of “fake news” around the privacy and functionality of the app
    *   Political disagreements and a lack of a unified front from the government to encourage adoption
    *   Incentives were unclear - beyond just getting exposure notification, there weren’t many reasons for users to download the app
    *   Marketing budget was low and so they could only work with what they were able to get donated
    *   Regional health departments were giving contradictory information to their constituents and to those who got exposure notification. That made it hard to make sure everyone who got notifications got tets in a timely fashion, created different word of mouth stories in the community and damaged the reputation of the app. 

## Discussion

*   Slack poll:
    *   Question for the audience: Our presenter spoke about making sure that we understand the safety implications of the intervention. How confident do people feel about the safety of GAEN apps?
        *   1️⃣  I'm not at all concerned about the safety of GAEN - I think we're in good shape.
        *   2️⃣  I think we've done a good enough job given the speed of development, but there's still more to do.
        *   3️⃣  We've got a ways to go and will need to keep improving and fixing the safety over time.
        *   4️⃣  We  need to slow down and address safety concerns before proceeding.
    *   Results: 1️⃣  - 3 votes | 2️⃣  - 6 votes | 3️⃣  - 2 votes | 4️⃣  - 0 votes
    *   There are people trying to hack the GAEN system, and like any other system it will be cat-and-mouse to keep ahead of what they’re attempting. [Article was referenced](https://www.forbes.com/sites/michaeldelcastillo/2020/08/27/google-and-apple-downplay-possible-election-threat-identified-in-their-covid-19-tracing-software/#5f60563e4bf3).
*   A second country chimed in about what worked well to get adoption up for them: 
    *   What appears to be working to produce high adoption in [our country] is a combination of a) trust in the other actions the government took during our first wave b) transparency (we published our code and worked with privacy advocates and they became allies) c) features (other than tracing) that citizens want (such as current data about where in the country infection is on the rise so they can plan)
*   How should a country deal with setbacks that start to shift user attitudes towards their app? An example was brought up in a country where a bug caused battery drain on Android for a few days. They found that they lost some goodwill from the population when that happened, and wanted to know what advice there is for teams to handle setbacks like this. 
    *   Public health expert: All PHIs will run into issues. Separate them out into two different types: the first are real issues with the design/science of the PHI, often around safety and efficacy, but also around getting the PHI in front of the right audience or positioning. The second set of issues are the anecdotes and rumors that the media might pick up on and magnify and cause a public relations issue.
        *   For science problems, take them VERY seriously and go back to the drawing board. 
        *   For the second type of issue, use all the investments you’ve already made in the rollout of the PHI to counter the rumor mill. Coalition-building matters for many reasons. Use a full range of society to respond - politicians, influencers, scientists, doctors, etc. One of the reasons you want all these different groups to be promoting the rollout of the PHI is that they then have skin in the game. If something isn’t going well mid-flight, they have a reason to get out in front of it to try and fix the issue. 
    *   European implementation team: There was a lack of political unity at the beginning, and we see some of our neighbors had more success with their rollouts because everyone throughout the government, across all political parties, were pushing with a united message.
        *   As for the social side there was also some resistance, and we saw all the fake news come out and the influencers and celebrities were not a part of the rollout.
        *   Lesson learned: Be swift in fixing the issue, don’t let it linger. Be proactive on public relations. Answer these issues quickly across multiple channels so that the falsehoods don’t ingrain themselves in people’s heads. 
        *   This applies to getting privacy advocates to review the source code ahead of time. Having those experts provide their stamp of approval _before_ rollout is very helpful. 
    *   Audience: Know that you will have to rebuild that trust, and adoption is a continuous game, not a one-and-done situation. People are constantly considering whether they should uninstall your app. 
*   How to deal with the politicization of an exposure notification app?
    *   European implementation team: Public health tools are important and should not get politicized. The majority of our political parties were unified, but there were still a few smaller parties that were opposed and vocal on it. There shouldn’t be debate about whether we should deploy a PHI if we know that it works and is worth it. To get political unity it comes back to the fact that you need to start messaging around why the app is important and helpful early on. Have those meetings with politicians early to try and get as many of them supporting from the beginning. 
*   How does interoperability drive adoption?
    *   European implementation team: Interop is very important because we have people who even commute across national borders. There’s a lot of pressure to deliver this and we have started piloting an interoperability solution. Technically there are not that many challenges or complications; the challenges are more organizational and legal as there will be issues around sharing data across countries. 
    *   Audience: Strongly consider allowing your app in the _global _app store instead of just your country’s app store. It helps get adoption from immigrant communities, tourists, and travelers. 
*   Should the app be required or is it better to have it as opt-in?
    *   One participant commented: We've found that in [our country] people appreciate that it's optional to participate. They like that surrendering their data is optional. They like that all the data is encrypted and stays on their phones until or unless they choose to upload their keys when they fall ill.
*   How do you define impact for these apps? Thinking about how the public health expert emphasized the importance of measuring efficacy, how are you making sure to do that? 
    *   European implementation team: One of the reasons there was such a battle this spring between the centralized and decentralized approach to exposure notification was because there was a belief that we could get much better data from a centralized approach.
        *   We’re also seeing people fearful of installing the app because they then will have to comply with a notification if they get one, and they don’t want to do that. 
        *   Most important piece of information being collected is how many notifications are being sent and which state the notification is getting sent in. 
            *   From this we can then notify a PHA within a specific state if we’re seeing a large number of notifications pop up in that area, warn them that a wave might be coming. 
        *   They also collect operational information to make sure that BLE is enabled, that the installation has gone well, and that the app is really working as expected. 
            *   (LFPH note: to learn more about different countries’ approach to analytics, take a look at this [video](https://www.youtube.com/watch?v=j0weRzYIsnM&list=PLLUsXRAaict7U00sMcwdLWwPPfRwpnMs5&index=6&t=0s) from the GAEN symposium and the Implementer’s Forum [analytics](https://implementers.lfph.io/analytics/) documentation page)
*   We have a good consensus that the safety of the app is alright or pretty good (see above poll, for instance). But one of the things mentioned in the public health expert’s talk was about making sure the efficacy is good too. Right now we don’t know for certain - how should we address this? 
    *   The people who should not be attesting to the safety or efficacy of the tool should not be the people who are building or promoting the tool. Use third party institutions, such as universities, research institutes, and other government entities that aren’t affiliated with the app to attest that the tool is working as it should be. Have those third parties be the ones to make statements about the efficacy and safety of the tools, not the teams launching the apps. 
*   Should these apps be required in some way or another?
    *   Public health expert: We use “incentives”, “opt in/out”, or “coercion” rather than requirements. It’s more about always having an incentive for someone to do something. But if something is heavily encouraged or default, then I’ve generally seen it to have a higher level of trust. People think that if something is required then the authorities believe that it is really effective. And don’t forget the other piece of this, lowering transaction costs. Make it incredibly easy to do and pair it with a lightweight incentive to drive adoption. Think of this like how Uber requires you to wear a mask before you get into one of their cars. 
    *   European implementation team: This is something we discussed, and really wanted to have some incentives in the app but were unable to get it there. We were hoping that we could link the app with the national health service so that if someone got a notification then you could get a test more rapidly and sort of “cut the line”. But not every regional health group was able to commit to this and so we couldn’t get it in the app. There were also concerns that if there was a large second wave we wouldn’t be able to uphold the promise we wanted to make with this additional incentive for having the app. We are asking companies and institutions to promote and encourage use of the app in their communities, and we’re seeing that work better than other adoption tactics right now. 
*   Have there been any challenges for the European team for sharing data between the national and the regional level? 
    *   This hasn’t been so tough - the national team has taken the lead around building the app and has been sharing all the data with the regional health departments, so it’s gone fine. 
