#using official maven image
FROM maven

#copying SpringMVCXML into container
COPY Java_Sample_App/SpringMVCSecurityXML /java_app/SpringMVCSecurityXML

# Set the Work directory
WORKDIR /java_app/SpringMVCSecurityXML

# buuild the application
RUN mvn clean install 

FROM tomcat:8 

#copy the application in tomcat server
COPY --from=0 /java_app/SpringMVCSecurityXML/target/SpringMVCSecurityXML.war /usr/local/tomcat/webapps

# run the application
RUN echo "Deployment successful"

