FROM amazonlinux:with-sources

WORKDIR /
LABEL Name=teste Version=0.0.1
COPY . .
Run chmod +x /server
EXPOSE 80

CMD "./server"