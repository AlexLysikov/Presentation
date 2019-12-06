REST API

Hi everyone!

**SLIDE 1.**

In this video we will understand what kind of beast is such a REST API, why it exists and how to hunt for it.

I will try to be extremely concise and not take much of your time. I apologize in advance for my English: I&#39;m not a magician, but just learning.

So, first of all, I would like to clarify the origin and meaning of the terms that make up this concept.

**SLIDE 2.**

As wikipedia tells us, REST is an abbreviation that stands for &quot;Representational State Transfer&quot; and represents the architectural style of interaction between components of a distributed application on the network. This style is a consistent set of constraints that are considered when designing a distributed system.

Such restrictions were originally published by Roy Fielding in his doctoral dissertation in 2000. Since then, this style has been used to describe the interaction of components in most web applications for which the term &quot;RESTful&quot; is used.

Restful mostly came into popularity due mostly to the reason of supporting of different languages and environments, enables web applications that are built on various programming languages to communicate with each other.

A RESTful web application exposes information about itself in the form of information about its resources. It also enables the client to take actions on those resources, such as create new or change existing resources, such as create a new user or edit a post.

**SLIDE 3.**

As we already know REST stands for REpresentational State Transfer.

It means when a RESTful API is called, the server will transfer to the client a representation of the state of the requested resource.

For example, when a developer calls Instagram API to fetch a specific user (the resource), the API will return the state of that user, including their name, the number of posts that user posted on Instagram so far, how many followers they have, and more.

The representation of the state can be in a JSON format, and probably for most APIs this is indeed the case. It can also be in XML or HTML format.

**SLIDE 4.**

What the server does when you, the client, call one of its APIs depends on 2 things that you need to provide to the server:

An identifier for the resource you are interested in. This is the URL for the resource, also known as the endpoint. In fact, URL stands for Uniform Resource Locator.

The operation you want the server to perform on that resource, in the form of an HTTP method, or verb. The common HTTP methods are GET, POST, PUT, and DELETE.

For example, fetching a specific Twitter user, using Twitter&#39;s RESTful API, will require a URL that identify that user and the HTTP method GET.

**SLIDE 5.**

In total, REST architecture has six limitations, which, in fact, represent the structure of the API of all program constructs that interact with your application.

In order for your APIs to be RESTful, you have to follow a set of constraints when you write them. The REST set of constraints will make your APIs easier to use and also easier to discover, meaning a developer who is just starting to use your APIs will have an easier time learning how to do so.

**SLIDE 5.1.**

First, for &quot;RESTful&quot; applications, a client-server model must be implemented. This means the separation of functionality between the client and server parts of the application, which will certainly affect their performance and scalability. This allows both parts to develop independently of each other and increases portability of the client interface code to other platforms, and allows the server to interact with several clients.

**SLIDE 5.2.**

Secondly, with this architecture there is no client state on the server, that is, in the period between client requests, no information about the client state is stored on the server. All requests from the client should be composed so that the server receives all the necessary information to complete the request and generate a response. The state of the session is saved on the client side, and the request is sent, when the client has &quot;matured&quot;, switch to a new state.

**SLIDE 5.3.**

Thirdly, caching, that is, storing intermediate data in temporary information storages, which allows to further reduce the number of server calls and speed up the application. Caching can be performed both on the client side and in the intermediate nodes of the network. Data the server sends contain information about whether or not the it is cacheable. If the data is cacheable, it might contain some sort of a version number. The version number is what makes caching possible: since the client knows which version of the data it already has (from a previous response), the client can avoid requesting the same data again and again. The client should also know if the current version of the data is expired, in which case the client will know it should send another request to the server to get the most updated data about the state of a resource.

**SLIDE 5.4.**

The fourth requirement is the uniformity of the interface, which manifests itself in the identification of resources by separating requests from representations, manipulating resources through presentations, &quot;self-describing&quot; messages, and hypermedia as a means of changing the state of an application.

The request to the server has to include a resource identifier. The response the server returns include enough information so the client can modify the resource.

Each request to the API contains all the information the server needs to perform the request, and each response the server returns contain all the information the client needs in order to understand the response.

By hypermedia we refer to the hyperlinks, or simply links, that the server can include in the response. The whole sentence means that the server can inform the client , in a response, of the ways to change the state of the web application. If the client asked for a specific user, the server can provide not only the state of that user but also information about how to change the state of the user, for example how to update the user&#39;s name or how to delete the user.

**SLIDE 5.5.**

Another requirement is the stratification of the interaction, the building of layered system. The client sending the requests does not need to contact the server directly; there are intermediate network nodes for this, which allow achieving load balancing and increasing scalability.

Server doesn&#39;t remember if the user of the API already sent a GET request for the same resource in the past, it doesn&#39;t remember which resources the user of the API requested before, and so on.

Each individual request contains all the information the server needs to perform the request and return a response, regardless of other requests made by the same API user.

**SLIDE 5.6.**

And finally, the last requirement, albeit optional, is to provide code on demand, that is, expanding client functionality by downloading and executing code in the form of applets or scripts. This simplifies the work of customers by reducing the number of functions required for preliminary implementation.

The client can request code from the server, and then the response from the server will contain some code, usually in the form of a script, when the response is in HTML format. The client then can execute that code.

All these principles help RESTful applications to be simple, lightweight, and fast.

**SLIDE 6.**

Client in REST —is the person or software who uses the API. It can be a developer, for example you, as a developer, can use Twitter API to read and write data from Twitter, create a new tweet and do more actions in a program that you write. Your program will call Twitter&#39;s API. The client can also be a web browser. When you go to Twitter website, your browser is the client who calls Twitter API and uses the returned data to render information on the screen.

**SLIDE 7.**

The key abstraction of information in REST is a resource. Any information that can be named can be a resource: a document or image, a temporal service, a collection of other resources, a non-virtual object (e.g. a person), and so on. REST uses a resource identifier to identify the particular resource involved in an interaction between components.

A resource can be any object the API can provide information about. In Instagram&#39;s API, for example, a resource can be a user, a photo, a hashtag. Each resource has a unique identifier. The identifier can be a name or a number.

**SLIDE 8.**

The state of resource at any particular timestamp is known as resource representation. A representation consists of data, metadata describing the data and hypermedia links which can help the clients in transition to next desired state.

The data format of a representation is known as a media type. The media type identifies a specification that defines how a representation is to be processed. A truly RESTful API looks like hypertext. Every addressable unit of information carries an address, either explicitly, how link and id attributes, or implicitly, how derived from the media type definition and representation structure.

**SLIDE 9.**

Other important thing associated with REST is resource methods to be used to perform the desired transition. A large number of people wrongly relate resource methods to HTTP GET/PUT/POST/DELETE methods, prefer to compare HTTP with REST. But REST and HTTP are not same.

Ideally, everything that is needed to change the resource state shall be part of API response for that resource – including methods and in what state they will leave the representation.

**SLIDE 10.**

Another thing which will help you while building RESTful APIs is that query based API results should be represented by a list of links with summary information, not by arrays of original resource representations because query is not a substitute for identification of resources.

In simplest words, in the REST architectural style, data and functionality are considered resources and are accessed using Uniform Resource Identifiers (URIs). The resources are acted upon by using a set of simple, well-defined operations. The clients and servers exchange representations of resources by using a standardized interface and protocol – typically HTTP.

Resources are decoupled from their representation so that their content can be accessed in a variety of formats, such as HTML, XML, plain text, PDF, JPEG, JSON, and others. Metadata about the resource is available and used, for example, to control caching, detect transmission errors, negotiate the appropriate representation format, and perform authentication or access control. And most importantly, every interaction with a resource is stateless.

**SLIDE 11.**

An important distinguishing feature of REST API is **HATEOAS** (Hypermedia as the Engine of Application State) is a constraint of the REST application architecture that keeps the RESTful style architecture unique from most other network application architectures. The term &quot;hypermedia&quot; refers to any content that contains links to other forms of media such as images, movies, and text.

REST architectural style lets you use hypermedia links in the response contents so that the client can dynamically navigate to the appropriate resource by traversing the hypermedia links. It is conceptually the same as a web user browsing through web pages by clicking the relevant hyperlinks to achieve a final goal.

**SLIDE 11.1.**

For example, below given JSON response may be from an API like HTTP "GET.

In this example, the response returned by the server contains hypermedia links to employee resources 10/employees, which can be traversed by the client to read employees belonging to the department.

The advantage of the above approach is that hypermedia links returned from the server drive the application&#39;s state and not the other way around.

**SLIDE 12.**

In preparation for the presentation, I used the sources that you can see on the screen. Most of them helped to understand the essence of the concept and the principles of the REST API.

SOURCES USED:

- What is REST — A Simple Explanation for Beginners: [https://medium.com/extend/what-is-rest-a-simple-explanation-for-beginners-part-1-introduction-b4a072f8740f](https://medium.com/extend/what-is-rest-a-simple-explanation-for-beginners-part-1-introduction-b4a072f8740f)
- RESTful API tutorial :[https://restfulapi.net](https://restfulapi.net)
- RESTful Web Services Tutorial with Example: [https://www.guru99.com/restful-web-services.html](https://www.guru99.com/restful-web-services.html)
- Identify examples of REST APIs: [https://openclassrooms.com/en/courses/3432056-build-your-web-projects-with-rest-apis/3496011-identify-examples-of-rest-apis](https://openclassrooms.com/en/courses/3432056-build-your-web-projects-with-rest-apis/3496011-identify-examples-of-rest-apis)
- Basic concepts of a RESTful application: [http://student.webcamp.com.ua/rest\_student/rest101](http://student.webcamp.com.ua/rest_student/rest101)

**SLIDE 13.**

At the end of my speech, I would like to note that building or using a quality REST API is enough just to follow the basic recommendations of the style and then your applications will be simple, easy and fast.

Good luck and all the best.

Buy!