## INVESTIGATION AND REPORTING - Blog Entry


### _Abstract Proposals:_

**Docker containers and Virtual Machines**

> _state the problem_ <br>

working on the same system on local machines with different
OS is complicated and will result in various errors which would slow
down the development.

> _say why it is interesting_ <br>

Developers using Virtual Machine with the same environment and containers that
isolates software/service can assures to not hear 'But it worked on my machine...".
Meaning that any machine can ran the docker image containing the project,
developed in the same environment.

> _say what your solution achieves_ <br>

> _Our development takes place on a Virtual Machine, which contains a Docker
file for each service/project. Dockerfile builds a Docker image, containing
projects code. This image sits on top of the machine, meaning, that the
Docker image is the service/project. Docker image can be ran on any
machine if it has docker._ <br>

> _say what follows from your solution_ <br>



**Continuous Integration and Git**

> _state the problem_ <br>

Being able to deploy to production often and easily is an important part
when developing larger systems that undergo constant maintenance and monitoring.

> _say why it is interesting_ <br>

Deploying regularly will avoid large deployments at once, therefor we
can mitigate errors faster.

> _say what your solution achieves_ <br>

By using various tools and services we are able to implement CI in our
development process. One of the ground helping tool is version control
system - Git, once the changes are pushed to master, master is deployed
to production automatically via CircleCI.

> _say what follows from your solution_ <br>

[link to HackerNews CI chain](https://github.com/ProjectHackernewsGroup04/Ops#cicd-chain)


**Microservice architecture**

> _state the problem_ <br>
Monolithic applications are difficult to maintain as they grow. 
We need another architecture to maintain ease of maintainance. 

> _say why it is interesting_ <br>
To achieve another architecture we'll have to think about software as individual modules. 
This results in a different development process and new problems to solve. 

> _say what your solution achieves_ <br>
By using a microservice architecture, every application has its own responsibility. 
This makes deployment of changes faster and independent from everything else.
Also, this results in more configuration files, but they're way more concise, since every project has their own.

> _say what follows from your solution_ <br>
Dockrization ended up being easier, and the modularization resulted in an easy construction of 
a docker-compose file for starting up dependency projects locally. 

***
> **Authors:**
> - Mikkel Ziemer
> - Diana Strele
