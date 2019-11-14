# Mapping Every Settlement in sub-Saharan Africa

## Vision
**Every person in the world, when arriving at a medical facility or calling for assistance, should be able to describe their origin or location in their own words using familiar local terms, such that those assisting them can accurately convert the location into precise coordinates to act upon.**

This will facilitate contact tracing for outbreak control, disease surveillance, all kinds of emergency response, personal navigation, and delivery of products and services both public and private.

## Specific Goal
We propose to visit every settlement (town, village, hamlet, cluster of houses, etc) in sub-Saharan Africa to take a set of location coordinates using a smartphone GPS reciever and complete a short survey to determine the locally-used description of the location and its place within the hierarchy of locations in the region.

In other words, we visit every village, take a GPS point, and ask:
- The name of the village (and any alternate names),
- The administrative divisions it belongs to (province, district, chiefdom, prefecture, section, county, etc)
- Contact names and numbers for local officials (village chief or equivalent)
- Presence and type of healthcare facilities

This makes it possible to produce both maps and gazetteers (indexes) enabling healthcare personnel and emergency responders to correlate a verbal location from a person to a set of coordinates.

## The Problem
Throughout most of sub-Saharan Africa and other low-income areas, settlement names are often non-unique (for example, there are an estimated 537 places called "Majengo" in Tanzania&mdash;just as there are dozens of places called "Springfield" in the United States). Many settlements have multiple names (for example in several tribal languages). Spelling and pronunciation are often not standardized. For a person to describe a location by simply giving the name of the village or town is not sufficient to identify the location.

This problem&mdash;that a described location is rarely sufficient to identify a place&mdash;makes public health management and outbreak control especially difficult. When one cannot ascertain the exact village that an Ebola patient has just come from, it is risky and time-consuming to perform the all-important contact tracing. This is to say nothing of the difficulty of surveillance for less spectacular illnesses, responding to other emergencies, or even delivering commercial products.

A rough estimate indicates that there are about 500,000 settlements in sub-Saharan Africa. The great majority of them have not been mapped in person by a surveyor with a GPS receiver (even a simple, inexpensive smartphone GPS). This leaves hundreds of millions of people without the spatial knowledge infrastructure that would enable the most basic practice of public health, as well as all of the economic and practical benefits of knowing and communicating one's location. 

## The Way Forward
Adding hierarchical administrative divisions is the most common way to disambiguate (Springfield in Sangamon County, Illinois, USA is an unambiguous location). However, in low-income countries the polygonal boundaries of administrative divisions are often not accurately drawn. Therefore without actually visiting the village and asking the inhabitants which divisions they consider themselves part of, it is frequently impossible to correctly identify them from their names.

Our experiences in several African countries suggest that a fairly consistent 20% of settlements are in a different administrative area than the official map boundaries suggest, and we have even encountered a few cases where settlements are on the wrong side of *international* boundaries)! In some cases, the official administrative divisions are not relevant to citizens, they identify themselves as belonging to traditional, informal, or linguistic/tribal groupings rather than colonially-imposed divisions. Some communities are nomadic and refer to temporary locations or migration routes. Others  Regardless, the most effective way to discover how people describe their homes and locations is to ask them, rather than querying official source. 

Our program is quite straightforward: to find out the names of half a million villages, how they are described, and what larger communities they belong to, we'll simply go and ask. 

We do not propose to introduce an external system of nomenclature. The [United Nations P-Codes](LINK) work fine for coordinating relief cluster logistics and donor reporting, but local people do not use or value them. Addressing systems like [WhatThreeWords](what3words.com) can be very useful for coordinating commercial and aid actors, but it is unrealistic to expect rural Africans to abandon centuries of traditional language and meaningful place-names for an pile of arbitrary phrases built by a pseudo-random algorithm. Our intention is to work together with local people to adapt our understanding&mdash;and the markings on maps&mdash;to their reality.

We will not ask local people to adapt to our system of naming and identifying places. We will adapt the global system of location to the language and terms of local people. 

## Operational Plan
SEE SPREADSHEET

It is only in the last few years that Android-based smartphones with GPS recievers have become ubiquitous in sub-Saharan Africa. While most people in the poorest countries do not have smartphones, it is generally the case in 2019 that _almost any given village_ has at least one or two GPS-capable Android devices (and often more, as even where there is no mobile network people use them as cameras, media players, and to play games).

Coupled with the wide availability of inexpensive Asian-manufactured motorcycles (also a relatively recent development), the ubiquity of smartphones changes village mapping from a monumentally difficult and expensive endeavor to a surprisingly feasible one. 

We'll support local people to map their own communities by providing them with free software (OpenDataKit), training, and money to travel to every village on the continent.

The basic method is:

- Travel to a country capital, manage basic permissions and security arrangements, and recruit a manager and administrator.
- From the capital, travel to central regional hub towns.
- In these towns, ask local leaders to put out the word that there is an opportunity for short-term work for clever people with smartphones, as well as competent motorcycle riders.
- A crowd will gather. Select a (representative and gender-balanced) group from this crowd that have working Android devices with functional GPS receivers, and get them to install OpenDataKit (either from the Internet, from a local micro-server if Internet is not available, or by Bluetooth transfer).
- Get them to fill out a sample survey. Choose those who:
  - Fill out the survey correctly
  - Help others (the natural leaders are quite easily spotted at this point)
  - Represent a good cross-section of the community
- Get the selected people to choose motorcycle riders, and verify that the motorcycles have license plates, brakes, and helmets (this can be quite time-consuming)
- Train them by going to a few nearby villages and filling out the mapping survey together. Iron out bugs by checking the data immediately. Prioritize ensuring that they _ask_ the villagers where they are rather than _telling_ them.
- Using satellite imagery and tracing done by Missing Maps volunteers to identify all roads and settlements, send the mappers out to systematically visit every human habitation in the area. Allow some overlap for quality checking.
- As the team completes the area near their own homes, add more mappers who live at the edges of the area; these new recruits will cover the area near _their_ homes. They are onboarded quickly because they learn from the others. The best of the mappers are retained as trainers and supervisors and move with the project, the others are thanked, given their pay, and return home.


This process was [used in Sierra Leone](https://www.newsweek.com/2017/11/10/slums-missing-maps-map-international-poverty-695381.html) to map two of 13 districts in the country, and resulted in [an extraordinary increase in accuracy of patient origins](https://academic.oup.com/trstmh/article/113/9/572/5533380) within the local healthcare system. 

## Why Open Mapping?
### Aren't there companies working on this?
Several high-quality proprietary mapping applications/databases exist, notably Google Maps, Apple Maps, and Bing Maps (Microsoft's offering). Why are we not relying on them to fill the need for local map information?

Google is moving quickly to map many cities in Africa. Microsoft and Apple actually use quite a lot of OpenStreetMap data under the hood of their map offerings (both include a copyright notice crediting the OpenStreetMap contributors) and contribute substantially to the OpenStreetMap project with imagery, data quality support, and direct donations. However, these companies are ultimately motivated by commercial concerns; they earn money based on providing information (and advertising) to people with money to spend. The location of the nearest barista coffee shop from a given village in rural Congo is not commercially valuable information, and is therefore not the focus of commercial mapping efforts, open or proprietary.

While the gap between map quality in African cities and those in high-income countries is closing in both open and proprietary platforms, rural areas in low-income countries, especially in Africa, are being left behind.

### Why OpenStreetMap specifically?
Open map data is more effective for use in public health than proprietary information because it can be used outside of proprietary platforms, making it available for use by public health practitioners with less risk to the privacy and confidentiality of patient data.

The terms of service of Google Maps forbids use of the raw data offline; all use must be within the ecosystem of services provided or authorized by Google. So if a public health officer wishes to correlate patient origin data from a clinic with Google map data, they must upload the patient data to a platform owned by Google or one of their commercial partners. It is risky and generally problematic in terms of medical ethics to upload patient data to an internet-based platform, not to mention difficult to access Web-based services from rural Africa.

OpenStreetMap data, on the other hand, can be downloaded freely (both free of charge and free of restrictions on what can be done with it). 

## Why Private Funding?
Agencies like the Gates Foundation, Medecins Sans Frontieres (MSF), and the Red Cross have an interest in this data. One might ask why they are not funding it?

In fact both MSF and the Red Cross movement have contributed money and resources to this effort. In several countries, they have actually funded small-scale versions of exactly this activity. The first real implementation of this agile, community member and motorcycle-based mapping was done by an MSF team in Sierra Leone during the Ebola outbreak of 2014-2015. However, these humanitarian agencies have relatively narrow mandates; their donors expect most of their funds to go to core operations. So while MSF and the Red Cross remain supporters, partners, and even donors to the effort, they will not fund the entire continental effort.

We do hope that the Gates Foundation will be willing to contribute to this effort. However, the methodology we propose is unusually lightweight. While it is much less expensive than a traditional development-style effort for the expected outcome, it requires that donors be prepared to be flexible in their reporting requirements and acceptance of risk.

If the project is done in the manner of traditional development aid, securing governmental and instutional partnerships alone will cost more than the entire propose project budget. We propose to work directly with African citizens, not governments or development-sector elites. This requires donors that won't be risking their entire portfolios by supporting such process that could be perceived by many in the sector as a maverick initiative (it's not; it's a citizen-based initiative that does not undermine governmental or aid sector responsibilities, but it's nevertheless a conceptual leap for most traditional donors). 

## How is the data sustainable?
Villages change, and map data can get out of date quite quickly. From our work in urban African environments, the Missing Maps has seen that the key to data sustainability is _data use_.

Once a set of map data becomes sufficiently complete to be operationally useful to many agencies, it becomes much easier to solicit the resources to maintain it. The contributions of Apple and Microsoft to OpenStreetMap are a case in point; they began using OpenStreetMap because it was the only dataset complete enough to compete effectively with Google's offering. Once this worked for them, they began investing in supporting the dataset.

While we don't expect the same type of support for rural areas (because the commercial incentive is less compelling), we nevertheless expect that a complete, accurate, and above all usable dataset of all settlements in sub-Saharan Africa will be so useful to both public and private sector users that, once they begin using it, some will be unwilling to let it degrade.

## Random leftover text for cleanup

By focusing on the basics, the data collection can move fast, and the whole of Sub Sahara Africa can be covered in a timeframe of two years.

People will always come before data. If there is any specific risk for people in the communities we wish to map, data will not be collected and/or publicly shared.

A key risk is mission creep: Temptation to fold in other aspects of mapping / data collection beyond its original scope of minimal viable geodata with an initial focus on public health. Keeping the focus on the basics is key.
