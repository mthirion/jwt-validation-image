# Info
A spring-boot based application using RedHat keycloak adapter that can be used as a sidecar image to validate JWT token in front of applications.
The maven artifact is called "sso-token-gateway".
The application forwards requests to a "target port" specified in the Spring application.properties

# How to Build
mvn clean package

# How to deploy to Openshift/Kubernetes
You can use the Fabric8 maven plugin to deploy to Openshift, overriding the namesapce on the command line.
While the application leverages RHOAR, the fabric8 image builder uses the Red Hat Fis v4 image with the same OpenJDK (this comes from project supportability reasons).
The service port is set to 8080 in the pom file.

mv fabric8:deploy -Dfabric8.namespace=<project>

# run locally
mvn spring-boot:run
