![header](/images/header.jpeg)
## SEACON API Documentation
#### v20190130

### Introduction

Seacon prefers to have direct system-integrations with its customers and suppliers. There are several options how we can do this. This document describes the technical details on how the integration can be done and what formats are preferred by Seacon.

### Integration	- Method of data transfer

Seacon uses an [Enterprise Service Bus](https://en.wikipedia.org/wiki/Enterprise_service_bus) (ESB) to integrate systems. Using this ESB we can use various methods of communication. We can use the most common communication methodologies to get and send EDI data between Seacon and it's customers. (E.g.  ftp(s) / http(s) / soap / AS2 etc.).  
Our preferred communication is POST-ing the data over http(s) through a Firewall-protected connection. Using this method, we can reply to the message as it is being sent that the content was accepted and communication has succeeded.  For setting this up we will provide the customer with an endpoint where they can POST their messages to. as an extra security feature, only pre-specified ip addresses are allowed to post to the endpoint.   
Exactly which method for communication will be used will be discussed with the customer or supplier on a case-by-case basis.

### EDI Messages

Seacon can convert between various EDI formats (E.g. EDIFACT / csv / fixed length / xml).
All Implementations require the files supplied by the second party to be mapped to the Seacon standard formats, this includes translations and conversions. (e.g. country codes, date formats, status messages, ect.)
The time needed for mapping this depends on the complexity of the implementation and any limitations from the connection party's systems.
Since the ESB internally uses XML files, it is preferred to receive the customer files in that format to lessen the steps needed for translation.  
It’s also possible to make use of the Seacon standard messages. These are described below.


### New Customer Procedure

Seacon follows the following steps when connecting new Customers to our systems.

1. The Integration Engineer will discuss the Customer and Seacon requirements for data transfer, focusing on what data is to be exchanged, and what fields are required. (requirements for each type are documented below)
1. Both the Customer and Seacon firewalls need to be configured to allow the required connections.
1. once the firewall changes have been implemented the connection can be tested using the [Seacon Echo Service](#seacon-echo-service)
1. after the connection has been tested we can test the integration with the webservice, Seacon has a test environment available where message may be tested without generating production orders.
1. each message type has a test endpoint where message can be posted to test for xml validity.
1. after a successful test the message may be sent to the Production servers.


## Seacon Standards (Customer to Seacon)
#### Shipment messages:
This is used to interface with the Seacon Transport and Oversea shipments. With this interface (truck) transport, sea freight (import and export) and airfreight orders can be booked. See attached xsd schemas and two example files.

Test with:  
`http://webservice.seaconlogistics.com:9000/validate?validate=shipment-message-65101-flat`

File | Description
-------- | -----------
[shipment-message-65101-flat.xsd](/sample_files/shipment/shipment-message-65101-flat.xsd)| Main **Shipment** message schema definition (flattened)
[]() | Basic Example File for a FTL Order
[]() | Basic Example File for a LTL Order
[]() | Basic Example File for a Rit with multiple addresses (this is a premium service)
[shipment-complete-65101.xml](/sample_files/shipment/shipment-complete-65101.xml) | Example File 2 (complete)
[shipment-message-65101.xsd](/sample_files/shipment/shipment-message-65101.xsd)| Original Shipment message schema definition
[shipment-message-65101.xsd.html](/sample_files/shipment/shipment-message-65101.xsd.html)| Original XML Schema Documentation
[shipment-elements-65101.xsd](/sample_files/shipment/shipment-elements-65101.xsd) | Base type and element specifications
[shipment-elements-65101.xsd.html](/sample_files/shipment/shipment-elements-65101.xsd.html)| XML Schema Documentation


#### CMS messages:
 This is used to interface with the Seacon Warehousing orders. With this interface inbounds, outbounds and mutations can be booked. See attached the xsd schemas and an example file.

Test With:  
`http://webservice.seaconlogistics.com:9000/validate?validate=cms-message-65101-flat`

File | Description
-------- | -----------
[cms-message-65101-flat.xsd](/sample_files/cms/cms-message-65101-flat.xsd)| Main **CMS** message schema definition (flattened)
[cms-example-inbound-multiple-sku-example.xml](/sample_files/cms/cms-example-inbound-multiple-sku-example.xml) | Basic Example File for **inbound** order with **multiple** SKU
[]() | Basic Example File for one article
[]() | Basic Example File for multiple articles
[]() | Basic Example File for ...
[cms-65101.xml](/sample_files/cms/cms-65101.xml) | Example File 1 (basic)
[cms-complete-65101.xml](/sample_files/cms/cms-complete-65101.xml) | Example File 2 (complete)
[cms-message-65101.xsd](/sample_files/cms/cms-message-65101.xsd)| Original CMS (#TODO what is cms??) message schema definition
[cms-message-65101.xsd.html](/sample_files/cms/cms-message-65101.xsd.html)| Original XML Schema Documentation
[cms-elements-65101.xsd](/sample_files/cms/cms-elements-65101.xsd) | Base type and element specifications
[cms-elements-65101.xsd.html](/sample_files/cms/cms-elements-65101.xsd.html)| XML Schema Documentation



#### Article Masterdata messages:
[If you prefer to use CSV, please go here.](/sample_files/article-wms/article-min.csv.md)

This is used to interface with the Seacon article masterdata. With this interface WMS articles can be created in the Seacon systems. See attached xsd schema and example files.

Test With:  
`http://webservice.seaconlogistics.com:9000/validate?validate=article-wms-message-65101-flat`

File | Description
-------- | -----------
[article-wms-message-65101-flat.xsd](/sample_files/article-wms/article-wms-message-65101-flat.xsd.xsd)| Main **Article** message schema definition (flattened)
[]() | Basic Example File for ...
[]() | Basic Example File for ...
[]() | Basic Example File for ...
[article-wms-65101.xml](/sample_files/article-wms/article-wms-65101.xml) | Example File 1 (basic)
[article-wms-complete-65101.xml](/sample_files/article-wms/article-wms-complete-65101.xml) | Example File 2 (complete)
[article-wms-message-65101.xsd](/sample_files/article-wms/article-wms-message-65101.xsd)| Original Main article message schema definition
[article-wms-message-65101.xsd.html](/sample_files/article-wms/article-wms-message-65101.xsd.html)| Original XML Schema Documentation
[article-wms-elements-62401.xsd](/sample_files/article-wms/article-wms-elements-62401.xsd) | Base type and element specifications
[article-wms-elements-62401.xsd.html](/sample_files/article-wms/article-wms-elements-62401.xsd.html)| XML Schema Documentation




#### Status messages:
This is used to update the Seacon system with tracking and tracing statuses.

Test With:  
`http://webservice.seaconlogistics.com:9000/validate?validate=status-message-65101-flat`

File | Description
-------- | -----------
[status-message-65101-flat.xsd](/sample_files/status/status-message-65101-flat.xsd)| Main **Status** message schema definition (flattened)
[status-message-example-carrier-confirmation.xml](/sample_files/status/status-message-example-carrier-confirmation.xml) | Basic Example File for **Carrier Confirmation** Order received message
[status-message-example-carrier-loaded.xml](/sample_files/status/status-message-example-carrier-loaded.xml) | Basic Example File for **Loaded** Basic loaded at pickup location message
[status-message-example-carrier-delivered.xml](/sample_files/status/status-message-example-carrier-delivered.xml) | Basic Example File for **Conform Delivery** confirmation of normal delivery
[status-message-example-carrier-nonconformity.xml](/sample_files/status/status-message-example-carrier-nonconformity.xml) | Basic Example File for **non-conform end of shipment** unable to complete shipment as requested message see below for list of non-conformity codes
[status-65101.xml](/sample_files/status/status-65101.xml) | Example File 1 (Basic)
[status-complete-65101.xml](/sample_files/status/status-complete-65101.xml) | Example File 2 (Complete)
[status-message-65101.xsd](/sample_files/status/status-message-65101.xsd)| Original status message schema definition
[status-message-65101.xsd.html](/sample_files/status/status-message-65101.xsd.html)| XML Schema Documentation
[status-elements-65101.xsd](/sample_files/status/status-elements-65101.xsd) | Base type and element specifications
[status-elements-65101.xsd.html](/sample_files/status/status-elements-65101.xsd.html)| XML Schema Documentation

##### Non-conformity codes
Code | Description
NCL_005 | Gremlins stole the Cargo #TODO set actual description

## Seacon standards (Seacon to Customer/Supplier)

#### Shipment-out xml:
This is used to interface (outgoing) with the Seacon Transport and Oversea shipments. With this interface (truck) transport, seafreight (im-and export) and airfreight orders or updated order can be sent to other systems.  See attached xsd schemas and two example files.

File | Description
-------- | -----------
[shipment-out-message-65101.xsd](/sample_files/shipment_out/shipment-out-message-65101.xsd)| Original **Shipment-out** message schema definition
[shipment-out-message-65101.xsd.html](/sample_files/shipment_out/shipment-out-message-65101.xsd.html)| XML Schema Documentation
[shipment-out-elements-65101.xsd](/sample_files/shipment_out/shipment-out-elements-65101.xsd) | Base type and element specifications
[shipment-out-elements-65101.xsd.html](/sample_files/shipment_out/shipment-out-elements-65101.xsd.html)| XML Schema Documentation
[shipment-out-65101.xml](/sample_files/shipment_out/shipment-out-65101.xml) | Example File 1 (Basic)
[shipment-out-complete-65101.xml](/sample_files/shipment_out/shipment-out-complete-65101.xml) | Example File 2 (Complete)

#### CMS-out xml:
This is used to interface (outgoing) with the Seacon WMS orders. With this interface warehouse informations about inbound, outbound an mutation orders can be sent to other systems .  See attached xsd schemas and two example files.

File | Description
-------- | -----------
[cms-out-message-65101.xsd](/sample_files/cms_out/cms-out-message-65101.xsd)| Original **CMS**-out message schema definition
[cms-example-outbound-multiple-sku-example.xml](/sample_files/cms_out/cms-example-outbound-multiple-sku-example.xml) | Basic Example File for **Outgoing** order with multiple **SKU**
[cms-out-message-65101.xsd.html](/sample_files/cms_out/cms-out-message-65101.html)| XML Schema Documentation
[cms-out-elements-65101.xsd](/sample_files/cms_out/cms-out-elements-65101.xsd) | Base type and element specifications
[cms-out-elements-65101.xsd.html](/sample_files/cms_out/cms-out-elements-65101.xsd.html)| XML Schema Documentation
[cms-out-65101.xml](/sample_files/cms_out/cms-out-65101.xml) | Example File 1 (Basic)
[cms-out-complete-65101.xml](/sample_files/cms_out/cms-out-complete-65101.xml) | Example File 2 (Complete)


#### Status out xml:
This is used to interface (outgoing) with the Seacon system. With this interface tracking en tracing information and statuses of orders can be sent to other systems. See attached xsd schemas and two example files

File | Description
-------- | -----------
[status-out-message-65101.xsd](/sample_files/status_out/status-out-message-65101.xsd)| Original **status**-out message schema definition
[status-out-message-65101.xsd.html](/sample_files/status_out/status-out-message-65101.html)| XML Schema Documentation
[status-out-elements-65101.xsd](/sample_files/status_out/status-out-elements-65101.xsd) | Base type and element specifications
[status-out-elements-65101.xsd.html](/sample_files/status_out/status-out-elements-65101.xsd.html)| XML Schema Documentation
[status-out-65101.xml](/sample_files/status_out/status-out-65101.xml) | Example File 1 (Basic)
[status-out-complete-65101.xml](/sample_files/status_out/status-out-complete-65101.xml) | Example File 2 (Complete)


## Test information

### How to test a XSD
`xmllint --noout --schema status-flat.xsd status-complete-65101.xml`  

`xmllint --schema status-flat.xsd status-complete-65101.xml`  


### Validate with Seacon Validator
to Test the valid XML, post the xml to the Seacon Validator  
`http://webservice.seaconlogistics.com:8000/validate?validate=status-message-65101-flat`



### Seacon Echo Service
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
