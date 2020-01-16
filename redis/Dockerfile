FROM amazonlinux:latest
LABEL Name=teste Version=0.0.1
COPY . .
RUN yum update -y 
RUN yum install mysql -y
RUN mysql -u admin -pteste123 -h database-1.caoms6p6ftnq.us-east-1.rds.amazonaws.com -e "create database batata;use batata;create table if not exists unicorns (unicornid varchar(100), unicornlocation varchar(100));"
EXPOSE 80
WORKDIR /
