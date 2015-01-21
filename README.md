# A great place to start your CAS Adventure!

## Getting started

* Download and install an appropriate JDK 1.7 (http://www.oracle.com/technetwork/java/javase/downloads/index.html).
Make sure you download the JDK and not the JRE.
* Download https://github.com/UniconLabs/cas-strap/archive/master.zip
* unzip master.zip

Much of the configuration of a custom CAS deployment is the same as with a Maven overlay, but is now controlled by
Gradle with a custom, streamlined interface.

## Running the server

On Linux/Mac:

```shell
./cas-strap run
```

On Windows:

```shell
cas-strap.bat run
```

## Building a war

On Linux/Mac:

```shell
./cas-strap war
```

On Windows:

```shell
cas-strap.bat war
```

## Properties files location

By default, cas-strap will use `WEB-INF/cas.properties` for properties. For external configuration, the location of the
`cas.properties` file is controlled by 2 exclusive system properties (in order of precedence): `etc.dir` and `etc.root`.

If the `etc.dir` system property is set, cas-strap is configured to use `${etc.dir}/cas.properties` for its properties.

If the `etc.dir` system property is not set, but the `etc.root` is, cas-strap is configured to use
`${etc.root}/etc/cas/cas.properties` for it's properties.

This behavior can be modified in the `/src/main/webapp/WEB-INF/spring-configuration/propertyFileConfigurer.xml` file.