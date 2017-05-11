# Android-based server appliation for mobile data collection

Mobile data collection has become incredibly powerful and appropriate for local settings in low-income countries. Many people have succesfully deployed things oike OpenDataKit in astoundingly low-resource settings. Android phones are increasingly ubiquitous throughout, for example, sub-Saharan Africa, making it possible to do sophisticated data collection with what is essentially local technology: the phones that people already have in their hands!

However, the paucity of reliable connectivity remains an obstacle. Getting a group of local data collectors set up with Internet connections to upload their data is arduous! Yes, you can get people a data package for their SIM card (if they have one; some phones are used purely as MP3 and video players or game consoles), but can you assure that the local tower has data enabled? Or that the phone, suddenly finding itself online, won't immediately download half a GB of updates (and/or porn), consuming the data package quickly? And how long will it last even if this doesn't happen?

The answer many of us have come to is local servers. Some use a virtual machine on a laptop, accessible via the wifi on an access point serving both the laptop and all of the phones, other use dedicated micro-servers like this https://github.com/ivangayton/ODKAggregateOnEdison, and some designate one phone to have a data package and provide a hotspot for all the others (which, by the way, exacerbates the problem of unintended update downloads, as most of the phones in the wild in Africa will excitedly take advantage of a wifi connection to update themselves, not realizing that they're just depleting another phone's limited data allotment). The main problem with local servers is that they aren't really locally available; you need to bring some kind of kit from the capital city, or even from abroad, to be the aggregate server. Implementing something like ODK Aggregate or POSM (https://github.com/posm) on a locally-available Android phone would make it easier to scale local data collection efforts by removing that external hardware dependency.

### Resources and skills needed
- Android development
  - Particularly implementation of Web servers on Android
- OpenDataKit knowledge
- Access to cheap Android phones available in African markets
- Hard liquor in substantial quantities
