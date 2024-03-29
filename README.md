# Navigating the journey of serverless event-driven architecture

<img width="1024" alt="image" src="https://user-images.githubusercontent.com/3268013/234830948-fc02da47-1228-456d-9803-a8773c5e2f65.png">

Building an event-driven architecture is a journey, these resources can help you understand and dive deeper into the three stages I have highlighted:

- [Initial Design](#initial-design)
  - Where should you start when building EDA applications? Understanding behaviour of systems can help vs diving straight in
- [Implementation](#Implementation)
  - When you start writing code, what should you be aware of? What can help?
- [Operational and maintenance](#Operation-and-maintenance)
  - When you are in production and scaling your solution, what can help you remain decoupled and agile?

Please find below a list of resources that can help you dive deeper into event-driven architecture. These resources map to my 2023 talk about `Navigating the journey of serverless event-driven architecture`.

## Initial Design

To build a successful event-driven application, it is essential to understand the problem domain, identify key events, and agree on standards. Understanding the problem domain involves identifying key concepts, entities, and workflows. This understanding can help vs diving straight into implemention details.

- [Understanding Event Storming](https://serverlessland.com/event-driven-architecture/visuals/event-storming) - Remember before you start building EDA applications, take time to understand the behaviour of your system, Event Storming can help you.
- [Event first thinking](https://www.youtube.com/watch?v=GBzr48Mj2JU&t=126s) - In this talk I spoke about YOLO events, and problems if we dive into implementation first over design or thinking first. Here is a talk I done in 2022 that might be able to help you. We dive into YOLO events, event patterns and trade-offs to consider.
- [EDA with Domain Driven Design](https://serverlessland.com/event-driven-architecture/visuals/eda-and-ddd) - It's important to have a shared understanding of your domain and domain driven design can help with this.

## Implementation

After gaining a clear understanding of the key events involved in your event-driven application, it is also crucial to familiarize yourself with messaging patterns and integration patterns. These patterns can provide valuable insights and solutions when dealing with specific implementation details or challenges that may arise during the development process.

### Messaging patterns

- [Understanding point-to-point messaging](https://serverlessland.com/event-driven-architecture/visuals/point-to-point-messaging) - Here is a bite sized visual to help you understand point-to-point messaging.
- [Understanding pub/sub](https://serverlessland.com/event-driven-architecture/visuals/publish-subscribe) - Dive in and understand publish/subscribe patterns, extra resources in here too.
- [Understanding event streaming](https://serverlessland.com/event-driven-architecture/visuals/event-streams) - Do you need to process events in real time and fast? Might be worth checking out event streaming.

### Integration patterns + consumer patterns
- [Content enricher pattern](https://serverlessland.com/event-driven-architecture/visuals/content-enricher-pattern) - Do you need to enrich events before they reach downstream consumers? This allows you to keep producer contract simple and consumers still get what they need without putting back pressure onto the producer. 
- [Claim check pattern](https://serverlessland.com/event-driven-architecture/visuals/claim-check-pattern) - Sometimes you may need to store first and then retrive data later, you can use this pattern to get around any payload limits you may have with your broker.
  - Example of a [Serverless claim check pattern](https://www.boyney.io/blog/2022-11-01-eventbridge-claim-check)
- [Messaging between bounded context](https://serverlessland.com/event-driven-architecture/visuals/messages-between-bounded-context) - When you consume events, how do you want to consume them? Conform, map or agree on a public language? Something to consider.

## Operation and maintenance

Scaling your event-driven application (EDA) in your organization can pose various challenges, such as discoverability issues, standardization problems, lack of documentation, and governance concerns. To ensure that your EDA operates efficiently at scale, it is crucial to keep track of these issues and implement appropriate solutions to address them.

### Standards

- [Payload standards](https://www.boyney.io/blog/2022-02-11-event-payload-patterns) - When you start building and designing events, maybe you want to consider standards within your events, here is a blog post I wrote about it in 2022.
- [Event first thinking](https://www.youtube.com/watch?v=GBzr48Mj2JU&t=126s) - Event design is important, when you scale your EDA solution in your organization it's important to consider your event design and how you can scale to 100s or 1000s of events. Treat events as first class citizens. In this talk I go into more detail and the risks you might face if you don't.

### Discoverability
- [Schema Registry](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-schema.html) - Your consumers will need to find which events are being raised and by who. Schema registry’s can help with this, and Amazon EventBridge has [one you can use](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-schema.html). If you want to dive deeper I have an open source project called [EventCatalog](https://www.eventcatalog.dev/) that may help. EventCatalog allows you to document your events and help consumers discover them.
- [AsyncAPI](https://www.asyncapi.com/) - Specification to help you define asynchronous APIs. Great for event-driven applications. Document messages, events, channels and much more. 

### Communication

- [Understanding and embrace ubiquitous language](https://serverlessland.com/event-driven-architecture/visuals/ubiquitous-language) - Each domain will be talking in a different language, that's OK, but make sure you are aware. Try not to leak domain information in your public events, and maybe use mapping between domains to help you translate domain models/events into models you understand (as a consumer).
- [Domain driven](https://serverlessland.com/event-driven-architecture/visuals/eda-and-ddd) - Understand the importance of domains and event architectures, so much we can learn from domain driven design and implement these practices in our EDA solutions to help us scale and remain decoupled and flexible.
- [Event Storming](https://serverlessland.com/event-driven-architecture/visuals/event-storming) - Included this one again here, Event Storming is not something you just do once, but something you can repeat over time. Identify behaviour of your system, and identify your events and domains. Visualising systems can help you write EDA architectures.

## Extras
- [EDA Visuals](https://serverlessland.com/event-driven-architecture/visuals) - List of visuals I have created to explain event-driven architectures, many have extra resources for you to dive deep and learn in your own time.
- [Enterprise integration patterns](https://www.enterpriseintegrationpatterns.com/) - Holy grail of information about integration patterns, totally worth checking out!
- [Severless Land Patterns](https://serverlessland.com/patterns) - Want to get started with these integration patterns on AWS, we have over 500 patterns for you to dive in, learn and deploy.

---

Reach out to me if you would like me to run this talk at your event.

Thanks!

