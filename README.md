# Currency Conversion Microservice

Code Forked from:
[Microservices with Spring Boot](https://github.com/in28minutes/spring-boot-examples/tree/master/spring-boot-basic-microservice) 
and Java - [Part 3 Tutorial](https://www.springboottutorial.com/creating-microservices-with-spring-boot-part-3-currency-conversion-microservice)

Example code part of in28minutes. Added google jib for docker builds

# TL;DR
1. clone repo
2. create docker image locally : `mvn compile jib:dockerBuild`
3. run docker image locally: `docker run -it -p 8100:8100 rarean/sb-ms-ccsvc`


# Resources Overview
Currency Conversion Service (CCS) can convert a bucket of currencies into another currency. It uses the Forex Service to get current currency exchange values. CCS is the Service Consumer.

An example request and response is shown below:

GET to http://localhost:8100/currency-converter/from/EUR/to/INR/quantity/10000

```
{
  id: 10002,
  from: "EUR",
  to: "INR",
  conversionMultiple: 75,
  quantity: 10000,
  totalCalculatedAmount: 750000,
  port: 8000,
}
```
The request above is to find the value of 10000 EUR in INR. The totalCalculatedAmount is 750000 INR.

# Notes
* to publish to docker registry, you will need to add your registry info to [pom.xml](https://github.com/rarean/springboot-currencyconversion/blob/master/pom.xml#L87) with your creds [see google jib docs](https://github.com/GoogleContainerTools/jib/tree/master/jib-maven-plugin#to-object)
* [flatten-maven-plugin](https://github.com/rarean/springboot-currencyconversion/blob/master/pom.xml#L117) is probably not needed
