#Step1: we want to use ubunutu, let's pull ubuntu
FROM ubuntu:16.04

#Step2: Author Name- Vijay
MAINTAINER Vijay

#Step3 : running apt-get update
RUN apt-get update -y

#Step4 : running apt-get install
RUN apt-get install -y apache2

#Step5 : move the default index page
RUN mv /var/www/html/index.html /var/www/html/index1.html

#Step6 : edit the html page
RUN echo "Welcome to the website created via Dockerfile" > /var/www/html/index.html

#Step7 : Mapping the port
EXPOSE 80

#Step 8: run the default command to start http
CMD apachectl -D FOREGROUND



