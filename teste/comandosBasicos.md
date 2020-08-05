# Basic Commands

### Build the image:
`docker build -t [name of the image] .`
### Run the image:
`docker run -d -p 80:80 -m 500M [name of the image ]`

### Get an aws login:
`aws ecr get-login --region us-east-1 --no-include-email`

### Connet on aws repository:
`docker login -u [user] -p [password] [repository]`

### Choose/tag your image to can push the image:
`docker tag [the name of the image]:latest [the url of the repository]:latest`

### Push the image into a repository:
`docker push [the url of the repository]:latest`
