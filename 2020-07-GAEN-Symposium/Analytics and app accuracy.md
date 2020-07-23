# Analytics, App Accuracy, and Disease Progression in a Community
## LFPH GAEN Symposium Breakout Session

## Tracking Notifications

*   How many notifications have been sent in [country A]?
    *   Close contact events have been generated
    *   There have been some keys uploaded
    *   Calls have gone out from contact tracers and secondary contacts have started getting tested
        *   They test people on day 1 and day 7 after exposure
    *   Contact tracing of the index case follows a two step procedure
        *   Call 1- you’ve tested positive, would you upload your keys? 
        *   Call 2 - more detailed case interview with manual contact tracing
*   The people who receive exposure notifications should test positive at a higher percentage than the general population, the delta between the people who receive exposure notifications and the general population is how you can quantify the value of EN
*   In East Asia the baseline % positive has been about 1% versus [US state A] is currently testing at about 4%. So think through a baseline 1% infection risk across a total population. 
*   Country A focused their launch on getting the privacy elements right. Now they’re starting to shift their focus to efficacy. And EN is just one element within a wide range of public health interventions, but the media treats the app as a panacea and the only thing that will work. 
*   State A has had to fight to get quarantine and infection/exposure risk to be managed consistently, rather than focusing on future infectiousness. 
    *   Key risk factors:
        *   Duration
        *   Attenuation
        *   Time of exposure relative to symptom onset
        *   Quarantine
*   Country A is also dealing with these challenges
*   What worked in state A was asking for a whole lot and getting refused which meant that the compromise got them some of what they actually wanted
*   Country A put a research group together and wanted to ground decisions in public health policy and science. This also helped technology and public health people actually develop a shared understanding of what’s possible. 
    *   They needed to pick what phase of pandemic/strategy they were in (i.e. containment) and get their app settings to match. 

## Exposure Science and Infection Risk

Much of this is based on [Quantifying SARS-CoV-2 infection risk within the Apple/Google exposure notification framework to inform quarantine recommendations ](https://www.medrxiv.org/content/10.1101/2020.07.17.20156539v1.article-info)

*   The 2 m guideline for distance is an approximation by scientists, but it isn’t exact
*   The reason that short distances are useful as a shortcut is because it assumed that they were more likely to be face-to-face and talking, just based on social standards, and face-to-face is far more risky
*   There is a 10x difference in risk between different transmitters based on how the infectivity data has been interpreted; this aligns with the culture data from the epidemiological models. 
    *   We’re actually at the point where we can quantify the actual dose required for people to get infected
    *   There’s a lot we don’t know about asymptomatic
    *   So what this really means is that **date of symptom onset matters a lot **
*   GAEN 1.1 allows us to capture this data around symptom onset
    *   Given this we can actually put the data into the model to add it to the risk factors that GAEN enables
    *   So we can try and figure out how GAEN variables turn into actual dose which helps us then understand infection risk 
    *   So then we have a probability of infection risk based on GAEN parameters
*   We don’t care as much about infection risk, but rather about infectiousness risk - how likely is it that someone will infect someone else
    *   With that we can use a distribution of incubation periods and how frequently people are asymptomatic, plus the distribution of shedding for those asymptomatic cases. 
    *   Asymptomatic carriers have a long shedding duration, which is problematic. A 14 day quarantine is great when you can test reliably, but given a lack of testing the 14 day quarantine is not quite enough to reduce risk of infectiousness to zero. 
        *   Ideal would be to test everyone before they leave quarantine 
*   One challenge of GAEN (from Country A) is that for GAEN you ultimately need to pick a number based on the attenuation levels
    *   It would be helpful if jurisdictions were able to share their testing data
    *   The authors of the paper would like to know what the distribution is of attenuation data since that can help improve the distance measures
    *   Any measurements people have taken that take distance and then report out attenuation as a result would be helpful (distance as a function of attenuation) 
*   Country A is also collecting and sharing data around how much time each exposed person is spending in each of the three buckets so that collectively they can run analytics on the various buckets and understand it further
*   There’s a lot you can do with these apps so long as you don’t send stuff to the app store. You can use test versions of the app and test entitlements in order to run experiments and get lots of data. 
*   Future API updates from A/G are looking good and the telemetry pieces are becoming more and more important. But essentially the PHA can collect some data that the app can’t collect, the app can collect some data that the PHA can’t, and if you can cross the two data sets it becomes pretty interesting. A/G care a lot right now about making sure that the EN apps are accurate and effective. 
*   There is probably a 10x difference between infectiousness and infectability based on different factors including date to/since symptom onset, environment, and a lot we don’t know. This means that we really should be taking in as many of these things as possible when accounting for our app settings. 
*   We need to understand asymptomatic transmission and this data will be very helpful for that. 

## Measuring Behavior Change

*   After someone gets an exposure notification, how does their behavior change? 
*   In country A if you get an exposure notification you automatically enter the contact tracing cycle and so you get daily symptom checks and follow ups
*   One worry: manual contact tracing doesn’t scale. So if this gets too big Country A might have a challenge
*   Handling tourists is very challenging - the PHA needs to know where people are, if they’re quarantining appropriately, get them to equip an app, etc

## Attenuation

*   There’s also good discussion in the measurements and signal attenuation room on how to get data to correspond to distance
*   Eventually the goal is a machine learning model to get to mapping distance data but we don’t have the underlying data yet
*   Can you extract exposure details out of the app with consent? 
    *   You can see these and read them via the app 
    *   There isn’t an issue with sharing the data with consent, the question is if it can be done with some form of automation. 
    *   Much easier with the people who have been positive. 
    *   Country A uses that data with close contacts as extra metadata and extracts it from the app. So yes, you can access this telemetry easily and safely. 

## How we succeed

*   Researchers need the data from these apps in order to understand how this disease spreads
*   Building in good ways for the apps to share anonymized, aggregated data with researchers and PHAs
*   Ask: please use the transmission risk levels and at least track it
    *   Log the data even if you’re not using it so it can be used in a hypothetical calculation
*   Country A decided to just go with 2m and 15 mins for shipping the app in order to get it out and has promised to circle back over to it as time goes by. But they felt momentum was critical in order for this to happen. 
*   Testing capacity needs to be up fast enough so we’re not doing 7-10 day turnarounds on test results. The app isn’t so helpful without good testing. 

## Interoperability

*   Country A is following the interoperability standard that have been published by eHealth for the EU
    *   Infrastructure will be managed at the EU level
*   How to handle the different android phones? 
    *   Country A did testing on a range of iPhones and Android phones to try and tune the attenuation levels but the testing cycle is long and torturous. Time ended up being the biggest limitation. 

## Q&A

*   Are you looking at people who tested negative in Country A? 
    *   Yes, absolutely. Trying to figure out anything we can with the data we have. So even if they test negative we’re reaching out with with MCT. 
*   State B - with the server-side complexities slowing people down, what is your take on this? 
    *   It’s been hard to have things changing constantly with the API while we’re trying to build the app. So we settled on something for now and built to that and will adapt and evolve once we get something shipped. 

Resources:

*   [https://github.com/immuni-app/immuni-documentation/blob/master/Privacy-Preserving%20Analytics.md](https://github.com/immuni-app/immuni-documentation/blob/master/Privacy-Preserving%20Analytics.md)
*   [Quantifying SARS-CoV-2 infection risk within the Apple/Google exposure notification framework to inform quarantine recommendations ](https://www.medrxiv.org/content/10.1101/2020.07.17.20156539v1.article-info)
