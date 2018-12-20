# Microservice Architecture

_Monolithic applications are difficult to maintain as they grow.
To achieve an architecture where application is structured as
collections of services will result in a different development process.
By using microservice architecture and thinking of software as
individual modules we can ease the maintenance of the system.
Modularization results in an easy construction and enables the
continuous delivery/deployment of large, complex applications._

***
> **_09.12.2018_**

> **Authors:**
> - Mikkel Ziemer Højbjerg Jensen
> - Diana Strele

### Introduction

As applications get larger and more complex, a [monolithic](https://en.wikipedia.org/wiki/Monolithic_application) approach,
which is the traditional architectural style of building an application,
can become problematic. In a single monolithic application, the
application contains all the code of the business logic. If the
requirements of the system grow, so does the application. Nevertheless,
several developers or even teams of developers, working on a single
monolithic application, are all dependent on the same code. Therefore,
making changes to the application becomes slow as it affects the entire
system. This can lead to drop of code and applications quality.

#### Problem Statement

Companies like Netflix, eBay, Amazon, Twitter have moved from monolithic
to [microservices architecture](https://en.wikipedia.org/wiki/Microservices), as microservices have many
benefits for an Agile and DevOps teams. In essence, microservices help
build an application as a collection of small services, each running on
its own and are independently deployable, resulting in the development
of systems that are scalable and flexible.

To better reflect on microservice architectural approach, during the development of
[HackerNews](https://github.com/ProjectHackernewsGroup04) 
project in Software Development BA degree, we implemented our system 
as microservices. The project consists of several services, implemented 
in different languages and each responsible for different parts of the 
HackerNews application.
Of course, this creates new problems that has to be solved. This
includes, but is not exclusive to, new deployment strategies, new
testing strategies and new integration strategies.

***
### Evidence

* _Principles of Microservice_

Microservices is a subset of Service-Oriented Architecture. Important
advantages of applying modularization are the ability to deploy different
services independently, and reliability. Meaning, ability for a service
to run even if another service is down or is undergoing maintenance.
Another advantage is the ability to build services on different
platforms, it is language independent approach of system development.
There is no formal definition of microservice architecture, but there
are certain characteristics that this architectural style shares.

Typical characteristics of a microservice architecture:

* Multiple components, the ability to replace parts of a system
* Organisation around business capabilities instead of around technology
* Decentralised data management with one database for each service
* Infrastructure automation with continuous delivery

One of the main key characteristics of microservice is that application
consists of multiple components. This is applied so each of the
components can be deployed, changed and redeployed independently.
Having separate services also leads to less overlapping code conflicts
and faster changes deployed to production.

* _Reflect on the use of Microservices_

During AP degree at Cphbusiness, we worked on developing applications in
a monolithic approach. We followed three tier architecture and created
applications as a single services. Our applications had user interface
that consists of HTML pages and javascript, database and server-side
application, that handles requests, retrieves and updates data from the
database and executes domain logic. In this case, any changes to the
system required building a new version of the application and if it was
deployed, it would also require deploying entire system after alteration.

Deciding on using microservice architecture for HackerNews project was
done at the beginning of the project, in the first Sprint. We worked in
a team of five developers on a system that needed continuous integration,
deployment, multiple functionalities and tools to be implemented.
As the software grows in size, it's a good practice to divide the
software up into modules, that are decoupled from each other.
Therefore, we chose microservice architecture, to avoid overlapping
conflicts and promote independent services, that can be easily managed
by different team members and wont conflict with each other’s work.

DZone has recently made a survey that we came across while researching
for this article [(Link to the DZone survey)](https://dzone.com/articles/dzone-research-microservices-priorities-and-trends).
For this survey, DZone asks developers and organizations about using
microservice architecture. Almost 50% are using microservices.
As mentioned earlier, many large companies already have switched to
using this architecture.

![image](https://github.com/UsernameDiana/Investigation_and_Reporting/blob/master/images/Screenshot%202018-12-07%20at%2012.11.18.png)

To clarify on why this architectural approach is a good practice, DZone
asked the users of microservice architecture, what they are using
microservice for. As we stated earlier, when introducing the need for
microservice architecture, that applications grow and become more
complex. Therefore, scalability and faster deployment are the leading
factors for using microservice architecture.

Another interesting choice is flexibility on choosing different tools
and languages. This can be a great learning and experiment process for
the developers as in this field continues curiosity and exploring is of
great value. Microservices provides ease to modify technology stack.
Developers can try new technologies on a specific components of the service.

During our development of HackerNews application, we started with three
different services, `backend`, `frontend` and `ops`, that composed the
application. This collection of three microservices ended up growing in
less than three month, into collection of nine services. Each service
responsible for their own task, each having their own Docker container
and each implemented in different language. According to [Medium](https://medium.com/devopslinks/microservice-architecture-is-it-right-for-your-software-development-eaa951e3ec35),
Netflix changed to microservices around 2012 as they where unable to
build data centers to provide scalability. Today Netflix is using 500+
microservices.

When DZone asked, if using microservices, has made job easier, 80.1%
agreed [(Link to survey graph)](https://github.com/UsernameDiana/Investigation_and_Reporting/blob/master/images/ms.png).
Using containers and virtualization to achieve automated operations,
makes usage of microservice more convenient. 63% is using containers
when working in microservice architecture, both in development and
production [(Link to survey graph)](https://github.com/UsernameDiana/Investigation_and_Reporting/blob/master/images/ms_container_usage.png). 46.02% ensemble their containers via Docker
Swarm [(Link to survey graph)](https://github.com/UsernameDiana/Investigation_and_Reporting/blob/master/images/ms-docker-swarm.png).

* _Pros and Cons_

As mentioned earlier in this blog post, new problems arise when using a
microservice architecture. First of all, developers have to be a lot
more knowledgeable of other applications and the entire domain.
A developer might not have access to every service integrated, so they
need this knowledge to know what to expect from integrated services.
This results in a natural need of more integration testing than usual,
to verify that behaviour.

This brings us to the next point in this section: testing! When testing
applications in a microservice architecture, you’ll have to do
excessive integration testing between services. Why? Because, even
though your organization owns all applications that you integrate to,
you can’t be sure you have access to the codebase for that project.
Actually, you have to treat every service you integrate, even if it’s
your own, as you would a third-party service.

Because applications are all separate services, testing does not
necessarily mean, that an application behaves as you expect. As an
example, if you are developing service A which depends on service B,
and service B changes after you’ve run your tests and deployed your
changes to production, the tests in service A will break. This is
usually solved with API versioning (if talking REST APIs), so breaking
changes will result in a new endpoint, transitioning from /v1 to /v2.

In monolithic application, scaling requires scaling of the entire
application rather than parts that require resources. In a microservice
architecture, you don’t have the same issue. Usually, you will have each
service on their own server, communicating in a private network. This
makes scaling very easy, as you should already have the infrastructure
to scale the services to multiple servers/instances. This is where a
load balancer comes in handy, and can make sure every instance gets the
same load.

***
### Conclusion

Our reason for writing this article was to explore microservices and
give a good understanding of what it stands for. Even though, is seems
to point in a direction that microservices are a better choice for
large system development, we still can't exclude that in some use cases
monolithic approach can be better. Time will show consequences of the
architectural design choices made for the system and its purpose.
With the increase of digital technology usage and multiple device
support, software development is becoming more and more complex.
Perhaps to help developers and businesses along the way of creating
such complex systems, microservice is the answer. Whichever solution of
architecture is selected, both have advantages and disadvantages as
discussed earlier.

To conclude, selecting software architecture should depend on project
requirements, the size of the project, team’s skill level and such.
Therefore, for a small-scale application, monolithic approach is a good
option, but if developing complex system, microservices architecture is
definitely something to consider. Nevertheless, there is always a
possibility to change the architecture, as Netflix, Uber and other
large-scale businesses have done already.

* _Outlook Discussion and Future work_

Initially our HackerNews application started with three microservices, 
as requierements grew, so did the services. 
In the system architecture diagram below, is displayed our applications
architecture as of now. It has a single service accesing the database.

![image](https://github.com/UsernameDiana/Investigation_and_Reporting/blob/master/images/SystemArchitectureDiagram.jpg)

In the future, if system would continue to grow and `Helge_api` would
keep on swarming our application with posts. We would implement a seperate
database for `Helge_api`posts. This would speed up the application and
also follow the characteristincs of microservices architecture with
having decentrilazed data access.

![image](https://github.com/UsernameDiana/Investigation_and_Reporting/blob/master/images/Screenshot%202018-12-14%20at%2012.59.54.png)

***
> **Referenced Literature:**
> - Martin Fowler “Microservices” (25.03.2014) ![link here](https://martinfowler.com/articles/microservices.html)
> - Martin Fowler “MonolithFirst” (03.06.2015) ![link here](https://martinfowler.com/bliki/MonolithFirst.html)
> - Mike Wasson “Microservice architecture style” (13.11.2018) ![link here](https://docs.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices)
> - Anne Marie Glen “DZone Research Microservices Priorities and Trends” (26.07.2018) ![link here](https://dzone.com/articles/dzone-research-microservices-priorities-and-trends)
> - Michael Bryzek “Designing Microservices Architecture the right way” (22.10.2018) ![link here](https://www.youtube.com/watch?v=j6ow-UemzBc)
> - Josh Evans “Mastering Chaos- a Netflix guide to Microservice” (22.02.2017) ![link here](https://www.youtube.com/watch?v=CZ3wIuvmHeM)
> - Medium Corporation "Microservice Architecture — Is It Right for Your Software Development?" (21.08.2018) ![link here](https://medium.com/devopslinks/microservice-architecture-is-it-right-for-your-software-development-eaa951e3ec35)
> - Emily Reinhold "Rewriting Uber Engineering: The Opportunities Macroservices Provide" (20.04.2016) ![link here](https://eng.uber.com/building-tincup/)
> - Tony Mauro of NGINX, Inc "Adopting Microservices at Netflix: Lessons for Architectural Design" (19.02.2015) ![link here](https://www.nginx.com/blog/microservices-at-netflix-architectural-best-practices/)
