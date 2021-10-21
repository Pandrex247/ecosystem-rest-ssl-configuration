# JAX-RS extension
JAX-RS Extension help to define the certificate alias rest client will use

To enable this we need to include the next dependency on the application

```xml
<dependency>
  <groupId>fish.payara.ecosystem.jaxrs</groupId>
  <artifactId>ecosystem-rest-ssl-configuration</artifactId>
  <version>1.0</version>
</dependency>
```
Also it is needed to specify the next property for Rest Client call

|Property|Description|
|--------|-----------|
|fish.payara.jaxrs.client.certificate.alias|The alias name of the certificate|


# Example

```java
ClientBuilder.newBuilder().property("fish.payara.jaxrs.client.certificate.alias", "someAliasName").build()
.target(new URI("https://localhost:8080/service")).request().get(Service.class);
```

**NOTE:** For this to work, you need to include the certificate with the given alias in the default payara keystore.