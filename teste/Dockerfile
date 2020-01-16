FROM amazonlinux:latest
LABEL Name=teste Version=0.0.1
COPY . .
RUN yum update -y 
EXPOSE 80
WORKDIR /
CMD /server