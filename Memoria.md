# Memoria.md - Lab6 - Microservices
First we run the Eureka Server.
It is ready for registering new services.
Then we run the first "Account" microservice and we check Eureka:
![Image 0](images/1stAccountTerminal.PNG "First account Microservice running")
![Image 1](images/EurekaAccount.PNG "First account Microservice registered in Eureka")

Re-check Eureka after running the "Web" microservice:
![Image 2](images/WebTerminal.PNG "Web Microservice running")
![Image 3](images/RegisteredEureka.PNG "Web Microservice registered in Eureka")

Finally change the port in application.yml to 4444 for running the second "Account" microservice:
![Image 4](images/2ndAccountTerminal.PNG "Second account Microservice running")
![Image 5](images/AllRunning.PNG "Second account Microservice registered in Eureka")

What happens when we kill the microservice with port 2222?
The web server could show us both "Account" instances:
![Image 6](images/WebInfoBeforeKill.PNG "Web server info about Account microsservice instances")

After killing the one in server 2222:
![Image 7](images/Kill2222.PNG "Killed the Account microservice in port 2222")

The web server shows:
![Image 8](images/ErrorWebServer.PNG "The web server shows an error when trying to reach the account")

But it still knows about the tow instances of the "Account" microservices:
![Image 9](images/WebInfoAfterKill.PNG "Web server info about Account microsservice instances")

After refreshing, the server can still find the account because it has gotten the info of 
the replica microservice on port 4444:
![Image 9](images/Account.PNG "Web server info about Account microsservice instances")
