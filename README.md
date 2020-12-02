# archtecture
Archtecture Study

## Database
* ACID vs BASE -> https://en.wikipedia.org/wiki/Eventual_consistency
```
Eventually-consistent services are often classified as providing BASE (Basically Available, Soft state, Eventual consistency) semantics, 
in contrast to traditional ACID (Atomicity, Consistency, Isolation, Durability) guarantees. 
In chemistry BASE is opposite to ACID, which helps remembering the acronym.
According to the same resource, these are the rough definitions of each term in BASE:

(B)asically (A)vailable: basic reading and writing operations are available as much as possible (using all nodes of a database cluster), 
but without any kind of consistency guarantees (the write may not persist after conflicts are reconciled, the read may not get the latest write)

(S)oft state: without consistency guarantees, after some amount of time, we only have some probability of knowing the state, since it may not yet have converged

(E)ventually consistent: If the system is functioning and we wait long enough after any given set of inputs, we will eventually be able to know what the state of the database is, and so any further reads will be consistent with our expectations
```

* ACID -> https://pt.wikipedia.org/wiki/Transa%C3%A7%C3%A3o_(banco_de_dados)
```
Atomicidade -> Ou tudo ou nada (capacidade de rollback de uma transaçao ou compensation)
Consistência -> Ter Constraints, por exemplo, foreign key, unique key, not null etc. Garante integridade dos dados.
Isolamento -> Chamadas concorrentes devem ser tratadas de maneira sequencial. Uma nao pode interferir na outra.
Durabilidade -> Nao persistir em memoria RAM, persistir em disco para garantir que vai ser possivel acessar o dado mesmo depois de alguma falha de hardware.
```

* CAP -> https://pt.wikipedia.org/wiki/Teorema_CAP
```
Uma vez que decidimos que temos que ter patition tolarance, temos que decidir entre ter alta disponibilidade (todos tenham acesso ao dado, ainda que nao seja o mais recente) ou consistencia (todos tenha acesso ao dado mais recente ou todos tenham um erro).
```

## Microservices
* Microservices -> https://martinfowler.com/articles/microservices.html
* Microservices Guide -> https://martinfowler.com/microservices/
* Event & CQRS -> https://martinfowler.com/articles/201701-event-driven.html
* NuBank Microservice Example -> https://github.com/nubank/basic-microservice-example (sensacional)
* Hexagonal Archtecture -> https://en.wikipedia.org/wiki/Hexagonal_architecture_(software)

### Key principals for Microservices

* Technology Heterogeneity
```
Each team can decide what technology and data store uses for their microservice, of course there are trade off for the company to maintain a large number of database to use (libraries, CI/CD tools, monitoring and logs).
```

* Resilience
```
Once we have our system separated in many small services we gain resilence, because if one service fail we can continue operate other services, we can respond fast for errors and send appropriate message to the client while we keep the others features working fine.
Of course, it needs a better design and apply some techniques like Circuit Breaker and Retry.
```

* Scaling
```
It is easier & cheaper to scale a microservice than a monolitic, we can focus on scaling just the services that we need.
```

* Ease of deployment
```
It is easier to deploy a microservice, it helps us deploy often instead avoiding deployment because of the risk of a big monolith.
```

* Organizational Alignment
```
We know that small teams works better than big teams. Small teams focues on some business problem is aligned with microservices archtecture, as we can give team autonomy, accountability and empowerment.
```

* Composability
```
We can resuse and compose services.
We have to be careful avoiding coupling services, sometimes it is better to replicate code. It is some trade-off that we need to do.
```

* Optimizing for Replaceability
```
If we follow the two week microservice rule, it is better to replace a legacy microservices.
We have a lot of companies struggling with legacy and they even try to remove those system because of the risk.
```

* General
```
For general decisions we need to decide based on trade-offs, for that, we must have have business goals, aligned with architecture principles and practices to decide those trade-offs.
```
