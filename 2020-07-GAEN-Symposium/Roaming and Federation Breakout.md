# Roaming and Federation

## LFPH GAEN Symposium Breakout Session


### Resources:

*   [Europe’s Interoperability Specs](https://ec.europa.eu/health/sites/health/files/ehealth/docs/mobileapps_interoperabilityspecs_en.pdf) 
*   [Digital Contact Tracing Service: An improved decentralized design for privacy and effectiveness](https://arxiv.org/abs/2006.16960)

## Introductory Thoughts

*   Roaming and federation will be an important consideration as we go forward
*   Using Google’s Reference Server, interoperability should not be too difficult

## WHO

*   When it comes to federation, a shared key system conversation should involve WHO or world authority
    *   WHO takes time to get used to new technologies
    *   Would LFPH be a good place to start this? APHL has efforts underway in the US
*   What is the WHO’s information collection and dissemination plan, regarding the app, moving forward? Information on emergency numbers, public health information per jurisdiction etc. 
    *   WHO has a huge advantage here. They have 140 country ambassadors with strong relationships to health ministries. WHO can get information and help figure out what customization each country wants. 
    *   It’s mostly a manual process, as of right now, from representatives. Because there is so much variation from nation-to-nation, there are a lot of benefits from this manually gathered information.
*   Can the WHO’s app be paired with the country’s exposure notification key server to avoid duplication? 
    *   If you need to set up a new server in each country, that’s a huge barrier to adoption. There are a lot of steps and work that go into creating each server. 
    *   Leveraging existing cloud infrastructure is the current vision and rolling out the app as a managed service. App itself is designed to run entirely offline.
*   Is the WHO app implementing GAEN or just sticking to information?
    *   WHO still getting comfortable with exposure notifications
        *   Interested in more data regarding efficacy
        *   Still looking for evidence 

## EU and other country considerations

*   In the European Context, there’s so many different commissions and compliance/security frameworks. How do you think about who is declaring these protocols and which ones to comply with? (ie. eHealth isn’t immediately compatible with GAEN)
    *   Major tension we’re seeing between open-source google implementation and eHealth demands is central database with all COVID-19 positive keys for members of eHealth network
        *   Not multiple databases communicating
        *   National systems may want the control to turn off federation. Even though Europe has the cohesiveness to manage this, other countries may not like the same idea. 
*   European Commission is tasked with implementation in tourism. Because of this, they have been leading the federation/roaming charge to enable tourism around Europe. 
    *   In the US, APHL is working on a federated key server that is US-specific
    *   Europe is a lot further ahead than the US
    *   These efforts could be a great source of knowledge for what exactly needs to be standardized - getting these things on paper is a good first step
*   Tourism-based countries will have different structure than large governing bodies like the EU, because of GAEN as means for tourism
    *   In the US, there haven’t been any productive conversations along those lines
    *   Irish context, access to the application limited to those registered with locals until July 16
*   For individuals who travel often, what happens if they use multiple different apps?
    *   Procedure of users getting a notification to switch apps is not solidified
        *   OS-level notifications aren’t documented, but important for communication to the traveller/user
        *   Apple/Google should work on this
    *   Regulatory-wise, is it possible to not have to download a new app every time I visit a new country?
        *   When you intersect with adoption, you’ll get a much lower uptake if they have to download the right app for every new country. It might not always have the suitable language and so on.

## Standardization



*   Regarding exchange of keys and verifying test results, we’re seeing two or three states shifting infrastructure to allow standardization. States seem to care a lot about their nation and what their surrounding states are doing.
    *   Establishing standardization will allow better collaboration
    *   LFPH could be a great place to host this conversation, which could eventually be transferred over to WHO
*   If travelling from one country to another with a compliant app, but my app is configured to home country information, there may be issues with international interoperability.
    *   As it stands now, Google allows for iPhone developers to know country location; however, Apple doesn’t allow country location to be identified. This is an area where Google and Apple’s different design of location services may prove troublesome. 
        *   Side note: NMCC should be readily available on iOS from CoreTelephone framework
    *   Irish app’s info displayed, when a notification is shown, is configured through the back-end.
    *   Standardization would be beneficial here.
*   Content must be updatable adherent to rapidly changing guidance
    *   Issues of different standards arise here
*   GAEN API v1.5 really changed what we would put into the metadata and standardize the transmission risk field
    *   We should start with 1.5 if we take steps to standardize metadata

## Server Development

*   The best solution, public health experts say, is to create one nationwide server that will power exposure-notification apps no matter where they're used in the country. Brookins calls this the last big remaining obstacle to releasing these apps.
*   The Association for Public Health Laboratories has taken charge of setting up this nationwide server. APHL already compiles all kinds of medical lab data from around the country, and maintains the foundations for [Sara Alerts, a case-management system](https://www.consumerreports.org/public-health/tracking-coronavirus-is-a-huge-task-these-systems-could-help/) that human contact tracers are using in Virginia, Arkansas, Arizona, and elsewhere. 
    *   [https://www.consumerreports.org/coronavirus/covid-19-contact-tracing-apps-could-slow-pandemic-but-delayed-release/](https://www.consumerreports.org/coronavirus/covid-19-contact-tracing-apps-could-slow-pandemic-but-delayed-release/)

## Open-Ended Questions

*   How will we handle cross-jurisdiction compatibility without explicitly defined borders?
*   Concerning federated test access and verification servers, is there any potential for sharing/centralizing testing databases (in a state-nation context)?
    *    Do we know of any current testing server federation efforts?
*   US approach to trade-union. Are states (in state-nations) solving this problem by using federated servers in countries/jurisdictions others are working with?

**_Positive Takeaway_**

*   Found that zero rate apps in large groups of countries was essential for adoption and federation
    *   Zero Rate -> Verizon or other cell networks not charging data for use of app
    *   Getting in touch with cell networks to zero rate could help with roaming and federation 

# Conclusions 

*   Good step here is enumerating problem scenarios
    *   Second step is identifying standards that would help eliminate these problem scenarios. LFPH could be a good place to prototype these standards before maybe moving to WHO.
*   Helpful to pull a list of action items out of conversation
    *   Zero-rating
    *   Other federation topics
    *   Further collaboration on standardization will be via a shared doc
