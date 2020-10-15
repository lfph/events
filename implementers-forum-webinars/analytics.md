# Analytics

## LFPH Implementer’s Forum Webinar

### October 6, 2020

This month's theme is analytics, with a focus on what analytics need to be in place in order to measure efficacy and how to get additional data about app performance while maintaining the privacy-by-design approach to app development.

Presenters included two European teams sharing their real-world examples with the group. We had presentations and live Q&A over the course of the hour. 

As with our last Implementer’s Forum event, we followed [Chatham House Rule](https://www.chathamhouse.org/chatham-house-rule) and the event was only open to teams that already have a GAEN entitlement. 


## Glossary
* EN - Exposure Notification
* GAEN - Google-Apple Exposure Notification (API)
* PHA - Public Health Authority
* MCT - Manual contact tracing


## How analytics help us measure efficacy in a European country

*   In their country, a person who gets an exposure notification is asked to call a central hotline to get a risk assessment and be told what the appropriate next steps are 
*   Data is collected in a few different ways: 
    *   From the app and app infrastructure
        *   To preserve privacy, there’s a limited amount of information they can collect
        *   Number of downloads
        *   Number of active users (based on pings to the config server)
        *   Generated verification codes
    *   From outside the app
        *   Number of positive PCR test results
        *   Some data from the manual contact tracing efforts
        *   Reasons for requesting PCR tests when the PCR result is positive
        *   Characteristics of the population, both app users and non, via research
        *   Volume of calls into the hotline
*   This data is rather sparse, but they are still able to figure out some interesting statistics
    *   Number of verification codes generated vs. number of verification codes entered: gives them a sense of the proportion of the total app user population actually sharing out their positive statuses
    *   Number of people with positive PCR tests who got their tests due to having been notified via the app - this helps them estimate the number of chains of transmission broken by the app
    *   Calls to the hotline vs verification codes entered - can provide an estimate of how many people have received notifications via the app before being identified or notified by manual contact tracing
*   They’ve been able to determine that there is pretty good overlap between people identified by manual contact tracing and EN. 
    *   About ⅔ of the identified index cases used the app
    *   About ⅓ of their identified contacts used the app
    *   One question to be answered is what actions a person takes when they receive a notification. They see people getting tests due to these notifications and see the number going up over time. They also see that of the group of people who were identified by both MCT and EN, a small but meaningful percentage of them got their app notification prior to the call from the MCT personnel. 
*   Lessons learned
    *   Think through your monitoring/analytics system from the beginning, not as an afterthought
    *   Use the data that already exists in your system - around MCT, lab results, etc, and feed those into your efficacy models
    *   Find research that is already happening around Covid and public health and take advantage of it - if there’s already a study happening and you can add one or two questions about the app, that’s much easier than launching a fresh study. 
    *   Make sure your operations are actually in good shape - you need the entire system to work smoothly and efficiently for EN to work. Positive test results need to be accompanied by a code and clear messaging, people need to be available to answer calls of those who were notified, etc. The technology working is only one piece of the system working. 
    *   Publicize your early successes to build more traction over time. 

### Q&A 

*   How did you communicate your message to the public and how did you manage sharing analytics data without hurting your privacy-first message? 
    *   Official communication goes through the PHA
    *   The most effective press event they had was where they “closed the circle” and were able to identify people who got tested because of the app
    *   With regards to privacy, the analytics are all aggregate and are also available publicly for study. There isn’t really a way to connect the data being collected to any privacy concerns and so there hasn’t been any backlash around the analytics info
    *   Additionally the code and the documentation is all open source with thorough explanations around what we collect and log as well as how all calculations are done for the reporting. So we have explanations that come alongside everything we do. 
    *   There is thorough university involvement that also vouches for the quality and privacy preserving aspects of the implementation. The university staff serves as oversight for ongoing development efforts to make sure that the privacy-preserving mission continues. 
    *   There is no question that the press asks where we don’t have a well thought-out answer immediately. We create confidence in the system by showing how thorough the planning and development was to preserve privacy. 
*   Has there been demand to track the number of notifications that have been sent? What would that allow you to do in terms of disease surveillance?
    *   This hasn’t been a dramatic issue for this team. There’s agreement that this would be helpful but that data doesn’t contribute to the purpose of the app.
    *   No epidemiologists have been able to convince them that they get useful data from notifications that don’t lead to any action. They only really care about the people who called, not the people who didn’t call.
    *   Would more notifications lead to more calls? Unclear. So from a privacy perspective it’s not got clear enough value. 
    *   Better to find different ways to answer particular questions rather than just collect data for unclear purposes. 
    *   _LFPH Note: There might be value in knowing the number of “dead end” notifications so that you can improve the efficacy of the messaging you deliver in an attempt to get more people to take action based on getting a notification. But there are other ways to test your messaging as well that don’t require this piece of analytics._
*   Have you linked up any of your analytics systems with the app to disease monitoring systems such as case management? 
    *   There are several independent systems we looked at: tracking active users, tracking infoline calls, etc. 
    *   The one place where some data comes together is in the MCT system. They have designed what they call the minimum data set that will be used at the state/province level and it has some basic questions about app use. That’s the only place where there’s any overlap between systems. 
*   How do you know when people get tested _because_ of the app versus _coincidentally?_
    *   They use a few pieces of data here: first, if a patient gets a positive test result the physician needs to fill in a form explaining why they ordered the test. These forms are centralized at the national PHA level. 
    *   It’s more fair to say that they were tested after receiving a notification, not _because_ of the app. So we aren’t positive of how many, but we have a sense that there are some that are happening. 
    *   They also create some incentives for testing because you can get a free PCR test if you have a notification from the app. 
*   Do you  have an estimate of the “true positive” rate? 
    *   They don’t have data about the number of negative tests, so they don’t know what percentage of people who are getting notifications are testing negative. 
    *   So they can’t compare the positive rate for app users versus non-app users
*   Were there challenges around getting buy-in from the state/province level PHAs? 
    *   There’s a lot of communication going on and the PHAs at the state/province level are seeing some value from the app. So while there was occasionally resistance at the beginning, there’s generally alignment now. 
    *   One thing we did at the beginning which we are happy for is that we had only one national system for generating codes and collecting the app data. So there’s more consistency across state/province level than places where verification codes are managed at a lower level, where there can be different policies for every state/province and so that can create problems with your models. 
    *   Homogeneity is really critical, even if you aren’t centralized. If you don’t have that then you can’t get comparable data. 

## Analytics update from Finland

*   Their app has been launched for about a month 
*   When developing the app they were targeting 1 million downloads in the first month - they hit that number in the first day
*   Their current downloads are at about 2.26 million and that means that 40.9% of the population has an app and 51.2% of Finnish smartphones have the app running on them
*   They track the number of daily codes generated. The number of generated codes has been increasing quickly and been somewhat proportionate to the number of cases in Finland. 
*   They send the verification codes via text message and it seems like that is well-received. There are options to get a code via phone call or via paper or a face-to-face meeting, but it appears that well over 90% of people opt in to getting their codes via text. 
*   Around 80% of the codes generated get entered into the app. 
    *   They made the choice to have a single-use only PIN code and require it to be used within 4 hours of being issued. This was a risky design decision but it turns out it has been working pretty well. 
*   They can compare the total number of infections in the country to the total number of codes entered into the app and are finding about 40% of all total known infections also include that person uploading their keys in the app. 
*   Though they can’t tell the number of notifications they send via the app, they accompany their ENs with a link to a symptom tracker. That symptom tracker is web-based so they can identify who is being sent to the symptom tracker via an exposure notification versus some other means. 

### Q&A

*   What are some of the reasons you were able to get such high adoption rates? 
    *   Finns are generally early adopters of tech and have high levels of trust for the government
    *   They’ve been very open with their development - they kept the press updated throughout the whole process and are very open to talking to anyone who wants to ask questions, both in the press and social media.
    *   They had a local group of white hat hackers who were invited to look at the software and give their opinion. There were also local security audits that were made public. 
*   Do you have the same system generating the test codes versus the real codes? There have been reports from elsewhere that analytics get muddied due to the fact that they don’t know if the codes all are connected to positive tests or just to people trying out the system. 
    *   They have a separate dev and prod environment
    *   They have been generating test codes in prod but aren’t seeing it as a problem because the test codes are a small fraction of the total codes issued. They’re aware of the challenges around this and so have taken this into account in their analytics
*   Are there any integrations between the app and manual contact tracing systems? 
    *   The app provides contact information for healthcare and then links people to the symptom tracker
    *   Once they either get a positive test or go to the symptom checker is when they enter the MCT flow
    *   This has been billed from the beginning as a supplement to MCT, not a replacement
*   Why did you create the 4 hour limit around the verification codes? 
    *   This was due to one of the suggestions from a security audit. We use this to prevent people from gathering codes and doing a large threat.
    *   The four hour code also ensures that they won’t have any issues with the codes getting re-used within a short time period. 
*   Are you doing anything to verify that the code is being sent to the right person? 
    *   The health care official is the once using the code generation interface. It’s usually the same person who is reporting the positive test result. Sometimes it is also the manual contact tracer who is also sending the SMS code. There’s a small chance of typos, but otherwise it’s highly unlikely that the code is going to the wrong place. 
*   How does the symptom checker tracking work? 
    *   They just use an extra parameter on the link from the app to the symptom tracker. 
    *   It’s not a secret parameter so it could be abused, but the motivation to abuse the parameter is low. 
