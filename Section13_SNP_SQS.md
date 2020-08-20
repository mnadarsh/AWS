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
