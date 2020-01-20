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

- __Transaction Validation Engine__ (__TVE__): Initiates and handles
_between peer-agents_ requests for engaging in a transaction
(through possibly multiple communication channels).
This includes generating a transaction form with complete and valid
data on behalf of the (owner of the) requester,
that is necessary for the (owner of the) receptor to decide whether they
want to involve. See *Verifier* and *Holder* in the *SSI Roles Layer*
subsection for details.

- __Transaction Result Dispatcher__ (__TRD__): Stores states of
(possibly intermediary) transaction results through access to
business data stores, which are to be subsequently dispatched ("issued") to
interested parties. State supersession is to be handled by this component.


### ESSIF-Glue API Layer

[pg. 15]

### SSI Roles Layer

[Figure]

- __Issuer__: Generates *credentials* to a Holder, i.e., a set of interrelated
statements accompanied by metadata and a digital proof of provenance and
integrity. Revocation and suspension of credentials are to be
handled by this component.
- __Wallet__: Securely stores credentials and keys that can be used for signing
on behalf of the wallet's owner. Most importantly, a wallet guarantees that its
stored content becomes available to another component only if they share the
same owner.
- __Verifier__: Supports the TVE in its effort of credentials acquisition in
the context of negotiating a transaction. From the crypto layer viewpoint, it
verifies the digital proof included in a transaction request.
More accurately, a Verifier
 1. prepares and sends a *presentation request* to a Holder asking for credentials
on behalf of the latter's owner
 2. receives the Holder's *presentation*, i.e., response to the above request
 3. verifies attached signature and proofs, forwarding results to the TVE.
- __Holder__: Handles presentation requests received from a Verifier, i.e.,
invokes requested data from the owner's wallet and uses them to respond
with a presentation.


### SSI Tech API Layer

[pg. 15]

### SSI Protocols and Crypto Layer

The set of underlying crypto libraries used in the implementation of SSI roles
(Issuer, Wallet, Verifier, Holder).

* __Credential related technologies__: e.g., X.509, OIDC, BlockCerts etc.
* __Secure communication technologies__: Mechanisms for component
identification and establishment of communication channels.
* __Crypto related technologies__: Mechanisms for generating and verifying
digital sigantures, zk-proofs etc.
* __Blockchain/Distributed ledger technologies__: Public or private mechanisms
for logging history in a variety of contexts.

## Initial SSI-agent network architecture

This refers to a specification of how SSI-components dynamically
gain or loose the attribute of SSI-agent, so that party and agents
comprising an organization can in principle collaborate in the
context of object realization. Not yet given.
