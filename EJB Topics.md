EJB 1
-----

 

EJB Concepts

EJB 2.0 vs EJB 3.0

Sample example on Session beans

 

 

EJB is a component based framework for building and deploying distributed
application

Why EJB? - fits into entire application

	EJB Services:

		- Transactions

		- Security

		- Persistence

		- Remoteability

		- Interceptors

		- Timer/Scheduling

		- State Management

		- Messaging

		

	EJB as a Container

		- it provides the set of services

		- provides verious setup services

		

	EJB containers are deployed on Application Servers like JBOSS, Glassfish to
provide what a ejb component is being developed for.

	

	EJB Kinds of Beans

	- Session Bean

	- Entity Bean

	- Message Driven Bean

	

	EJB 2.0

	- programatic and declarative configurations (config files)

	- if you need to create a Session Beand or any kind of beand you need to have:

		- some sort of Interfaces - Remote, Home Interface, Local Interface

		- Bean - implements ALL the interfaces

	- Beans are configured using XML files

	- Entity Beans - purely for persistence

	- Session Bean - used for business logic

	- there are 2 types of Entity Beans:

		- CMP - Container-Managed Persistence - you relly on this container

		- BMP - Bean-Managed Persistence - programatic, programmer must write jdbc code
to insert data into database

			

			BMP

			- Bean managed persistence

			- Developer has to write persistence code for ejbLoad(),ejbStore() for entity
beans

			- Should follow this approach only when its bare necessity to write your own
persistence logic.Usually container managed persistence is quite sufficient and
less error prone.

 

			CMP

			- Container managed persistence

			- Developer maps the bean fields with the database fields in the deployment
descriptors.

			- Developer need not provide persistence logic (JDBC) within the bean class.

			- Containiner manages the bean field to DB field synchronization.

 

			The point is only ENTITY beans can have theier pesristence mechanism as CMP or
BMP. Session beans, which usually contains workflow or business logic should
never have persistence code.Incase you choose to write persistence within your
session bean, its usefull to note that the persistence is managed by the
container BMP.Session beans cannot be CMP and its not possibel to provide field
mapping for session bean.

	- Message Driven Bean - EJB can communicate to JMS

	- Client for EJB - Servlet program

	

				

	EJB \>3.0

	- configuration using annotations

	- POJO Based Beans : POJO + Annotation = EJB

	- Beans are configured using annotations

	- no concept of Entity Beans in EJB; they where replaced by JPA

	- we have only Session Bean and Message Driven Bean

	- JPA is annotation based and is used to persist records into database

	- Message Driven Bean

	- EJB can be exposed as Webservices

	

	

	

	EJB 3.2 - easy development and testing

	

 

		

	Beans use cases

		Session Bean - might be used for Cradi Card validtion, Entity validation ..;
eache request is a independent request

			Stateless Session Bean - you don't want your session to be tracked; eache
request is different and you don't require to store anything on the server;
validate user; credit card verification; inventory check

			Statefull Session Bean - shopping cart or order fulfillment; multiple steps with
validations

		Entity - you want to store your data into a persistence

		Message Driven Bean

		

		Flight booking

			- browse -\> we use Session Bean

			- select flight -\> we use Session Bean

			- address details -\> we use Session Bean

			- passport details -\> we use Session Bean

			- credit card details -\> we use Session Bean

			- confirmation -\> we use Entity Bean

			

		Message Driven Bean - use cases

			- msn.com

			- asynchronous messages

			- delayed operations and async like bank salary paiment

			

		

	

	

	Creating Sample Session Bean

		- Eclipse

		- JBOSS

		- create "EJB Project", generate descriptor, finish

		- New-\> create Session Bean

		- export EJB jar file

		

		

	

![](ejb-img-1.PNG)
