# LFPH GAEN Symposium Plenary Session



*   The goal of the implementor’s forum is to build community with everyone building GAEN apps
*   LF Public Health is a brand new foundation under The Linux Foundation, focusing on public health efforts
*   LF Public Health and staff are here to help with apps and questions, available via Slack
*   LF Public Health is launching next week!
    *   Membership options are available, please speak with Dan Kohn
*   This symposium is designed to be interactive - please use the Slack channel to post thoughts and questions
*   This symposium will use Chatham House Rules for notetaking
*   Mid-March, people started to realize that these issues were important and discussions needed to start happening about how to move forward using technology
    *   People also noted that the technology created could have unintended consequences and could be used maliciously.  There was a need to discuss privacy
*   GAEN = Google and Apple protocol
    *   Builders of apps - we need to think more broadly about the technology


# COVID-19 Public Health Essentials for App Developers


## Kacey Ernst and Amanda Wilson, _University of Arizona Public Health_



*   Over 13 million case of COVID-19 and nearly 600,000 deaths
*   We cannot look at the cases dispassionately, as the people affected are mothers, brothers, fathers, friends, sisters, and children.
*   Primarily transmitted through close contact and droplet spread, can also be aerosolized
*   Other lesser studied modes of transmission are mother-child during pregnancy, fecal-oral transmission, and blood-borne transmission, but these all need more rigorous evidence in order to define their quantitative probability
*   SARS CoV is challenging to prevent - it can be transmitted by presymptomatic spread, before someone displays symptoms, or via asymptomatic spread, where the individual never shows symptoms
*   On average, time from exposure to symptoms is 4-6 days, but it could be up to 14 days
*   Duration of exposure and distance from the infected are two critical determining factors determining whether someone gets infected
*   Age of the affected person may affect transmission.
    *   Younger children appear less likely to transmit when affected
*   Being face to face compared to side to side increases exposure
*   Indoor exposure is much riskier than outdoor exposure
*   Respiration patterns such as exercising, singing, coughing, sneezing, or other activities that increase the force of exhalation increases the potential for aerosolization and expulsion of the virus into the air.
*   There are several benefits of bluetooth exposure notifications - it has the potential to be faster, notify people that you don't know, preserve privacy, minimize recall bias of duration of exposure, and has the potential to connect well with public health guidance and provide resources to people that may need to be in quarantine.
*   Uptake of these technologies is unlikely to be universal, but there are certain instances that could maximize GAEN technology, especially when one has a high chance of interacting with people you do not know, such as classroom settings, public transportation, travel
*   In regions where manual contact tracing programs are delayed or overwhelmed, these automatic notifications may be the only notification received
*   Broader perspectives on GAEN application to be considered in design and implementation
    *   We want to minimize false senses of security.  Low use may lead to a false sense of security if others around you do not use an exposure notification app. You would not be getting notifications and so would think you are “covered”, but really it’s just that others around you are not using the app and doesn’t reflect your safety. 
    *   Equity issues - are we reaching the most marginalized communities?  Or just the ones that have smartphones and are able to physically distance? Think both about who has access to smartphones as well as who just might not have the latest technology. 
    *   Availability of testing could limit utility - laboratory results are taking 7 to 14 days, so systems that rely on positive test results the usefulness of the alert would be limited
    *   It can be challenging to put into place physician-generated codes for input into the app for case confirmation, and that infrastructure and buy-in that we would need from the medical community is quite significant.
*   How do we go about determining the risk of a single exposure?  
    *   Dose = the number of microbes we are ingesting or inhaling
    *   Dose affects our risk of a negative health outcome, such as infection, illness, death, etc.
    *   Relationship between dose and the probability of a health outcome is referred to as “dose-response”
    *   What affects dose?  
        *   Time
            *   Duration of an interaction
            *   Volume of air inhaled over time
            *   Amount of virus inhaled
            *   Duration x Volume x Amount of Virus = amount of Virus
        *   Orientation of faces
        *   Distance between people
            *   Bigger droplets deposit faster over shorter distances, meaning closer interactions pose greater risk of exposure to large droplets
        *   Amount of the virus being shed
            *   Theoretically, the density of the virus being shed drops dramatically as the days after symptom onset pass
            *   The molecular data we actually see is much different
        *   Characteristics of the air
            *   Useful analogy:
                *   Indoors = putting a drop of dye into a glass of water
                *   Outdoors = putting a drop of dye into the ocean
            *   Relative humidity
                *   Greater “transfer efficiency” - fraction of total amount of microbes that are transferred from one surface to another
                *   Has effects on inactivation of virus
                *   Has effects on aerosol sizes and concentrations in the air
    *   What makes one interaction riskier than another?
        *   The following questions need to be answered:
            *   How long was the interaction?
            *   How close was the interaction?
            *   How much was the person shedding the virus?
            *   What were the characteristics of the air when the interaction took place?


# Diagnosis and Authentication Process



*   Why are we here?
    *   We want to build this technology to slow/stop the pandemic
    *   There is always a learning curve when communicating with the public
        *   For this particular technology, there are 2 curves
            *   1 - not knowing if the technology will work
            *   2 - learning how to limit your exposure
    *   There are a few methods to handle exposure:
        *   No intervention
        *   Universal Quarantine - would stop spread but hard to do
        *   Manual Contact Tracing - Tough to scale up when there’s a large number of cases.  Not everyone gets alerted, but not enough to stop the spread.
        *   Manual Contract Tracing + Exposure Alerts - The two methods work best in combination. The hope is that this will help stop the spread
    *   With manual contact tracing, a contact tracer talks to someone exposed on the phone and tries to identify who they interacted with, and will then go speak to those exposed
        *   People might not remember who they interacted with or may have exposed
    *   The hope with exposure notification apps is that people (who have the app) can be alerted anonymously about exposure, as well as doctors and runners.
    *   The apps are designed with privacy in mind
    *   How do we communicate to the public how anonymity is possible with exposure notification apps?
        *   A useful example is that the app on your phone sends out random words every once in a while.  Other nearby phones with the app will hear those words and remember them.  If you are exposed and upload it to your phone, your app will then alert other people’s apps that it interacted with using the random words that were sent out in a given time period.
*   **Diagnosis and Authentication Presentation**
    *   Why is Diagnosis Authentication needed?
        *   To build trust
        *   Prevent fake notifications and increase confidence in the technology
        *   Reduce unnecessary quarantine
        *   Accurately judge someone’s risk
    *   Design goals
        *   Difficult to falsely submit diagnosis keys
        *   Minimal effort from healthcare system
        *   High user compliance
        *   Low notification delay
        *   People trust accuracy and privacy
    *   Authentication method
        *   Verification code - portal used to generate code
        *   Users enter code into app to authenticate
    *   Interfacing with Public Health
    *   Number of groups that could be responsible for authentication
        *   Case investigators/contact tracers
        *   Doctors/nurses
        *   Testing facilities/labs
        *   Automated messaging
    *   Updating Diagnoses
        *   Reducing notification delay is critical
        *   Could notify people even before positive test results returned
    *   At-home tests
        *   At-home testing will come soon
            *   Faster and more widely available
        *   How to enable low-effort diagnosis reporting without reducing trust in the system?
            *   Central reporting of results tied to identity?
            *   Codes associated with each test?
            *   Authentication by community health workers?
*   Q&A
    *   Q: If we went from presumed positive and then the test results came back with negative, what are some of the challenges of that with the way GAEN is set up?
    *   A: There's no official support for that functionality yet but assuming that Google and Apple want to do that, the main challenges are conveying to the user that there was a new update (ie the user experience)


# Analytics, App Accuracy, and Disease Progression in a Community


## Comments from a team with a deployed app



*   Amazing response in the country from the app they deployed
    *   X million people have installed and configured the app
*   Most important things they did to get adoption:
    *   Public health response to COVID-19 built trust and acceptance with the public
*   Initial problem with the media due to all of the different tech options that were being evaluated at the time
    *   The outside observer is saying “tell me what you’re going to do” and when you don’t have a good answer, it’s a difficult situation to be in
*   Used a decentralized architecture
    *   Public Health response involves the identification of an index patient and then the tracing of contacts you suspect could be infected with the disease. It’s all around the limitation of that 
    *   Decentralized approach comes from a different place (privacy preserving). It deals with the data from everyone which creates other problems, massive amounts of information
    *   Problematic when a government undertakes this - boil back to the trust relationship with the government and its citizens
*   Technical issues make the delivery of a bluetooth app very difficult, but GAEN flipped that.  However communicating to the Public Health people was challenging, as they no longer would have an index patient.  Instead, it would be an unknown contact.
*   Small amounts of data available - people who download the app can choose to provide data or not
    *   Consent can be withdrawn at any time, making analytics even more difficult
*   Data protection and privacy were extremely important when building the app
*   App augments an existing contract tracing system
*   If you only had an app, you would need 60% adoption, but if you have a larger system in place with testing and other contact tracing methods, you wouldn’t need as much adoption of the app to be effective (referring to the research from the [Coronavirus Fraser Group](https://www.coronavirus-fraser-group.org/))
*   Data from the app can help people make decisions about their own behavior, where they will go and how they interact with others
    *   People want more data from the app, but much of it is hard to provide given the limitations of the system
*   If someone tests positive, they are asked to upload keys from GAEN to registry
*   We’re also seeing adoption of our app from other countries
*   Q&A
    *   Slack Q: Do we have any idea what fraction of people who get a positive diagnosis actually do consent to enter it into the app?
        *   A: Small sample size so far but it's pretty high, there have been some people balk when asked but not many
    *   App has been live for one week but unprecedented levels of adoption in their opinion (more than 25%).
    *   App alone is not sufficient, there needs to be a larger system of support


# Measurements and Signal Attenuation 


## Comments from a professor



*   Epidemiologically Significant Encounters
    *   If a user reports they were diagnosed, we want to determine that the encounter was close and long enough that other users should be warned of the exposure.
    *   Air circulation and PPE can be significant, but the app would not have that information
    *   Health authority can provide guidance to define a significant encounter, based on evolving knowledge
*   Bluetooth can’t precisely measure distance
    *   Signal strength is affected by many things, such as location (front pocket, back pocket, held, etc)
    *   Some encounters are in the “grey zone”
    *   What time/distance characteristics do we really want to or not want to report?
    *   What falls in between, and how would we prefer to classify them?
*   Phones are always broadcasting out messages to other phones.  Every so often, the phone does a scan (every 2.5 to 5 minutes, lasts for 4 seconds) and listens for other phones in range that use the framework.  It records the attenuation for the signals from other devices in range
*   Terminology for this talk: Encounter vs. Exposure Detection
    *   Encounter Detection: talking about measuring time and attenuation/distance
    *   Exposure Detection: combining detection of an encounter along with other information to decide if a user should be warned of an exposure 
*   Approaches to detecting significant encounters
    *   Goal is similar to desired physical characteristics
        *   A minimum of a certain amount of time with a low attenuation
        *   Low signal attenuation correlated with devices being close
    *   Initial design in April just duration and attenuation risk and config file, proved difficult to use to correctly classify encounters
    *   Most everyone uses attenuation thresholds and durations, perhaps in conjunction with duration and attenuation risk
*   Thresholds
    *   Specify low and high attenuation threshold
    *   Split exposure time into 3 buckets - low/medium/high
    *   Defined meaningful time - _time in low_ **+** _time in high_ **/** 2
    *   Initially uses thresholds of 50 dB, 55 dB, and greater than or equal to 15 min
        *   May be too conservative
    *   Evolving: don’t blindly use any one set of numbers, discuss and review with your PHA and epidemiological team
*   Attendees invited to take the Encounter Detection Survey (link in Slack)
    *   No one right way to determine which encounters are reported
    *   Apple/Google are not giving recommendations on this
    *   Teams developing apps should communicate with each other
        *   Share basic approach
        *   Note unusual things they are doing
    *   Asking teams/apps to fill out a survey, the speaker will publish results
    *   Questions:
        *   Basic approach - are you using a config file or attenuation threshold
        *   Are you combining exposures or looking at exposures separately
        *   Is anyone using more exotic ideas
        *   Close/Prolonged encounters
            *   Some encounters barely exceed threshold, others significantly exceed
                *   Are these treated differently?
                *   Perhaps described differently to user?
        *   Are thresholds universal?
            *   Do you anticipate situations where different thresholds might be used for different people?
                *   Perhaps based on personal risk profile?
                    *   Someone living with elderly parent might want lower threshold
        *   Empirical studies
            *   Lots of people are doing studies, don’t take any as gospel
            *   Look for studies that are actually collecting data via EN framework
            *   Both static measurements and scripted scenarios are important
*   Not a lot of answers given in talk, as people really need to think about this and talk to each other
*   Link to [survey on measuring attenuation and duration in GAEN](https://forms.gle/zKJvFSiBJcN19gXA9)


# Adoption, Notification and User Experience 


## Elissa Redmiles, _Microsoft_



*   UX and Adoption Challenges
*   3 main types of COVID-19 apps implemented
    *   Contact tracing
    *   Information-based - personalized narrowcast or general broadcast
    *   Medical - symptom checkers, home health support
*   Adoption matters for all apps, but particularly contact tracing apps
    *   Benefit of contact tracing app use scales quadratically with the number of users
    *   Doesn’t mean low app adoption won’t be beneficial, but more and more benefit as apps are adopted throughout the population
*   Adoption has to be facilitated and encouraged - unofficial rough estimates show 20-40% voluntary adoption across four countries
*   Many possible variables for app adoption decisions
    *   Benefits of using an app - receiving exposure notification, joining the fight by installing app, helping government and researchers
    *   Who is the provider - provided by public health department, federal government, university, employer, etc?  Different populations have their own preferences across the world
    *   Privacy and authoritarianism - apps represent an increased level of surveillance
    *   Mobile costs & “I don't use apps” - older devices and battery drain, mobile data plans, socio-economic status, some people don’t use apps
    *   Accuracy - “will it work?”  People care about accuracy based on research
    *   Disbelief of COVID - people may not believe that COVID is a threat, might be overwhelmed
*   Each adoption consideration offers many implementation directions
    *   Personalized guidance and announcements
    *   Exposure alerts
    *   Information about hotspots / locations of infected
    *   Ability to donate data to researchers
    *   Ability to record symptoms
    *   Ability to make contact with a medical professional
*   Research from multiple groups suggest these considerations (and more) matter for adoption
*   Contact tracing apps are unique - they benefit others more than they benefit the user
    *   Users with the app can get notification exposures, but generally the apps help protect the community
    *   Research suggests that financial incentives may be 2x as powerful as other considerations in users’ decision to adopt contract tracing apps
*   Culturally relevant tradeoffs may exist as well
*   Q&A
    *   Q: We’ve seen a number of apps out there, have you seen any particular strategies around adoption that stand out as successful?
        *   A: Germany’s approach to advertising to their app is unique
        *   Have to think carefully about how to incentivize adoption
        *   Focused on getting people to adopt, but not the end of the story
            *   If diagnosed, will users be willing to upload to app?
            *   What are people actually willing to do if exposed?
            *   Are users using the app the way we need/want them to?


# Recent API Changes to GAEN



*   API Changes
    *   Exposure notification framework continues to evolve
    *   Talking to developer contacts at Apple/Google is the best way to learn more about these changes
    *   Many people have been told details about upcoming API changes are not yet public - don’t share during this symposium please
*   API Changes:
    *   iOS 13.6 was released on July 15
    *   Bug fixes to EN framework
    *   iOS 14 will ship in the fall
    *   Google announced v1.5 of their Exposure Notifications APIs
*   Rounding of duractions - iOS 13.6
    *   Duration of an ExposureInfo in no longer rounded up to the multiple of 5 minutes
    *   You might need to tweak your parameters for which exposures to report
    *   Might want to allow different config files depending on which iOS version your code is running on in case it becomes relevant later
*   ExposureWindows (Android EN 1.5)
    *   A different API for looking at data from Exposures
    *   Replacement for ExposureSummary and ExposureInfo
    *   Same day release of keys
        *   Framework can now provide a key that applies to the previous part of the day, and generates a new key for use for the rest of the day
            *   Will result in keys that have rolling periods other than 144
        *   Impacts servers and older clients
