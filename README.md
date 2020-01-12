# Currency Conversion Microservice

Code Forked from:
[Microservices with Spring Boot](https://github.com/in28minutes/spring-boot-examples/tree/master/spring-boot-basic-microservice) 
and Java - [Part 3 Tutorial](https://www.springboottutorial.com/creating-microservices-with-spring-boot-part-3-currency-conversion-microservice)

Example code part of in28minutes 

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
