# Asp.Net WebApi
* Api stands for Application Programing Interface
* ASP.NET Web API is an extensible framework for building HTTP based services that can be accessed in different applications on different platforms such as web, windows, mobile etc.
* It works more or less the same way as ASP.NET MVC web application except that it sends data as a response instead of html view.
* It Supports only HTTP protocol.
* It Maps http verbs to methods
* Web API can be configured using HttpConfiguration class but not in web.config.
# App_Start Folder<br>
![Web-API-Config-File-768x376](https://user-images.githubusercontent.com/74582120/133383391-3bc002ca-dcd4-499e-b307-a78027357e47.png)<br>
We can see a default route is configured within the Register() method for our Web API project. The Web API routes are different from the MVC routes. We can find the MVC routes in RouteConfig.cs file which is present in the App_Start folder.

The default route in Web API starts with the word API followed by a / and then the name of the controller and then another / and an optional id parameter as shown below.

“api/{controller}/{id}”


**In a database table row, we can perform the following 4 actions**<br/>
![CRUD-Operations](https://user-images.githubusercontent.com/74582120/133376938-4fd0f506-f20f-4bd9-9620-f5e67b45b95e.png)<br>
**From the ASP.NET Web API point of view, these 4 actions correspond to GET, POST, PUT and DELETE verb as shown below**
![Http-VERB-For-CRUD](https://user-images.githubusercontent.com/74582120/133377013-dfa7104f-9009-471f-a0db-791030fc7096.png)<br>

## Concepts Related to HTTP request and response.
**Resuest Verbs**
* The HTTP verbs such as GET, POST, PUT and DELETE describe what should be done with the Web API resource. For example, if we need to read, create, update or delete an entity? The HTTP Verbs GET, PUT, POST and DELETE are the most commonly used verbs in real-time applications.<br>
**Request Header:**
* When a client sends the request to the server, the request contains a header and a body. The header of the request contains some additional information such as what type of response the client required. For example, the client wants the response to be in XML or JSON format.<br>
**Request Body:**
* The Request Body contains the data that you want to send to the server. For example, a POST request contains the data in the Request Body for the new item that you want to create. The data may be in the form XML or JSON.<br>
**Response Body:**
* The Response Body contains the data that is sent as a response from the server. For example, if you request a specific employee, then the response body includes the employee details either in the form of XML or JSON.<br>
**Response Status codes:**
* The Response Status Codes are the HTTP status codes that will specify the status of the request. 
