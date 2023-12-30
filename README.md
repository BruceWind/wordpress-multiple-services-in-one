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
# and then, change 8001:80 to any port you want.

#   Start each service command:
docker-compose up -d

# after that, you can see the service is running. 
```

It is important to modify the docker-compose.yml file:
Adjust the desired HTTP port mapping for each service. 


Access each WordPress instance:

Open your web browser and visit http://localhost:<your-port> where <your-port> is the HTTP port you specified for each WordPress service.


## How it works:

After you start a instance of wordpress. You only expose one http port. The DB container doesn't need to expose to a port.  This is because Wordpress connect db via internal docker network. 

As a result, It is not only isolated, but also safe.


## How much memory does it take?

As I tested, it takes 300 to 500MB memory for wordpress + Mysql. It is not a big deal for a modern computer


## Contributing

Contributions are welcome! If you find any issues or would like to add new features, please submit a pull request.