## INVESTIGATION AND REPORTING - Blog Entry


### _Abstract Proposals:_

> _state the problem_ <br>
> _say why it is interesting_ <br>
> _say what your solution achieves_ <br>
> _say what follows from your solution_ <br>

**Microservice architecture**

* Monolithic applications are difficult to maintain as they grow.
We need another architecture to maintain ease of maintainance.
* To achieve another architecture we'll have to think about software as individual modules.
This results in a different development process and new problems to solve.
* By using a microservice architecture, every application has its own responsibility.
This makes deployment of changes faster and independent from everything else.
Also, this results in more configuration files, but they're way more concise, since every project has their own.
* Dockrization ended up being easier, and the modularization resulted in an easy construction of
a docker-compose file for starting up dependency projects locally. 

**Docker containers and Virtual Machines**

* Working on the same system on local machines with different OS is
complicated and will result in various errors which would slow down the
development.
* Using Virtual Machine with the same environment and containers that
isolates software/service can assures to not hear 'But it worked on my machine...".
* Our development takes place on a Virtual Machine, which contains a Docker
file for each service/project. Dockerfile builds a Docker image, containing
projects code.
* Docker image is the service/project. Docker image can be ran on any
machine if it has docker.

**Continuous Integration and Git**

* Being able to deploy to production often and easily is an important part
when developing larger systems that undergo constant maintenance and monitoring.
* Deploying regularly will avoid large deployments at once, therefor we
can mitigate errors faster.
* By using various tools and services we are able to implement CI in our
development process.
* This practice of integrating changes from different developers as
early as possible, makes sure the code individual developers work on
doesn’t divert too much.

***
> **Authors:**
> - Mikkel Ziemer
> - Diana Strele
