# ESSIF-Lab architecture

[Intentionality]

## Intro

[Explain SSIF-Lab difference between architecture and infrastructure]

### Notion of SSI-component

An SSI-component is an electronic application run by a human actor (common user
or an administrator), capable of performing formal actions in the context of
SSI flow. Except for its electronic core, it consists of a
_business interface_ for interacting with the highest business layer
(databases, registrations, cloud-services etc.),
an _SSI-interface_ for interacting with the middle layer of
SSI-infrastructure (primarily implementing the protocols for credential exchange)
and a _user interface_ for the human actor to interact with the
above-mentioned APIs (policy specification, transactions log etc.).
It should be stressed that the SSI roles of *Issuer*, *Holder* and *Verifier*
(see the *SSI Roles Layer* section below) fall under the SSI-interface.

### Entities

- __party__: entity capable of decisions and being held accountable (person, organization)
- __actor__: entity capable of performing formal actions (person, computer/robot)
- __agent__: actor acting _at some particular moment_ on behalf of a party
- __SSI-agent__: an SSI-component that acts as an agent
- __owner__: the party an actor acts _at some particular moment_ on behalf of
- __colleage__: agents acting _at some particular moment_ on behalf of the same party
- __organization__: the composite entity of owner together with their agents _at some particular moment_

### Transaction related attributes

- __peer-party__ (of a specific party): self-evident meaning in the context of a specific bilateral transaction
- __peer-agent__ (of a specific agent): self-evident meaning in the context of a specific bilateral transaction

## Initial functional architecture

Initial functional architecture refers to the totality of functions necessary
for all parties to dispose of, so that electronic transactions be in principle possible.


__Fundamental requirement__: Every agent acting on behalf of a party in the
context of a specific bilateral transaction must be certain (to the extent
necessary for the transaction) that their peer-agent acts indeed on behalf
of the corresponding peer-party. Note that establishing genuineness of a
peer-agent does not necessarily require knowledge of the peer-party's identity.

[Figure]

The architecture is here exposed from the highest to the lowest level.

### Business Transaction Layer(s)

Transaction execution from the business viewpoint (database updates,
cloud-services etc.) and accompanying business decisions are to be
accommodated in this layer. This consists of a _higher_ and a _lower_ sublayer;
only the latter falls strictly under the ESSIF-Lab architecture.

[Figure]

#### Higher

Realization of actual transactions from the business viewpoint (form-filling,
actual business decision, validation and storage of data etc.). Very business
specific, outside the scope of ESSIF-Lab's both architecture and infrastructure.

#### Lower

Contains two functional components, each one associated with a business
specific policy. Both fall under the ESSIF-Lab architecture but not
infrastructure.

- __Transaction Validation Engine__ (__TVE__): [pg. 12, pg 15-18 (policy)]
- __Transaction Result Dispatcher__ (__TRD__): [pg. 12, pg. 20]


### ESSIF-Glue API Layer

[pg. 15]

### SSI Roles Layer

[Contains four functional components, each one associated with a specific policy]

[Figure]

- __Issuer__: [pg. 13, pg. 21]
- __Wallet__: [pg. 13, pg. 22]
- __Holder__: [pg. 13, pg. 19]
- __Verifier__: [pg. 13, pg. 18]

### SSI Tech API Layer

[pg. 15]

### SSI Protocols and Crypto Layer

[...]

* __Credential related technologies__: [pg. 14]
* __Secure communication technologies__: [pg. 14]
* __Crypto related technologies__: [pg. 14]
* __Blockchain/Distributed ledger technologies__: [pg. 14]

## Initial SSI-agent network architecture

This refers to a specification of how SSI-components dynamically
gain or loose the attribute of SSI-agent, so that party and agents
comprising an organization can in principle collaborate in the
context of object realization. Not yet given.
