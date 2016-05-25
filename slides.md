## Architecture, Frontend 
## and a Bit of Frontend Architecture
Jan Hein Hoogstad   
offcourse.io   
@yeehaa

<!---

Good morning everyone. Really excited to be here. My name is Jan Hein Hoogstad. In my previous life, I was a professor in philosophy and cultural studies. But that's all behind me. Nowadays, I'm running a startup called 'Offcourse'. Offcourse is going to radically change the way you learn new skills online, but that's not what I'm going to talk about in this presentation. Please check out our website if you want to know more.

Today, I am going to talk about buildings, actual buildings - houses, towers, bridges, etc. And I will discuss what these constructions share with the artifacts that we, developers, are creating: programs, libraries, and applications.

-->

---
"All that functional stuff, immutability, no side effects... I understand why this makes sense on the backend, but on the frontend..." 

—A Friend.

<!---

The inspiration for this presentation came from a comment that a good friend of mine made when I told him that I had decided to use clojurescript as the language for the offcourse frontend application. While I cannot remember his words verbatim, I know that it was something along the lines of:  

"All that functional stuff, immutability, no side effects... I understand why this makes sense on the backend, but on the frontend..." 

What fascinates me about this remark is not the content, but the assumptions about frontend development that were implied in his words. Let me spell them out for you:

-->

---
|Backend                |Frontend                     |
|---------------------  |-----------------------------|
|Complex                |Simple                       |
|Core Product           |Marketing                    |
|Long Term Investment   |Temporary Artifact           |
|Architectural Patterns |Whatever Works               |

<!---

His comment suggests that:

The backend is complex, while the frontend is not.

The backend represents the core product, while the frontend is merely a by product, mainly used for marketing purposes.

Consequently, the frontend is just a temporary artifact while the backend should be a long term investment

And last but not least, that architectural patterns are only important on the  backend, while the frontend developer should simply use whatever works

My own views on frontend development are diametrically opposed to these assumptions. I argue that architecture does matter on the frontend. Today more than ever. My main two reasons are the following:

-->

---
"Serverless" application architectures offer tremendous cost savings and colossal horizontal scaling ability, with the side benefit of encouraging loosely coupled design. The advantages are so profound, that the days of monolithic application servers might be numbered." 

—Obie Fernandez

<!---

First, the current transition towards so-called serverless architectures means that the frontend is becoming more and more important. Obie Fernandez, for instance, claims:

"Serverless" application architectures offer tremendous cost savings and colossal horizontal scaling ability, with the side benefit of encouraging loosely coupled design. The advantages are so profound, that the days of monolithic application servers might be numbered." 

Without a backend, however, the frontend application ofter becomes the place where all the services are connected. As a consequence, seriously thinking about frontend architectures is no longer a luxury but a must.

-->

---
"We shape our buildings; thereafter they shape us." 

—Winston Churchill

<!--

Still, the second reason is much more important. I believe, that not thinking about architecture is a mistake under all circumstances. Here I'm in the company of statesmen like Winston Churchill who claimed that:

"We shape our buildings; thereafter they shape us."

Not thinking about the architecture of our programs means that we are shaped by implicit instead of explicit design choices.

-->

---
## Architecture
## Software and Architecture
## Frontend Architecture

<!---

This presentation consists of three parts. 

In the first, I will talk about architecture in general, how its use in software development is significally different from its physical counterpart, and why this matters.

In the second part, I will go through a some important design patterns and show what they look like as actual buildings

The last part, focusses on frontend architecture patterns in particular and how serverless changes everything.

-->

---
## Architecture

---
<img class="stretch" data-src="assets/brick-generic.jpg">

"Lisp isn’t a language, it’s a building material." 

—Alan Kay.

<!--- 

Alan Kay famously said that: 

"Lisp isn’t a language, it’s a building material." 

To me, this is exemplary of the way we, developers, conceive architecture. We understand architecture in terms of the building blocks that we use, such as:

+ Languages
+ Abstractions
+ Libraries and Frameworks
+ Patterns

Although code reading groups - such as the classical code reading group - are becoming more common, the actual artifacts that we produce are still rarely discussed. We don't talk about programs like we do about books or our favorite netflix shows. We cannot stop comparing languages, patterns, and libraries, but we forget to look at the product of these building blocks: the program as program. 

-->

---
<img class="stretch" data-src="assets/libeskind.jpg">

"Architecture is not based on concrete and steel, and the elements of the soil. It's based on wonder." 

—Daniel Libeskind

<!---

Actual Architects tend to do the exact opposite. Daniel Libeskind for instance said that: 


"Architecture is not based on concrete and steel, and the elements of the soil. It's based on wonder." 

Although this quote is a bit too new-agey for my taste. It does clearly illustrate the way architects view their profession. To them, architecture does not deal with the building blocks that they use. They care about the constructions that emerge from these individual pieces.

-->

---
<img class="stretch" data-src="assets/eiffel-tower.jpg">

“Eiffel saw his Tower in the form of a serious object, rational, useful; men return it to him in the form of a great baroque dream which quite naturally touches on the borders of the irrational ... architecture is always dream and function, expression of a utopia and instrument of a convenience.” 

—Roland Barthes

<!---

Of course, leave it to the philosophers to go even a step further. Roland Barthes, for instance, said that:

“Eiffel saw his Tower in the form of a serious object, rational, useful; men return it to him in the form of a great baroque dream which quite naturally touches on the borders of the irrational ... architecture is always dream and function, expression of a utopia and instrument of a convenience.” 

To put this differently, architecture is always a expression of a future that can be, of could have been. It's the materialization of common ideals. 

-->

---
"Ethos"

—Aristotle


<!-- 

Architecture is what Aristotle called an ethos. which literally means 'accustomed space'

-->

---
<img class="stretch" data-src="assets/unlivable-house.jpg">

"A House Is Not A Home" 

—Burt Bacharach & Hal David

<!---

Which his great successors Burt Bacharach and Hal David translated into "A House is Not a Home"

-->

---
<img class="stretch" data-src="assets/eiffel-tower.gif">

"Architecture starts when you carefully put two bricks together. There it begins." 

—Ludwig Mies van der Rohe

---
1. Lived Space
2. Construction 
3. Bricks and Mortar

<!---

To sum this up: Architecture is actually three things at the same time:

An material representation of a desired future, a set of ideals, a lived space, an ethos, a home

It's a technical construction. A feat of engineering. The product of many though choices.

But, of course, it's also simply collection of blocks. Or, as the famous modernist architect Mies van der Rohe said: "Architecture starts when you carefully put two bricks together. There it begins." 

-->

---
## Software and Architecture

<!---

In the next section of this presentation, I will look at different software architecture patterns by comparing them to actual buildings.

-->

---
<img class="stretch" data-src="assets/three-stories.jpg">

"The main principle behind layered architectures is that of 'separation of responsibility'. Each layer is responsible for a finite amount of work."

—Jean Paul Boodhoo

<!---

The best known, and probably still most commonly used, software architecture pattern is the so-called layered architecture. 

"The main principle behind layered architectures is that of 'separation of responsibility'. Each layer is responsible for a finite amount of work."

This is comparable to the classic home layout, as idealized in the dollhouse in the picture on this slide. In this house, each floor has a clearly defined responsibility. The bottom layer consists of the living room, the middle is the parent's bedroom, and the top one is where the baby sleeps.

In software development, a layered architecture can have many layers, but in its simplest form it consists of a persistence layer with business and presentation layers build on top of it.

-->

---
<img class="stretch" data-src="assets/escher.jpg">

"Unfortunately, people using layered architectures can often run into a scenario where they introduce an unnecessary amount of coupling between layers of their application."

—Jean Paul Boodhoo

<!--

In practice, however, layered architectures often end up like this Escher print. This is due to the fact that the clearly defined layers of such a architecture can easily get mixed up.

(and yes, I'm looking at you Active Record)

"Unfortunately, people using layered architectures can often run into a scenario where they introduce an unnecessary amount of coupling between layers of their application."

As a result of this tight coupling, layered architecture are often hard to scale or refactor.

-->

---
<img class="stretch" data-src="assets/oude-kerk-before.jpg">

"The Microkernel architectural pattern applies to software systems that must be able to adapt to changing system requirements."

—Dharmesh Sheta

<!--

The microkernel patters aims to correct the flaws of the layered architecture. This 

"architectural pattern applies to software systems that must be able to adapt to changing system requirements."

The kernel in the name functions as a hub that can be extended by plugins or adapters. While this may not be a common pattern in real-world architecture, it is one of the oldest.

The 'Oude Kerk' in Amsterdam for instance was build using a very similar design pattern. This is best illustrated visually. First look at its original state around 1306.

-->

---
<img class="stretch" data-src="assets/oude-kerk.jpg">

"It separates a minimal functional core from extended functionality and customer-specific parts. The microkernel also serves as a socket for plugging in these extensions and coordinating their collaboration."

—Dharmesh Sheta

<!--

And compare that to how it looks now. The core chuch is still intact, but is now augmented by many small modules that each extended the original building which custom functionality, such as housing, and - ironically - prostitution.

This quote about the microkernel pattern therefore equally applies to the architecture of the 'Oude Kerk':

"It separates a minimal functional core from extended functionality and customer-specific parts. The microkernel also serves as a socket for plugging in these extensions and coordinating their collaboration."

-->

---
<img class="stretch" data-src="assets/jfk-airport-plan.png">

"In short, the microservice architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API."

—Martin Fowler

<!--

No presentation on software architecture nowadays, however, would be complete without a extension discussion of the current favorite: the microservices pattern. Martin Fowler defines this pattern as follows:

"... the microservice architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API."

Just like most modern airports consist of separate terminals and other building that each serves a particular purpose. The microservices architecture loses the concept of a predefined whole.

In direct contrast to the microkernel architecture, microservices also do not need a central hub to work properly. Each service functions independently as well as in conjunction with others.

-->

---
| Characteristics                | Solution                            |
|--------------------------------|-------------------------------------|
| Componentization               | Containers / Functions as a Service |
| Smart Endpoints and Dumb Pipes | Messaging Bus                       |
| Design for Failure             | Asynchronous Coupling               |
| Evolutionary Design            | Continuous Deployment Pipeline      |

<!---

Although, the microservices patters is not as clearly defined as the others, it does have a couple of common characteristics.

The first is that it distributes the business logic of an application over multiple components. Each of these components has it's own clearly defined domain and is individually deployed. Usually in the form of a Docker Container, or - even more state-of-the-art - an AWS Lambda function.

These services communicate with each other through a message broker - for instance zeromq or rabbitmq. This marks the second characteristic 'smart endpoints dumb pipe'. I will come back to this in a second.

Another very important quality of a microservices architecture is that it is designed for failure. The way to accomplish this is to avoid synchronous coupling between the components as much as possible. Instead, they only communicate via the aforementioned messaging pipeline. This also allows for replica's and backup services in case one of them fails.

Lastly, microservices are characterized by an evolutionary design. They are commonly part of a continuous integration and continuously deployment pipeline. As a result, developers can roll out individual features one at a time, rather than fitting them in periodical release cycles.

-->

---
<img class="stretch" data-src="assets/terminal-schema.png">

"The microservice community favours an alternative approach: smart endpoints and dumb pipes. Applications built from microservices aim to be as decoupled and as cohesive as possible - they own their own domain logic and act more as filters in the classical Unix sense - receiving a request, applying logic as appropriate and producing a response."

—Martin Fowler

<!--

Of these characteristics, I want to single out the 'Smart Endpoints, Dumb Pipes'. To me, this mark the core of the microservices pattern. Martin Fowler describes this characteristic as follows:

"The microservice community favours an alternative approach: smart endpoints and dumb pipes. Applications built from microservices aim to be as decoupled and as cohesive as possible - they own their own domain logic and act more as filters in the classical Unix sense - receiving a request, applying logic as appropriate and producing a response."

This flow should be instantly recognizable to any functional programmers. In a microserver architecture. Each service basically works as a - pure or impure - function, with clear inputs and outputs. (unfortunately the airport terminal in the schema is an impure function...) To me, a microservices architecture and functional programming are therefore a natural fit.

-->
---
<img class="stretch" data-src="assets/beautiful-airport.jpg">

"Engineering is not a science. Science studies particular events to find general laws. Engineering design makes use of the laws to solve particular practical problems. In this it is more closely related to art or craft."

—Ove Arup

<!---

To me, the appeal of a microservices architecture lies in the fact that it encourage a developer to think about her specific domain. As opposed to all other patterns that I have discussed, this design pattern does not try to force the domain knowledge to fit the architecture, but vice versa. A properly executed microservices architecture values good design. Or as Ove Arup puts it:

"Engineering is not a science. Science studies particular events to find general laws. Engineering design makes use of the laws to solve particular practical problems. In this it is more closely related to art or craft."

-->

---
## Frontend Architecture

---
"All that functional stuff, immutability, no side effects... I understand why this makes sense on the backend, but on the frontend..." 

—A Friend.

<!---

From well-designed architectures, it's only a tiny step back to my friend's objection:

"All that functional stuff, immutability, no side effects... I understand why this makes sense on the backend, but on the frontend..." 

By now, I have hopefully convinced you that it's important to think about architecture in general. But I haven't explained why and how this applies to the frontend. 

My answer will be a simple one though. A serverless frontend architecture should be shaped after a microservices architecture. Even though the code probably run on the same client, rather than distributed, it's still valuable to conceive the application as if it's a collection of services.

Before I explain the what and how of the serverless frontend architecture that we use at offcourse, I want to discuss some common alternatives.

1. Shantytown Architecture
2. Frameworks

-->

---
<img class="stretch" data-src="assets/shantytown.jpg">

"Too many of our software systems are, architecturally, little more than shantytowns. Investment in tools and infrastructure is often inadequate and the tools that are used are primitive. Parts of the system grow unchecked, and the lack of architecture and planning allows problems in one part of the system to erode and pollute adjacent portions. Deadlines loom like monsoons, and architectural elegance seems unattainable."

—Brian Foote and Joseph Yoder

<!---

Shantytown aka big ball of mud aka spaghetti code

-->
---
<img class="stretch" data-src="assets/prefab.gif">

"More Productive Out Of The Box." 

—Ember
    
<!---

So what's the first stage to clean up this shantytown, this big ball of mud, or jquery spaghetti... a framework ofcourse. At first glance, frameworks have a lot of advantages. Like the slogan for the Ember framework states. They make the coder more productive out of the box. They also replace the law of the jungle that characterizes the shantytown architecture with conventions and best practices. In short, frameworks are the software equivalent to prefab houses.

-->

---
<img class="stretch" data-src="assets/belgian-house2.jpg">

"Compromise makes a good umbrella, but a poor roof." 

—James Russell Lowell

<!---

Unfortunately, frameworks also have the same flaws as prefab houses. They function as a 'one size fits all' solution. While this may help you get started in the beginning, they often make it difficult to scale and customize later on.

While I have nothing against frameworks, I would argue that they have little to do with architecture. Architecture is about finding specific solutions to specific problems. To make, spaces livable for the individual users. Framework tend to do the opposite.

-->
---
| Serverless Frontend                 | Clojurescript                       |
|-------------------------------------|-------------------------------------|
| Componentization                    | Component                           |
| Smart Endpoints and Dumb Pipes      | Core.Async                          |
| Design for Failure                  | Component + Core.Async              |
| Evolutionary Design                 | Build Artifact Plain HTML/CSS/JS    |

<!---

misnomer... explain

-->

---
## Conclusion

---
1. Lived Spaces
2. Expression of a Desired Future
3. Assemblage of Building Blocks.

---
<img class="stretch" data-src="assets/unlivable-house.jpg">

"A House Is Not A Home" 

—Burt Bacharach & Hal David

<!---

No one has summarized this clearer than the great philosophers Burt Bacharach and Hal David, when they used the voice of Dionne Warwick to claim that: "A House is Not a Home"

And even though I completely agree with them, I would just like to add one tiny thing...

-->

---
<img class="stretch" data-src="assets/cozy-house.jpg">

"Most Homes Are Also Houses"

—Jan Hein Hoogstad

<!---

Go out and build beautiful buildings.

---
### offcourse.io  
### @yeehaa  
offcourse.github.io/presentation-moonconf/
github.com/yeehaa123/presentation-moonconf/blob/master/slides.md
