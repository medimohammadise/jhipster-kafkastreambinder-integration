# producer
This application was generated using JHipster 5.0.0-beta.1
I'm trying to integrate Kafka Streams Binder with Jhipster. 

## Configurations 
### class configurations for producer channel
In the my.microservices.kafkastream.producer.service.messaging package I have NewReviewPublishedEvent class  and NewReviewPublisherChannel.
In the my.microservices.kafkastream.producer.web.rest.
I have ProducerResource for sending the message.
In my.microservices.kafkastream.producer.config.MessagingConfiguration I have configured NewReviewPublisherChannel in EnableBinding section.

### yaml file configurations
in recource/config/application-dev.yml file :

    cloud:
           stream:
               kafka:
                   binder:
                       brokers: localhost
                       zk-nodes: localhost
               bindings:
                   output:
                       destination: topic-jhipster
                   newreview-Channel:
                     destination: new-reviews
                     #content-type: application/json
                     producer:
                       header-mode: raw  #cause skip parsing header for middlewares that do not support header


in recource/config/application.yml file :


    cloud:
            stream:
                kafka:
                 streams:
                   binder:
                    configuration:
                      commit:
                        interval:
                          mms: 1000
                      default:
                        key:
                         serde: org.apache.kafka.common.serialization.Serdes$StringSerde
                        value:
                         serde: org.apache.kafka.common.serialization.Serdes$StringSerde

## How to test 

To start your application in the dev profile, simply run:

    ./mvnw
    
You can just hit this url for sending message from producer :
http://localhost:8881/api/review/"testcode"

    





