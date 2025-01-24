# PubSub

- Google `Cloud Pub/Sub `is a fully managed messaging service that enables you to build event-driven systems by decoupling publishers and subscribers. It is designed for low-latency, high-throughput, and reliable message delivery at scale.

### Key Components of GCP Pub/Sub
1.  `Topic`: 
A named resource to which messages are sent by publishers.
Each topic is global and can have multiple subscriptions.

2. `Subscription`:
A named resource that represents the stream of messages from a specific topic to a subscriber.
Subscriptions can be either:

    - `Pull`: The subscriber explicitly fetches messages.
    - `Push`: The service delivers messages to a specified endpoint (e.g., a webhook).

3.  `Message`:
    - Data sent by publishers to topics.
    - Includes:
        - Payload: The actual data.
        - Attributes: Optional key-value metadata.  

4. `Publisher`: An application or service that sends messages to a topic.
5. `Subscriber`: An application or service that consumes messages from a subscription.  
6. `Acknowledgment`: After a subscriber processes a message, it sends an acknowledgment (ACK) to confirm successful delivery.

### Pub/Sub Workflow in GCP
1. A `publisher` sends messages to a topic.  
2.  `Subscribers` subscribe to the topic via a subscription.  
3. Messages are delivered to subscribers:
    - In `Pull mode`, subscribers explicitly request messages.
    - In `Push mode`, Pub/Sub pushes messages to a specified URL.
4. Subscribers process messages and acknowledge them.


### Features of GCP Pub/Sub
1. Asynchronous Messaging:
Publishers and subscribers operate independently.
2. At-Least-Once Delivery:
Ensures messages are delivered, though duplicates are possible.
3. Message Ordering:
Messages can be delivered in order with ordering keys.
4. Dead Letter Topics:
Messages that can't be processed after multiple attempts are routed to a dead letter topic.
Message Filtering:
5. Subscribers can filter messages based on attributes.
6. Scalability:
Handles millions of messages per second with automatic scaling.
7. Durability:
Messages are stored for up to 7 days (default retention period).
