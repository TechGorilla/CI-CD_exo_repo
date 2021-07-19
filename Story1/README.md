## Story 1 :
   
 >   As a DevOps engineer, I want to have a CI/CD pipeline for my application. \
 >       The pipeline must build and test the application code base. \
 >       The pipeline must build and push a Docker container ready to use. \
 >       The pipeline must deploy the application across different environments on the target       infrastructure.
    
_Bonus point: Separate the backend and the frontend in different pipelines and containers._

## First step

Create a new directory "CI-CD_EXO_REPO/Story1/" for the first story elements.\
The Java and React pipelines will documented in their respective directories "JavaDev" and "ReactDev".

### TIP
To run jenkins on a Windows environment or other OS, you can use the official Jenkins container.

```Docker
docker run -d -v jenkins_home:/var/jenkins_home -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts-jdk11

# Pulls from the official repository and maps the port to port 50000
# to connect agents not using SSH build agents (use for testing only).
```

__docker-compose__
```Docker
# Example from Wes Higbee, creating a jenkins container and a mail server container

version: "3.8"

services:

  jenkins:
    image: jenkins/jenkins:2.255
    ports:
    - "127.0.0.1:9080:8080"
    volumes:
    - ./jenkins_home_on_host:/var/jenkins_home
    # using a bind mount to the host `./jenkins_home` means I can easily peruse the jenkins_home files without needing to "get into the container"
    restart: unless-stopped
    # a named volume is fine too - jenkins_home:/var/jenkins_home



  # I like docker-compose because I can easily spin up multiple apps like a test email server alongside jenkins! for testing email notifications from jenkins (later)
  mails:
    image: mailhog/mailhog
    restart: unless-stopped
    ports:
    - "127.0.0.1:8025:8025" # mailhog's web app (think test instance of gmail)
    # "127.0.0.1:1025:1025" # jenkins will use `mail:1025` to send emails, only map to host if you want to send files


## NOTES:
# Host port bindings are constrained to listening on 127.0.0.1
# - avoids external access to services
# - To open external access:
#   - Remove IP address constraint to open the flood gates
#   - Bind to another IP 
# - https://docs.docker.com/config/containers/container-networking/#published-ports
```