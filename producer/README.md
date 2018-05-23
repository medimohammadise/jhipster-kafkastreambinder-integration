# producer
This application was generated using JHipster 5.0.0-beta.1
I'm trying to integrate Kafka Streams Binder with Jhipster. 

## Configurations 
### class configurations for producer channel
In the my.microservices.kafkastream.producer.service.messaging package I have NewReviewPublishedEvent class  and NewReviewPublisherChannel
In the my.microservices.kafkastream.producer.web.rest I have ProducerResource for sending the message
In my.microservices.kafkastream.producer.config.MessagingConfiguration I have configured NewReviewPublisherChannel in EnableBinding section

### yaml file configurations

## How to test 

To start your application in the dev profile, simply run:

    ./mvnw
    
You can just hit this url for sending message from producer :
http://localhost:8881/api/review/%22B072QG8BX6%22

    





