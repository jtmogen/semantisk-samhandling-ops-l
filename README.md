# Semantic Interoperability in Norwegian Agriculture

Semantic interoperability is the ability of computer systems to exchange data, in a well defined manner and with unambiguous meaning. Improving data exhange between and within organisations enables greater data quality and less cost in moving and understanding data. This in turn leads to improved and new business processes that directly improve the industry. 

# Background

OPS-Landbruk sees that like most industries agriculture and general land use actors are in greater need to sharing and understanding the common data elements that make up their digital worlds. 

Based on the guidelines defined at digdir.no https://www.digdir.no/digital-samhandling/rammeverk-digital-samhandling/2148#nr_br_du_bruke_rammeverket, the technical working groups of OPS-Landbruk have decided to create a semantic information model to support agriculture data interoperability use cases.

# Livestock Agriculture Information Model - High Level Scope

Our mission is to prepare a proposal for a common and open data model for agriculture, it will describe the domain through data objects and relationships between them, and adopt an event centric approach.

- We will replace proprietary models that require "interpretation" when sharing data.
- We must cover the needs of the farmer, other commercial interests and authorities.
- We will facilitate simplification, improvement and automation.
- The model must be suitable for further development and scaling.
- The model must cooperate well with other shared information models.

See the spec at [working draft](spec.html). Create [issues](https://github.com/datautvikling/Semantisk-samhandling-OPS-L/issues) if things need fixing or have been missed.

# Use Cases Document

The LAIM data model looks to support many different use cases and also provide value and support as new situations arise.

To help guide and anchor the development of the information model we capture the various uses cases. We strive for each use case to be as minimal as possible in order to facilitate concise modelling.

# Contribution 

This process is open to all. Please feel free to submit [issues](https://github.com/datautvikling/Semantisk-samhandling-OPS-L/issues). When submitting an issue that relates to text in the spec please reference the section by number. 

If you want to make a proposal for a new part of the model either create an issue or clone the repository and create a pull request. See this short video on how to create a pull request. [Pull Request Example](https://www.youtube.com/watch?v=nCKdihvneS0)

To clone a repository check out the following [link](https://github.com/git-guides/git-clone)

## Slack Channel

We have created a slack channel that can be used for discussion and questions

mattilsynet-hq.slack.com#ops-landbruk-livestock-stadardisering

Please contact Lars Bekk for an invite
lars . bekk @ mattilsynet.no

# Data Exchange Protocol - High Level Scope

A web enabled protocol for the exchange of data entities that correspond to the LAIM data model. A generic approach to data sharing that allows for future model constructs to be exhanged without need to change the protocol.

# Modelling Concepts

There a few core concepts about how we intend to develop the model. These choices have been made in order to facilitate independent lighweight development of different parts of the model. 

## Lightweight Core Entity Types

The concept of the core entity types can be likened to having some hooks upon which more things can be connected. These types ideally contain very little core data themselves and are involved in only shallow type hieararchies. They all have strong notion of identity and share the common property of having a single global uniquey identifier and the ability to convey other equivalent identifiers. 

Supporting a mapping of identifiers on all core objects can be seen as a way to meet a core requirement that enables integration across systems of the same thing, that is identified differently.


## Event Centric Modelling

To complement the Core Entity approach we decided to focus on an event centric model. For example rather than saying that an animal is part of a farm, we instead have events that talk about enrollment into a farm. 

This approach allows for different kinds of livestock events to be worked on somewhat independently, and also means that the central model is lightly connected. This provides a much more agile basis for the evolution of the information model over time.

## Controlled Vocabularies and Shallow Class Hiearchies

A class hierarchy is when one class inherits from another, e.g. Cattle extending Animal. Some of these hierarchies do provide useful semantic refinement and allow for the grouping and sharing of common properties. However, there are other situations where the refined classes do not confer or offer specialisation beyond the actual subclass naming. An example of this is CattleBreed. CattleBreed could be modelled as a number of subclasses, but at this level this does not imply any additional value. Another potentially similar case is AnimalTransfer events. There are many reasons for each transfer, and these could either be modelled as subclasses of animal transfer event, or using a controlled vocabulary for the reason for the event. In general we plan to adopt the vocabulary / classification approach where possible. 

There will be many properties whose value is one value from a known set of values. These controlled vocabularies should be clearly defined and map to existing code lists and vocabularies as already defined elsewhere. 

## Common Identifier Schemes

This is not yet decided, but it a proposal to try and create some common identifier schemes that aid the construction of core entities when there is clear ownerships related to the minting of identity. e.g. http://data.mats.no/livestock/cattle/{unique mats assigned id}

## MultiLingual Terms

Every class and property class has identifiers and labels. Identifiers will be in english (well the prefix part - the rest is guid or some other non-human friendly value) to help with gaining wider adoption. But these classes can have labels and descriptions in many languages. We will ensure that all core classes have labels and descriptions in both Norwegian and English.









