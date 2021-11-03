###sonarqube server setup, jenkins integration, maven project and database configuration 


link: https://www.youtube.com/playlist?list=PLxzKY3wu0_FL3TzBnBeBoIMoRkXmYe3VB 


###pre-requisites 


1.An EC2 instance with a minimum of 2 GB RAM (t2.small)
2.Java 11 installation 

##next

cd /opt

sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-8.9.3.48735.zip

sudo unzip sonarqube-8.9.3.48735.zip /opt/sonarqube-8.9.3.48735

cd /opt/sonarqube-8.9.3.48735/

#check for sonar.propeties file


#add user to run sonarqube , under root wee cannot run the sonarrqube server, so create a user to run sonar

### Note : elastic search is not possible if we run sonar under root admin  

useradd sonaradmin # command -useradd 

passwd sonaradmin #to provide password

#change the ownershiip 

chown -R sonaradmin:sonaradmin /opt/sonarqube-8.9.3.48735

#run the sonarqube server

cd /opt/sonarqube-8.9.3.48735/bin/linux-x86-64/ ./sonar.sh start

#check the server status 

cd /opt/sonarqube-8.9.3.48735/bin/linux-x86-64/./sonar.sh status

##Access the serverr console

http://public-ip:9000/
 
##to stop the server  
 
cd /opt/sonarqube-8.9.3.48735/bin/linux-x86-64/./sonar.sh stop
