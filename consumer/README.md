# consumer
This application was generated using JHipster 5.0.0-beta.1
I'm trying to integrate Kafka Streams Binder with Jhipster. 

## Configurations 

### class configurations for consumer channel
In the my.microservices.kafkastream.consumer.service.messaging package.
I have ConsumerChannel interface  and NewReviewPublishedEvent class.
I am willing to receive message hear in the class ConsumerService but It is not working!
In my.microservices.kafkastream.consumer.config.MessagingConfiguration I have configured ConsumerChannel in EnableBinding section.

### yaml file configurations
   resources/config/application-dev.yml
   
    cloud:
               stream:
                   kafka:
                       streams:
                         bindings:
                          newreview-subChannel:
                            consumer:
                             keySerde: org.apache.kafka.common.serialization.Serdes$StringSerde
                             valueSerde: org.apache.kafka.common.serialization.Serdes$StringSerde
   
                       binder:
                           brokers: localhost
                           zk-nodes: localhost
                   bindings:
                       output:
                           destination: topic-jhipster
                       newreview-subChannel:
                         destination: new-reviews
   
                         consumer:
                             header-mode: raw
                             useNativeDecoding: true
                             

## How to test 

To start your application in the dev profile, simply run:

    ./mvnw
    



    





