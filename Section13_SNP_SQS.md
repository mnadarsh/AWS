# Cloud Integration

  **Section Introduction**
  
      • When we start deploying multiple applications, they will inevitably need
        to communicate with one another
      • There are two patterns of application communication
      
   ![communication_method](https://github.com/mnadarsh/AWS/blob/master/Images/communication_method.PNG "communication_method")
   
       • Synchronous between applications can be problematic if there are
            sudden spikes of traffic.
      • What if you need to suddenly encode 1000 videos but usually it’s 10?.
      
      • In that case, it’s better to decouple your applications:
          • using SQS: queue model
          • using SNS: pub/sub model
          • using Kinesis: real-time data streaming model.
      • These services can scale independently from our application!
      
 **Amazon SQS – Standard Queue**
 
      • Oldest AWS offering (over 10 years old).
      • Fully managed service (~serverless), use to decouple applications.
      • Scales from 1 message per second to 10,000s per second.
      • Default retention of messages: 4 days, maximum of 14 days.
      • No limit to how many messages can be in the queue.
      • Messages are deleted after they’re read by consumers.
      • Low latency (<10 ms on publish and receive).
      • Consumers share the work to read messages & scale horizontally.

  ![sqs](https://github.com/mnadarsh/AWS/blob/master/Images/sqs.PNG "sqs")
  
  ![sqs_decouple](https://github.com/mnadarsh/AWS/blob/master/Images/sqs_decouple.PNG "sqs")
  
**Amazon SNS**

    • What if you want to send one message to many receivers?
    
    • The “event publishers” only sends message to one SNS topic.
    • As many “event subscribers” as we want to listen to the SNS topic notifications.
    • Each subscriber to the topic will get all the messages.
    • Up to 10,000,000 subscriptions per topic, 100,000 topics limit.
    
    • SNS Subscribers can be:
       • HTTP / HTTPS (with delivery retries – how many times).
       • Emails, SMS messages, Mobile Notifications.
       • SQS queues (fan-out pattern), Lambda Functions (write-your-own integration).
       
   ![sns](https://github.com/mnadarsh/AWS/blob/master/Images/sns.PNG "sns")
   
 **Integration Section – Summary**
 
    • SQS:  
    
       • Queue service in AWS.
       • Multiple Producers, messages are kept up to 14 days.
       • Multiple Consumers share the read and delete messages when done.
       • Used to decouple applications in AWS.
       
    • SNS:
    
       • Notification service in AWS.
       • Subscribers: Email, Lambda, SQS, HTTP, Mobile…
       • Multiple Subscribers, send all messages to all of them.
       • No message retention.
    
