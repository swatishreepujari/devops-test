FROM java:8

RUN apt-get update -qq && apt-get install -y maven && apt-get clean
RUN PATH="/usr/share/maven:$PATH"
RUN export PATH


WORKDIR /opt/workspace

ADD pom.xml /opt/workspace/pom.xml

# Adding source, compile and package into a fat jar
ADD src /opt/workspace/src
RUN ["mvn", "clean" , "install"]

CMD ["mvn" , "tomcat7:run"]