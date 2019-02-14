# A distributed ledger for land rights in low-income countries

Cadastres. Land title for poor people. It's been a huge problem for centuries, and one aspect of the problem is that cadastres are centralized in opaque government agencies, therefore vulnerable to tampering (for example, the sum of the land titles in circulation in Haiti is said to be around three times the actual surface area of the country&mdash;the average plot of land has three different ownership claims on it). Mitigating this is an incredibly obvious use for a distributed ledger; if everyone has a tamper-proof copy of their land title, even if it's not backed by government authority, it makes it much harder for a government to arbitrarily give the land to one of their cronies. 

Why is this suddenly important or relevant now (early 2019)? Surely someone has thought of this? Well, yes, but it's never been possible to delineate the precise boundaries of smallholder land due to the lack of surveying precision. Here's the new situation:

The latest low-cost GPS devices, released in late 2018 around the $250 mark, are capable of several-centimeter precision, and consumer-grade phones will likely have similar precision in another few months. 

A pair of UBlox GPS receivers retail for $250 each, and there are recently-developed open-source libraries that can implement differential correction with them. Another challenge in this repository deals with implementing differential GPS correction on Android phones; with a concerted effort it's probably relatively inexpensive Android phones being able to survey with sufficient precision&mdash;around the 20cm range&mdash;to create smallholder land ownership boundary polygons. We're already into an era, marked by the release of the latest UBlox GPS unit, in which we can survey small landholdings with $500 worth of kit, and we're about to be able to do it with with a cheap and ubiquitous off-the-shelf phone.

As the surveying capability is here, it's time to start thinking about how we implement the tamper-proof cadastre to document and protect the land title/rights of poor people, smallholders, slum residents, etc. 

