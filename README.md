# Backend code challenge

For the creation of this project I used Ruby on Rails, an open-source software used to build Rest API. The web server was built using XAMPP, MySQL and phpMyAdmin.

The project is able to register vehicles, collect their locations in real time and delete the vehicles when it will stop emitting location updates.

## Installation

```console
# XAMPP, phpMyAdmin and Ruby on Rails are required to run this project.

# https://www.apachefriends.org/download.html
# https://www.phpmyadmin.net/downloads/
# https://www.ruby-lang.org/en/downloads/


# open command line and cd to the project directory
$ cd vehicles


# install rails
$ gem install rails


# install the requirements
$ install bundler
$ bundle install


# once the bundle is installed and XAMPP has started running Apache and MySQL we can start our rails project
$ rails s
```



## Postman

We can test our get, post and delete requests using Postman.

GET :

```
# Request URL
http://localhost:3000/vehicles/
```

POST : We are going to use two posts. The first one will register the vehicle, the second one will update its location data.

First Post
```
# Request URL
http://localhost:3000/vehicles/

# Headers | Content-type - application/json

# Body
{
    "id":"852e593c-057b-417e-a2cf-4315b3cfb31"
}
```

Second Post
```
# Request URL
http://localhost:3000/vehicles/852e593c-057b-417e-a2cf-4315b3cfb31/locations

# Headers | Content-type - application/json

# Body
{
    "id":"852e593c-057b-417e-a2cf-4315b3cfb31",
    "lat":85.5,
    "lng":82.1,
    "at":"2021-11-14T01:09:33.258Z"
}
```

DELETE :

```
# Request URL
http://localhost:3000/vehicles/852e593c-057b-417e-a2cf-4315b3cfb31
```



## Handling more than 1000 vehicles

For demonstrating how the solution would handle 1000+ vehicles, I used Faker. A library for generating fake data. As we can see, it created 1000+ rows of data.

![image](https://user-images.githubusercontent.com/72938289/141835011-8f8eb24e-9889-473a-9031-9c55240b55c8.png)





```


```

The optional ```--rm``` flag removes the container filesystem on completion to prevent cruft build-up. See: https://docs.docker.com/engine/reference/run/#clean-up---rm

The optional ```-t``` flag allocates a pseudo-TTY which allows colored output. See: https://docs.docker.com/engine/reference/run/#foreground

Use the following command to access the saved results:

```
docker run --rm -t -v "$PWD/results:/opt/sherlock/results" mysherlock-image -o /opt/sherlock/results/text.txt user123
```

The ```-v "$PWD/results:/opt/sherlock/results"``` options tell docker to create (or use) the folder `results` in the
present working directory and to mount it at `/opt/sherlock/results` on the docker container.
The `-o /opt/sherlock/results/text.txt` option tells `sherlock` to output the result.

Or you can use "Docker Hub" to run `sherlock`:
```
docker run theyahya/sherlock user123
```

### Using `docker-compose`

You can use the `docker-compose.yml` file from the repository and use this command:

```
docker-compose run sherlock -o /opt/sherlock/results/text.txt user123
```

## Contributing
We would love to have you help us with the development of Sherlock. Each and every contribution is greatly valued!

Here are some things we would appreciate your help on:
- Addition of new site support ¹
- Bringing back site support of [sites that have been removed](removed_sites.md) in the past due to false positives


[1] Please look at the Wiki entry on [adding new sites](https://github.com/sherlock-project/sherlock/wiki/Adding-Sites-To-Sherlock)
to understand the issues.

## Tests

Thank you for contributing to Sherlock!

Before creating a pull request with new development, please run the tests
to ensure that everything is working great.  It would also be a good idea to run the tests
before starting development to distinguish problems between your
environment and the Sherlock software.

The following is an example of the command line to run all the tests for
Sherlock.  This invocation hides the progress text that Sherlock normally
outputs, and instead shows the verbose output of the tests.

```
$ cd sherlock/sherlock
$ python3 -m unittest tests.all --verbose
```

Note that we do currently have 100% test coverage.  Unfortunately, some of
the sites that Sherlock checks are not always reliable, so it is common
to get response problems.  Any problems in connection will show up as
warnings in the tests instead of true errors.

If some sites are failing due to connection problems (site is down, in maintenance, etc)
you can exclude them from tests by creating a `tests/.excluded_sites` file with a
list of sites to ignore (one site name per line).

## Stargazers over time

[![Stargazers over time](https://starcharts.herokuapp.com/TheYahya/sherlock.svg)](https://starcharts.herokuapp.com/TheYahya/sherlock)

## License

MIT © Sherlock Project<br/>
Original Creator - [Siddharth Dushantha](https://github.com/sdushantha)
