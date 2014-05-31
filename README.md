
Patent Application Publication Notification System
============================

RE: http://hackforchange.org/challenges/uspto-innovation-challenge-patent-application-publication-notification-system/

ABSTRACT
============================

The idea here is to so generate a space and/or API that allows an experienced and otherwise genuinely interested populace to peruse newly (and ‘open for review’) patent applications that match their interest or expertise so they can, in turn, react and inform the patent office on the validity of the patent.

This will be at least a two part infrastructure that …

… begins with a storage space and reactive API that essentially joins folk who register with the service/app
… and boils down key identifications from patent abstracts to match them with.

From there, the end user needs be responsible for submitting the proper forms already provided by the US patent and trademark office.

Services/APIs
============================

Registration and Querying Service
::General

The ‘front end’ service to be created will have to be one that allows folk to register themselves -- not necessarily with personally identifying information -- and their interests, be those interests entities like businesses (aka: apple, HP, boeing, etc) or institutions (aka: MIT, CalTech, et cetera ad nauseam ) OR topics (aka: molecular biology, chemistry, software, et cetera.)

Within this service, a mapping must be generated between individuals and commonly acceptable tags of interest.
For end users, interfaces must be made available for control over privacy, opting in and out of receiving alerts, et cetera.

For cost minimization concerns coming from years of experience from my long term employer, I believe it would be best that the service should NOT proactively disseminate alerts about patent terminology matches to registered users.  It might, perhaps, aggregate a weekly tag-centric newsletter (itself perhaps not PUSHED/SENT but instead made available for RSS feed,) but, primarily, interest parties should have to QUERY the service for updates.  This could be potentially automated, but it puts a little bit more of the burden on the end user, making the service itself more likely to be maintainable.

::General

The ‘back end’ service needs to be capable of noticing and parsing the contents of the USPTO’s weekly snapshots re: newly receive patent applications.

From these snapshots, certain codes can be quickly discerned regarding the overall categorization the application was submitted under… and that categorization would be included in the eventual data application layer interest parties would query at a later time, perhaps as a ‘super tag(?)’

Beyond that, however, the required abstracts from any given application can be parsed for terminology, and while it has been indicated to me by the USPTO representative present today that it’s not at all uncommon for applicants to effective invent words to describe their inventions (a fully understandable quandary applicants will face), it still seems largely true that they will have to describe precisely WHAT it is they intend to patent.  To that end, natural language processing techniques and stemming should be applicable to generate a list of probable tags that apply to the patent.
These tags, then, are saved to a data layer and performant cache.

Each tag aggregates references to pertinent applications and will report these upon query by the end user.


