# Event Driven Architecture
- Event Driven Architecture (EDA) is a kind of architecture style that respond asynchronously on events in a system.
- Different services and event processors triggers events and other set of services and event processors of the same system will respond to these events asynchronously.
- The need of EDA increases because of increase in the demand of non-deterministic systems.
- Things that are hard to manage in EDA are complexity and user paths.
- EDA is built on top of event channels. 

[Event Driven Architecture](.images/blogs-event_driven_architecture.drawio.png)

- Components of EDA
  - Events: Comes either from internal or external system.
  - Event Channel: These event channels are known as event brokers and streaming brokers. These are the dumb channels that are only there to consume or produce events.
  - Event Processor: These are the services that consume initiating events and generate derived events. They advertise derived events to the rest of the system. They send derived events into event channels. These derived events are picked by other event processors.
- When to use EDA?
  - Abstraction :star2: :star2: :star2: :star2:
  - Elasticity  :star2: :star2: :star2: :star2:
  - Observability :star2: :star2: :star2: :star2: :star2:
  - Fault Tolerance :star2: :star2: :star2: :star2: :star2:
  - Performance :star2: :star2: :star2: :star2: :star2:
  - Scalability :star2: :star2: :star2: :star2: :star2:
  - When nature of business problems talks about events or triggers than EDA is a good match.
  - When fault tolerance is that priority which means If a service goes down the whole system remains working.
  - When we need a high performing system that supports asynchronous processing or parallel processing.
- When not to use EDA?
  - When we are dealing with deterministic systems.
  - When we need high consistency.
  - When we need high integrity.
  - simplicity :star2:
  - testability :star2: :star2:
- General rating of other operational characteristics
  - Maintainability :star2: :star2: :star2:
  - Deploy-ability :star2: :star2: :star2:
  - Cost :star2: :star2: :star2:
  - Evolvability :star2: :star2: :star2: :star2: :star2:
  - Interoperability :star2: :star2: :star2:
- Most of the 5 star characteristics involves with operational architecture characteristics.