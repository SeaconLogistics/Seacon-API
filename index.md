![header](/images/header.jpeg)
## SEACON API Documentation
#### v20190130

### Introduction

Seacon prefers to have direct system-integrations with its customers and suppliers. There are several options how we can do this. This document describes how the integration can be done and what formats are preferred by Seacon. 

### Integration	- Way of data transfer

Seacon uses an ESB for integration systems with each other. In this ESB we can connect to systems in several ways. We can use most common communication types to get and send EDI data to and from our customers. (E.g.  ftp(s) / http(s) / soap / AS2 etc.).  
Our preferred communication is over http(s). In this way we can have direct communications to the systems with reply if all is okay.  For setting this up we can provide the customer with an endpoint where they can post their messages to. We need some systems information to be able to whitelist the server that is posting (e.g. IP addresses) . 
The options in how to integrate can be discussed with Seacon IT and the customer or supplier to see what will be the best way for that particular implementation. 

### EDI Messages

Seacon can convert from and to several different EDI formats (E.g. EDIFACT / csv / fixed length / xml) . All implementations will require a pre-investigation of how the mapping to the Seacon system will be done and what information the customers or suppliers require.  The time needed for this depends on the complexity of the implementation.
Seacon prefers to receive and sent xml files for these are the easiest to map to the Seacon standard. 
It’s also possible to make use of the Seacon standard messages. These are described below.


### New Customer Procedure

Seacon follows the following steps when connecting new Customers to our systems.

1. The Integration Engineer will discuss the Customer ans Seacon requirements for data trasnfer.  
1. ???  
1. Both the Customer and Seacon firewalls need to be configured to allow the required connections.
1. once the fireawll changes have been implemented the connection can be tested using the [Seacon Echo Service](#seacon-echo-service)
1. after the connection has been tested we can test the integration with the webservice, Seacon has a test enviroment available where message may be tested without generating production orders.
1. each message type has a test endpoint where message can be posted to test for xml validity.
1. after a successfull test the message may be sent to the Production servers.


## Seacon Standards (Customer to Seacon) 
#### Shipment messages:
This is used to interface with the Seacon Transport and Oversea shipments. With this interface (truck) transport, seafreight (im-and export) and airfreight orders can be booked. See attached xsd schemas and two example files.

File | Description
-------- | -----------
[shipment-message-65101.xsd](/sample_files/shipment/shipment-message-65101.xsd)| Main Shipment message schema definition 
[shipment-message-65101.xsd.html](/sample_files/shipment/shipment-message-65101.xsd.html)| XML Schema Documentation
[shipment-elements-65101.xsd](/sample_files/shipment/shipment-elements-65101.xsd) | Base type and element specifications
[shipment-elements-65101.xsd.html](/sample_files/shipment/shipment-elements-65101.xsd.html)| XML Schema Documentation
[shipment-65101.xml](/sample_files/shipment/shipment-65101.xml) | Example File 1
[shipment-complete-65101.xml](/sample_files/shipment/shipment-complete-65101.xml) | Example File 2


#### CMS messages:
 This is used to interface with the Seacon Warehousing orders. With this interface inbounds,  outbounds and mutations can be booked. See attached the xsd schemas and an example file.

     





#### Article Masterdata messages:
This is used to interface with the Seacon article masterdata. With this interface WMS articles can be created in the Seacon systems. See attached xsd schema and example files.





#### Status messages:
This is used to update the Seacon files with tracking and tracing statuses. 





## Seacon standards (Seacon to Customer)

#### Shipment-out xml:
This is used to interface (outgoing) with the Seacon Transport and Oversea shipments. With this interface (truck) transport, seafreight (im-and export) and airfreight orders or updated order can be sent to other systems.  See attached xsd schemas and two example files. 


#### CMS-out xml:
This is used to interface (outgoing) with the Seacon WMS orders. With this interface warehouse informations about inbound, outbound an mutation orders can be sent to other systems .  See attached xsd schemas and two example files. 


#### Status out xml:
This is used to interface (outgoing) with the Seacon system. With this interface tracking en tracing information and statuses of orders can be sent to other systems. See attached xsd schemas and two example files


### Test information

#### Seacon Echo Service
To test your connection to the Seacon ESB please POST a test file to the following URL.

##### Production server:
`http://webservice.seaconlogistics.com:9000/echo`

##### Test server:
`http://webservice.seaconlogistics.com:8000/echo`

#### Sample Commands

`curl -X POST http://webservice.seaconlogistics.com:8000/echo`

`curl -X POST -H "Content-Type: text/plain" --data "Hallo Seacon, dit is een test" http://webservice.seaconlogistics.com:8000/echo`





### More information:
With every customer or supplier we will discuss what will be the most efficient way to connect the systems. It could be the usage of the “Seacon standard” files, but there are of course other options. We have a lot op options in connecting. 


## Contact information
More information about EDI integrations you can contact:  
Seacon Logistics B.V.  - IT Department  
Mark Vromans   
Manager IT & Engineering  
T: +31 7 327 5531  
M: +31 6 20 40 1290  
E: mvromans@seaconlogistics.com  

![header](/images/footer.jpeg)