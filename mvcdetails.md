  # Asp.Net MVC Request Life Cycle
![MVC-request-life-cycle-pipeline-dotnet-helpers](https://user-images.githubusercontent.com/74582120/133243492-cd014ee6-c5ba-4f58-bc14-2b622b81d6a6.jpg)


# Asp.Net MVC - ViewBag
The ViewBag in ASP.NET MVC is used to transfer temporary data (which is not included in the model) from the controller to the view.<br />

![viewbag](https://user-images.githubusercontent.com/74582120/132456022-adc74cf2-6d9d-422e-839d-6eea07893d89.png)
ViewBag Data Transfer<br/><br />
In the above figure, it attaches Name property to ViewBag with the dot notation and assigns a string value "Bill" to it in the controller. This can be accessed in the view like @ViewBag.Name.<br/><br>

# Asp.Net MVC - ViewData
* In ASP.NET MVC, ViewData is similar to ViewBag, which transfers data from Controller to View.
* ViewData is of Dictionary type(it contains key-value pairs where each key must be a string), whereas ViewBag is of dynamic type. 
* In ViewData We can only transfer data from Controller to view but if we wish to pass data back again to controller then it is not possible. So it is valid only for the current request.<br>
![viewdata](https://user-images.githubusercontent.com/74582120/132458567-943e845b-afbb-4321-ab41-367519272790.png)
<br/><br>
# ActionResult
* The ActionResult class is a base class of all the below result classes, so it can be the return type of action method that returns any result listed below. However, we can specify the appropriate result class as a return type of action method.
* MVC framework includes various Result classes, which can be returned from an action method.
* The result classes represent different types of responses, such as HTML, file, string, JSON, javascript, etc. 
* The following table lists all the result classes available in ASP.NET MVC.

| Result Class                                        | Description                                           | Base Controller Method |
|-----------------------------------------------------|-------------------------------------------------------|------------------------|
| ViewResult                                          | Represents HTML and markup.                           | View()                 |
| EmptyResult                                         | Represents No response.                               |                        |
| ContentResult                                       | Represents string literal.                            | Content()              |
| FileContentResult/ FilePathResult/ FileStreamResult | Represents the content of a file.                     | File()                 |
| JavaScriptResult                                    | Represent a JavaScript script.                        | JavaScript()           |
| JsonResult                                          | Represent JSON that can be used in AJAX.              | Json()                 |
| RedirectResult                                      | Represents a redirection to a new URL.                | Redirect()             |
| RedirectToRouteResult                               | Represent another action of same or other controller. | RedirectToRoute()      |
| PartialViewResult                                   | Returns HTML from Partial view.                       | PartialView()          |
| HttpUnauthorizedResult                              | Returns HTTP 403 status.                              |                        |

# Asp.Net CRUD Operations
* how to insert update delete and display the data using sql in MVC.
# Filters
An filter is an attribute that you can apply to a controller action -- or an entire controller -- that modifies the way in which the action is executed. 

## Builtin filters
* OutputCache – This action filter caches the output of a controller action for a specified amount of time.
* HandleError – This action filter handles errors raised when a controller action executes.
* Authorize – This action filter enables you to restrict access to a particular user or role.
    16-Oct-2008.
## Custmon filters
* Action Filter: It is performing before or after action method.
* Result Filter: It is performing before or after the action result.
* Exception Filter: It is executed if there is some exception thrown by application when performing action process. It is used to show the error page or for logging error details.
