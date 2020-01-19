# ESSIF-Lab architecture

[Intentionality]

## Intro

[Explain SSIF-Lab difference between architecture and infrustructure]

### SSI-component

[Explain SSI-component notion and high-level architecture, pg. 26-7]

### Entities

- __party__: [entity capable of decisions and being held accountable (person, organization)]
- __actor__: [entity capable of "doing things" (person, computer/robot)]
- __agent__: [actor acting (at some particular moment) on behalf of a party]
- __SSI-agent__: [an SSI-component that acts as an agent]
- __owner__: [the party an actor acts (at some particular moment) on behalf of]
- __colleage__: [agents acting (at some particular moment) on behalf of the same party]
- __organization__: [owner + agents (dynamic: depending on particular moment)]

### Transaction related attributes

- __peer-party__ (of a specific party): [self-evident meaning in the context of a specific bilateral transaction]
- __peer-agent__ (of a specific agent): [self-evident meaning in the context of a specific bilateral transaction]

## Initial functional architecture

[Functionalities necessary for all parties to dispose of, so that electronic transactions be possible]

[Figure]

__Fundamental requirement__: Every agent acting on behalf of a party in the
context of a specific bilateral transaction must be sure (to the extent
  necessary for the transaction) that their peer agent acts indeed on behalf
of the corresponding peer party. Establishing whether the an actor is peer
agent does not necessarily require knowledge of the peer party's identity).

### Business Transaction Layer(s)

[...]

[Figure]

#### Higher

[Actual business transactions, including transaction form-filling and execution,
actual business decision, validation and storage of data. Very business
specific, outside the scope of eSSIF-Lab's infrastructure]

#### Lower

[Contains two functional components, each one associated with a business specific policy
(Both in architecture, but not in infrastructure)]

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

[Specify how SSI-components become SSI-agent or loose this attribute,
so that the SSI-agents of a party can work together at any time
for object realization]

NOT YET WRITTEN
