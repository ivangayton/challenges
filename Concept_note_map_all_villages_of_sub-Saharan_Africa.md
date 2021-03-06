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

This data will be uploaded to free repositories such as [OpenStreetMap](https://www.openstreetmap.org) and the [Humanitarian Data Exchange](https://data.humdata.org/) and provided directly to healthcare systems.

## The Problem
Throughout most of sub-Saharan Africa and other low-income areas, settlement names are often non-unique (for example, there are an estimated 537 places called "Majengo" in Tanzania&mdash;just as there are dozens of places called "Springfield" in the United States). Many settlements have multiple names (for example in several tribal languages). Spelling and pronunciation are often not standardized. For a person to describe a location by simply giving the name of the village or town is not sufficient to identify the location.

This problem&mdash;that a described location is rarely sufficient to identify a place&mdash;makes public health management and outbreak control especially difficult. When one cannot ascertain the exact village that an Ebola patient has just come from, it is risky and time-consuming to perform the all-important contact tracing. This is to say nothing of the difficulty of surveillance for less spectacular illnesses, responding to other emergencies, or even delivering commercial products.

A rough estimate indicates that there are about 500,000 settlements in sub-Saharan Africa. The great majority of them have not been mapped in person by a surveyor with a GPS receiver (even a simple, inexpensive smartphone GPS). This leaves hundreds of millions of people without the spatial knowledge infrastructure that would enable the most basic practice of public health, as well as all of the economic and practical benefits of knowing and communicating one's location. 

## The Way Forward
Adding hierarchical administrative divisions is the most common way to disambiguate (Springfield in Sangamon County, Illinois, USA is an unambiguous location). However, in low-income countries the polygonal boundaries of administrative divisions are often not accurately drawn. Therefore without actually visiting the village and asking the inhabitants which divisions they consider themselves part of, it is frequently impossible to correctly identify them from their names.

Our experiences in several African countries suggest that a fairly consistent 20% of settlements are in a different administrative area than the official map boundaries suggest, and we have even encountered a few cases where settlements are on the wrong side of *international* boundaries)! In some cases, the official administrative divisions are not relevant to citizens, they identify themselves as belonging to traditional, informal, or linguistic/tribal groupings rather than colonially-imposed divisions. Some communities are nomadic and refer to temporary locations or migration routes. Others  Regardless, the most effective way to discover how people describe their homes and locations is to ask them, rather than querying official source. 

Our program is quite straightforward: to find out the names of half a million villages, how they are described, and what larger communities they belong to, we'll simply go and ask. 

We do not propose to introduce an external system of nomenclature. The [United Nations P-Codes](https://www.humanitarianresponse.info/applications/data/document/pcode-implementation) work fine for coordinating relief cluster logistics and donor reporting, but local people do not use or value them. Addressing systems like [WhatThreeWords](https://what3words.com/) can be very useful for coordinating commercial and aid actors, but it is unrealistic to expect rural Africans to abandon centuries of traditional language and meaningful place-names for an pile of arbitrary phrases built by a pseudo-random algorithm. Our intention is to work together with local people to adapt our understanding&mdash;and the markings on maps&mdash;to their reality.

We will not ask local people to adapt to our system of naming and identifying places. We will adapt the global system of location to the language and terms of local people. 

## The Proposed Project
In 2017, the Missing Maps project piloted this methodology in [in Sierra Leone](https://www.newsweek.com/2017/11/10/slums-missing-maps-map-international-poverty-695381.html). Two of 13 districts in the country were mapped, and it resulted in [an extraordinary increase in accuracy of patient origins](https://academic.oup.com/trstmh/article/113/9/572/5533380) within the local healthcare system.

For approximately USD$7M, we hope to replicate this project on a continental scale, visiting and mapping every inhabited area in 46 countries, reaching 1 billion people in just over 500,000 settlements in 24 months.

[Details of the budget, operational plan, and assumptions can be found on the Web-based spreadsheet here](https://drive.google.com/file/d/1j4nLHKWw3fUFtjSvSYTKNNE3avzPQBKv/view?usp=sharing). _NOTE: this document can be viewed and commented upon by anyone who has the link, but editing is restricted._

Here is a summary of projected costs:

| Item                                     | Cost       |
|------------------------------------------|-----------:|
| Senior managment incl. Travel and accom  | $630,000   |
| regional managers incl. Travel and accom | $594,000   |
| Local supervisors                        | $426,800   |
| Local team leaders                       | $633,600   |
| Enumerators wages and motorcycles        | $2,395,140 |
| Country offices                          | $370,000   |
| Data analysts                            | $400,000   |
| Digitizers                               | $253,440   |
| HQ and Project Management                | $605,945   |
| Total                                    | $6,308,925 |

## Operational Plan

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
- The resulting data is then uploaded to [OpenStreetMap](https://www.openstreetmap.org) where it becomes an open public resource, as well as to the [Humanitarian Data Exchange](https://data.humdata.org/) where it is similarly open and freely available but more neatly packaged for technical use.
- Gazetteers are made specifically available to Ministries of Health and healthcare facilities (Ministry, Non-Governmental Organization, and private) to improve understanding and use of patient origins for public health.

## Why Open Mapping?
### Aren't there companies working on this?
Several high-quality proprietary mapping applications/databases exist, notably Google Maps, Apple Maps, and Bing Maps (Microsoft's offering). Why are we not relying on them to fill the need for local map information?

Google is moving quickly to map many cities in Africa. Microsoft and Apple actually use quite a lot of OpenStreetMap data under the hood of their map offerings (both include a copyright notice crediting the OpenStreetMap contributors) and contribute substantially to the OpenStreetMap project with imagery, data quality support, and direct donations. However, these companies are ultimately motivated by commercial concerns; they earn money based on providing information (and advertising) to people with money to spend. The location of the nearest Starbucks from a given village in rural Congo is not commercially valuable information, and is therefore not the focus of commercial mapping efforts, open or proprietary.

While the gap between map quality in African cities and those in high-income countries is closing in both open and proprietary platforms, rural areas in low-income countries, especially in Africa, are being left behind.

### Why OpenStreetMap specifically?
Open map data is more effective for use in public health than proprietary information because it can be used outside of proprietary platforms, making it available for use by public health practitioners with less risk to the privacy and confidentiality of patient data.

The terms of service of Google Maps forbids use of the raw data offline; all use must be within the ecosystem of services provided or authorized by Google. So if a public health officer wishes to correlate patient origin data from a clinic with Google map data, they must upload the patient data to a platform owned by Google or one of their commercial partners. It is risky and generally problematic in terms of medical ethics to upload patient data to an internet-based platform, not to mention difficult to access Web-based services from rural Africa.

OpenStreetMap data, on the other hand, can be downloaded freely (both free of charge and free of restrictions on what can be done with it). 

## Why Private Funding?
Agencies like the Gates Foundation, Medecins Sans Frontieres (MSF), and the Red Cross have an interest in this data. One might ask why they are not funding it?

In fact both MSF and the Red Cross movement have contributed money and resources to this effort. In several countries, they have actually funded small-scale versions of exactly this activity. The first real implementation of this agile, community member and motorcycle-based mapping was done by an MSF team in Sierra Leone during the Ebola outbreak of 2014-2015. However, these humanitarian agencies have relatively narrow mandates; their donors expect most of their funds to go to core operations. So while MSF and the Red Cross remain supporters, partners, and even donors to the effort, they will not fund the entire continental effort.

We do hope that instutions like the Gates Foundation will be willing and able to contribute to this effort. However, the methodology we propose is unusually lightweight. While it is much less expensive than a traditional development-style effort for the expected outcome, it requires that donors be prepared to be flexible in their reporting requirements and acceptance of risk.

If the project is done in the manner of traditional development aid, securing governmental and instutional partnerships alone will cost more than the entire propose project budget. We propose to work directly with African citizens, not governments or development-sector elites. It's a citizen science-based initiative that does not undermine governmental or aid sector responsibilities but is nevertheless a conceptual leap for most traditional donors who expect close operatioal collaboration with government and UN structures. 

## How is the data sustainable?
Villages change, and map data can get out of date quite quickly. From our work in urban African environments and a few preliminary implementations of the project discussed here, the Missing Maps has seen that the key to data sustainability is _data use_.

Once a set of map data becomes sufficiently complete to be operationally useful to many agencies, it becomes much easier to solicit the resources to maintain it. The contributions of Apple and Microsoft to OpenStreetMap are a case in point; they began using OpenStreetMap because it was the only dataset complete enough to compete effectively with Google's offering. Once this worked for them, they began investing in supporting the dataset.

While we don't expect the same type of support for rural areas (because the commercial incentive is less compelling), we nevertheless expect that a complete, accurate, and above all usable dataset of all settlements in sub-Saharan Africa will be so useful to both public and private sector users that, once they begin using it, some will be unwilling to let it degrade.

## Security
People will always come before data. If there is any specific risk for people in the communities we wish to map, data will not be collected and/or publicly shared.

There are two security concerns here: the security of the people doing the mappping, and the security of the population being mapped. In this section we'll focus on the mappers, with the discussion of the impact on the population in the following section addressing project ethics.

Undertaking a mapping project of this scale necessarily creates risks. The key risks we have identified (and in some cases experienced) in previous projects have been:

- Motorcycle accident
- Other accidents related to travel in deep rural areas (snakebite, exposure to elements, river crossings, etc)
- Robbery
- Deliberate targeted violence by population or armed groups

None of these risks can be eliminated. However, they can be mitigated. The project will implement a security plan for each context (at least one per country, in some cases per region within a country) addressing the _specific_ risk profile in each area. The most universal key principles are:

- Training, supervision, and support for motorcycles and riders.
- Insurance covering injury or illness incurred in the course of mapping
- Use of local people to map their own regions&mdash;very limited movement of mappers from one region to another. People map where they are already living and moving around; we provide them with the resources, knowledge, and means to do so rather than sending in outsiders.
- Ongoing dialogue with communities.

## Ethics
Not everyone wishes to be on the map. In some cases, being mapped can put individuals and communities at risk. Our intervention is based on three foundational principles:

1. Informed consent.
2. The precautionary principle; we are responsible for a duly diligent effort to anticipate potential harm and refrain from acting where we cannot do so or mitigate in collaboration with the affected commuinity.
3. Community involvement. We map with, not for, communities.

While it is not possible to interview every single individual in all mapped settlements (which would essentially amount to the entire rural population of sub-Saharan Africa), it is possible to liaise with communities in such a way that the wishes and well-being of the local people are respected. A fuller discussion of the issue of consent and mapping is [here](https://docs.google.com/document/d/1p9L3q4JXMDPmS-NFCLWMkHFapaBQM5Se6dJmdKHwu-Y/edit?usp=sharing).

Similar to the security management mentioned in the previous section, a ethics and impact assessment will be done in each context (usually countries, in some cases regions within countries). 

## Programmatic Risks
A key risk is mission creep: Temptation to fold in other aspects of mapping and data collection beyond its original scope of minimal viable geodata with an initial focus on public health. Attempting to turn a basic mapping visit into a detailed vulnerability assessment of each visit increases training and survey time exponentially (our rule of thumb is that each additional question doubles the training and survey time). As much as it would be nice to gather data on education, water, economic development, sanitation, and so forth in every village, keeping the focus on the basics is key to the project's feasibility.

The balance between a relatively independent community mapping or citizen science style intervention versus a more traditional multi-stakeholder development-sector style project is tricky. Too independent and the data risks being ignored by key potential users (Ministries of Health and UN or NGO health organizations). Projects may even be blocked altogether by governments or development agencies that feel threatened by data and projects that seem out of their control. On the other hand, embedding too deeply with government or the development sector can cripple this type of project. Often such actors will prefer to choose the participants based on criteria not related to effectiveness and require lengthy disussions (and expenditures) before any type of activity can begin. The precise balance required varies by context, but a rule of thumb is to engage as much as possible with government and aid actors in discussion of public health, strategy, and data use, and as little as possible in operational matters.

Probably the most serious risk is to map every village, only for the data to go largely unused. While we anticipate a great many uses for the data, our intention is to focus intently upon the public health use-case which is relatively well-understood and compelling. Partnerships with healthcare systems are critical here. Given that the Missing Maps already involves key health actors such as Medecins Sans Frontieres (who will be part of this effort) and the Red Cross/Red Crescent movement, there's a reasonable user base already more or less in place. However, translating this to broad Ministry of Health utilization across the continent will be a key challenge and will require more than just creating a nice map. 

## Team
[**Ivan Gayton**](https://www.linkedin.com/in/ivan-gayton-a6081b29?originalSubdomain=ca) spent 13 years working with Medecins Sans Frontieres (MSF) as a logistician, Head of Mission, Humanitarian Affairs Advisor, and Innovation Advisor. He founded the [Missing Maps project]() a [collaboration between Medecins Sans Frontieres, the Red Cross, and the Humanitarian OpenStreetMap Team](https://www.theguardian.com/cities/2014/oct/06/missing-maps-human-genome-project-unmapped-cities).

[**Ka-Ping Yee**](http://zesty.ca/cv.html) is a software engineer with a career focus on humanitarian work.

[**Hassan Valji**](insert link here) needs to put something about himself here.

[**Mike White**](insert link here) needs to big himself up too.

[**Anne Connelly**](https://www.anneconnelly.ca/) should also write something.

[**Doric Mugusi**](https://www.linkedin.com/in/dorica-mugusi-71a521166/?originalSubdomain=tz) works for the Humantiarian OpenStreetMap Team in Tanzania, and has participated in a motorcycle mapping initiative to identify villages for mini-grid electrification.

[**Ed Monk**](https://academic.oup.com/trstmh/article/113/9/572/5533380) is a physician with a specialization in public health. He led the medical aspect of the motorcycle mapping in Sierra Leone that resulted in 97.1% of patients in a rural African hospital having a properly determined geographical origin. 

