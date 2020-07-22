# GAEN Measurements and Signal Attenuation


## LFPH GAEN Symposium Breakout Session


### Resources/references



*   [GAEN Explorer](https://github.com/billpugh/GAEN_Explorer)
*   [Testing apps for COVID-19 Tracing, Doug Leith and Stephen Farrell](https://down.dsg.cs.tcd.ie/tact/)
*   [DP-3T Exposure Score Calculation summary](https://github.com/DP-3T/documents/blob/master/DP3T%20-%20Exposure%20Score%20Calculation.pdf)
*   [PEPP-PT Exposure Measurements](https://github.com/pepp-pt/pepp-pt-documentation/tree/master/12-proximity-measurement)
*   [SwissCovid ExposureScore](https://github.com/admin-ch/PT-System-Documents/blob/master/SwissCovid-ExposureScore.pdf)
*   [contacTUM paper](https://arxiv.org/abs/2006.16960)


### Survey



*   [Survey on measuring attenuation and duration in GAEN](https://forms.gle/zKJvFSiBJcN19gXA9)
    *   asking teams working with a PHA to deploy an app to fill out the survey. App names and countries will not be published. 


### Presentation



*   [Measurements using GAEN Explorer](https://docs.google.com/presentation/d/1_adF7jlFcY1tt5FP8AkWaQYvgE-6jUWu8RInoGK4Olw/edit?usp=sharing), by Bill Pugh
    *   Open Source tool - iOS only
        *   Requires entitlement needed for iOS, but anyone with the entitlement can run it, just rebrand with your own name
        *   Doesn’t use/require servers to be set up in order to do the analysis
        *   Uses entitlements only available in development, gets very precise info about the attenuation (2 dB precision)
            *   Example, for any one exposure, it will call the method to analyze it about 9 different times in order to analyze it with different attenuation thresholds
        *   Data viewed on phone or exported for analysis
    *   Early experiment results - work in progress
        *   Done dozens of tests, many with 8 iPhone SE’s for a period of 30 min
        *   Summary of results - promising but frustrating
        *   Bodies interfere
        *   BLE signal strength isn’t a uniform sphere around phone, noted big differences on right or left side of the phone
        *   If you only look at attenuations &lt;60 dB, you will miss a lot of encounters
        *   If you include attenuations of >70 dB, you are going to include a lot of distant encounters
        *   Sweet spot is attenuations around 62 to 64 dB, but a lot of caveats there
    *   Experiments
        *   Results conducted at home and at UMD, with help of colleagues
        *   Will be written up as a research report, spent much of last 2 weeks learning how to best design and set up experiments
        *   With a fixed design, results are fairly consistent/repeatable
        *   Have done experiments on the patio, with phones both horizontal and vertical orientations, also flat on surface.  At 4 foot intervals.
        *   iOS 13.6 reduces noise
        *   Orientation matters - early results indicate that orientation can make a significant difference.  4-10 dB difference.  Further study to be done
        *   Experiment with putting phones in different pockets while sitting at a table
            *   Phone in back pockets did not get very good signals
            *   Whether or not to include warning in user guides about not putting phones in back pockets is something that everyone will have to decide
            *   Relevant paper provided in the comments of this document:
                *   P. C. Ng, P. Spachos, and K. Plataniotis, “COVID-19 and Your Smartphone: BLE-based Smart Contact Tracing,” arXiv [cs.LG], 28-May-2020 [Online]. Available: [http://arxiv.org/abs/2005.13754](http://arxiv.org/abs/2005.13754)
                *   Basically they show that the likelihood p(R | D, C), where R is the observed RSS, D is the distance, and C is the context of the sender and receiver (eg sender=phone-in-hand, receiever=phone-in-pocket), is very dependent on C.
                *   See the plots of their data here: [https://github.com/pc-ng/rss_HumanHuman](https://github.com/pc-ng/rss_HumanHuman)
                *   MIT Lincoln Labs has also done similar studies (not sure if results are public or not).
                    *   MIT LL paper: [https://arxiv.org/abs/2006.15711](https://arxiv.org/abs/2006.15711)

#### Discussion

*   Someone else in the breakout has done a lot of experiments as well - recommends using Android phones rather than iPhones.  Data is a lot more easily accessible. You can actually read the logs and attenuation values directly.  
*   It is very important to use the attenuation values provided by the GAEN framework rather than measuring signal strength directly. All phone broadcast at different signal strengths
    *   Tremendous amount of work done to calibrate phones. Android is challenging because there are many types of phones.
*   Orientation matters - antennas are placed in locations where your hand won’t typically grasp the phone - on the top or front of the phone
    *   Google had documented the methodology for doing the calibration for how you orient the phones relative to each other so that you get consistent results 
    *   Phones should not block each other, affects signal strength
*   Trade-off between precision and recall - not just simple accuracy 
    *   [Summary of the data used to set the thresholds in the SwissCovid app](https://github.com/admin-ch/PT-System-Documents/blob/master/SwissCovid-ExposureScore.pdf)
    *   Best way to look at the data is a precision recall curve (page 5 of document linked above)
    *   Trade-off catching people between 2 meters vs not catching people between 2 meters
        *   Can’t optimize so that you get 100% for the first and 0% for the second, so you know it’s a trade-off
*   Question: a lot of women wear handbags - has this been thought about?
    *   Answer: yes, also men may put phone in a backpack
        *   It would be great to determine all of this, there have been discussions with Apple and Google about this
        *   In the end, keep in mind that this process is extremely approximate
        *   15 min/2 meter guidelines are extremely precise and in reality it’s much more approximate
*   Almost every question that has been asked outside has been discussed inside Apple/Google - don’t assume that they haven’t thought about it just because they haven’t publicly commented on it
*   Question: Ultrasound issues?  Just about microphones and privacy?
    *   Answer: Turning on the microphone in a privacy app will be a difficult sell. Android phones when you turn on bluetooth, you have to give permission to turn on locations services, which has caused some concerns with the public
*   Question:  Recall - what does that mean?
    *   Answer: Recall is defined as a fraction of beacons from phones within the distance that had an attenuation equal or smaller than the threshold.  Basically, false positives.  
*   Question: Is the API working in all 3 states (foreground, background, and terminated)? 
    *   Answer: Bluetooth signal is received and recorded continuously as long as you haven’t turned off the scanning
    *   Separate issue -  if you're writing an app, you really want to make sure that it wakes up periodically every two to four hours, whatever it is, to download new keys and check them.
    *   If you’re writing an app, talk to Google/Apple about ensuring that you get the background time you need in order to process things
*   iOS is going to release the API as part of the OS?
    *   Answer: Can’t talk about anything at this point
*   Has anyone done a study of the human body being 80% water and what happens in terms of accuracy?
    *   Answer: It’s easy to do a reproducible experiment with phones at specified distances.  Really hard to do something repeatable with human bodies.  People moving around complicate things. The studies are important, but more noisy than the static experiments
    *   There are sensors available to use for experiments (ultrawide band sensors)
        *   Could give bluetooth and decawave sensors to people in a study
        *   Are there other sensors available?
        *   New iPhones have ultrawide band radios in them
    *   Possible to get detailed logging out of iPhones, not just Androids
*   Looking at false positives and false negatives, looking for a classifier for distance
    *   Can take distance, map to expected varion density
*   Someone spoke about handling attenuation as a parameter when estimating risk
    *   Opposed to using High/Medium/Low, they estimate the dose
    *   Look at different attenuations related to different distances
    *   They use a dose response curve
    *   Can link with public health messaging
    *   Question: What is the user experience?  How do you display this information to users with appropriate context to get them to do the right thing?
    *   Question: Breathing rate of the person ingesting the varions - can you adjust for age/lifestyle/weight/gender/etc?
        *   Answer: important to consider and are incorporating it into research


### Presentation



*   **Technical Challenges for BLE-based contact tracing presentation:**
    *   Aim: highlight the variables driving the GAEN attenuation stats, and how to assess the likely impact on false positives and negatives
    *   We are all familiar with the fact that we expect bluetooth signal strength to decrease with distance
    *   Challenge: Body effects and signal penetration - possible to be far away and detect high power, possible to be very close and detect low power, possible to be very close and detect high power but with a window or wall between (so no/low risk)
    *   Real life walk test (walking away from a BLE transmitter and back again) - clear line of sight
        *   WIFI scanning presented a problem (impossibly loud, 10x more than you’d expect) - turning it off reduced noise
    *   Watch out for leakage between internal radios (OS can stop this with scheduling)
        *   Happens on some phones but not others
        *   Hopefully Apple/Google will bake it into the protocol
    *   High “noise” levels - 3 “advertising channels” can measure signal strength, a smartphone is reporting a measurement from one of those 3 channels - when BLE devices “advertise” themselves they constantly hop between the channels
    *   Hack-up yourself some custom transmitters - selectable channels!
        *   Static “single channel” transmitter and smartphone receiver, only one advertising channel in use, see a much finer signal strength
    *   Multipath interference - signals bouncing off stuff 
    *   Simulations can help to answer questions like “What should the GAEN beaconing interval be?”
        *   Waiter scenario using different update intervals provide varying levels of false positives and negatives. 15 min exposure within an hour, not necessarily all at once


#### Comments



*   Slack Comments
    *   Discussion about what is epidemiologically significant regarding accuracy in capturing short interactions and the fact that we don't know - those small interactions can still contribute dose and dose can accrue over many small interactions. In my opinion, I don't think we can discount the importance of short or variability in distance over an overall interactions quite yet.
        *   Indoors vs outdoors seems like a very important distinction especially considering the growing amount of evidence of aerosol transmission - any way of getting this information for attenuation or no?
    *   Are we over-rotating on Bluetooth Low energy instead of looking at the problem more holistically?
        *   For example, using the Satellite signal strength you can do a pretty good job of indoor/outdoor.
        *   And indoor/outdoor is a very material impact on transmission.


#### Discussion:



*   We also need to look at battery drain
*   Question: Students living in dorms, phones by the side of the bed.  Student in the next room over, on the other side of the wall, with their phone nearby.  There could be a many hour exposure due to close proximity in dorms.  Has anyone looked at this?
    *   Answer: no data handy but seems like a good thing to look at
        *   You might decide that if a phone is on a flat surface for several hours, it might not be a good proxy to someone’s location
        *   If someone is infected in a dorm, may not be a bad idea for neighbors to get tested anyways
    *   Answer: there is attenuation drop off between walls
        *   Can look at the different wall materials
    *   Answer: air circulation is recently being discussed, so dorm room proximity could affect infection
        *   Noisy bar where people are shouting is probably one of the more risky locations on a college campus
        *   If people were okay with turning on a microphone, knowing the ambient noise and if people were shouting could be very relevant
*   Question - People are starting to use the buckets instead of just the attenuation levels?
    *   Answer: Yes, instead of just the attenuation and duration risk
    *   Some people might be using both, but the impression is at least 90% of the people who are writing apps are using the attenuation threshold as part of their way of doing it.
