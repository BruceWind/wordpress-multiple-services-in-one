# wordpress-multiple-services-in-one
🛳️ Manage multiple WordPress instances on a single computer with flexible multi-port configuration.

## Prerequisites

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

## Usage

1. Clone this repository to your local machine:

``` shell

   git clone git@github.com:BruceWind/wordpress-multiple-services-in-one.git
## below is example, you can change the target directory name.
   cp wordpress-multiple-services-in-on/ wordpress-multiple-services-in-one-service-1/
   cp wordpress-multiple-services-in-on/ wordpress-multiple-services-in-one-service-2
#   Navigate to each copied directory:
cd wordpress-multiple-services-in-one-service-1

## use nano or vis to change port mapping.
# vi docker-compose.yml
# and then, change 8001:80 to 8002:80

#   Start each service command:
docker-compose up -d

# after that, you can see the service is running. 
```

In each copied directory, modify the docker-compose.yml file:

Adjust the desired HTTP port mapping for each service. For example, change 8001:80 to <your-port>:80, ensuring that each service has a unique port.



Access each WordPress instance:

Open your web browser and visit http://localhost:<your-port> where <your-port> is the HTTP port you specified for each WordPress service.



## Contributing

Contributions are welcome! If you find any issues or would like to add new features, please submit a pull request.