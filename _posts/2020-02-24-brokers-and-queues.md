---
layout: "post"
title: "Brokers and Queues"
date: "2020-02-24 13:01"
category: Backend
---
Before we get into message brokers and queues it's important to understand how the Pub/Sub model works where publishers send messages into channels without knowledge of the subscribers at the other end if any. Workers can subscribe to channels by using the name of the channels.

- publisher/producer/client (sends messages)
- subscriber/consumer/workers (receives messages)
- channel (links the publisher and subscriber)
- Broker (receives the messages from the producer and routes them to consume, a broker has an exchange and queues)
- Bindings (rules that exchange uses to route messages to queue)
- Queue (message or task queue is a buffer that stores messages)

A message or task consists of attributes and payload.

"Celery is a task queue with focus on real-time processing, while also supporting task scheduling."
Celery has it's own terms and does need a separate broker system. RQ and Celery are the same thing!

"To initiate a task the client adds a message to the queue, the broker then delivers that message to a worker."

Celery workers constantly monitor the task queues for new work. Celery is highly available where workers will automatically retry in the event of a failure.  

"Redis is a message broker. This means it handles the queue of "messages" between Django and Celery."

Redis also acts as a Results store which stores the task (regular python functions) results and state

Queues are the same as message brokers? and are not really persistent, in case of power failures it will not save the data.
It does look like Celery has it's own built in queues.

What happens when a task fails? When a particular task fails, you can configure celery to retry until a particular exception occurs, or set max_retries parameter to enable retrying n times before giving up.
