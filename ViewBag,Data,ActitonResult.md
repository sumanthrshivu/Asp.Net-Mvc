## Routing in ASP.NET
 - Routing is a process through which the application matches any incoming URL path and execute the corresponding action methods ASP.net MVC. 
 - Routing is a pattern matching system that is responsible for mapping incoming browser requests to specified MVC controller actions.
 - routing engine uses the route table for matching the incoming request.
 - Route config file is used for adding route rules.
 - We invoke a RegisterRoutes methods in the App_Start() method.
 - Routing can also be used to setup the startup page of the application.
## Default  routing  
      When we create a new ASP.NET MVC application,by default the application is already configured to use ASP.NET Routing.
```C#
public class MvcApplication : System.Web.HttpApplication
    {
        public static void RegisterRoutes(RouteCollection routes)
        {
            routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

            routes.MapRoute(
                "Default",                                              // Route name
                "{controller}/{action}/{id}",                           // URL with parameters
                new { controller = "Home", action = "Index", id = "" }  // Parameter defaults
            );
        }

        protected void Application_Start()
        {
            RegisterRoutes(RouteTable.Routes);
        }
    }
```
# Asp.Net MVC - ViewBag
The ViewBag in ASP.NET MVC is used to transfer temporary data (which is not included in the model) from the controller to the view.<br />

![viewbag](https://user-images.githubusercontent.com/74582120/132456022-adc74cf2-6d9d-422e-839d-6eea07893d89.png)
ViewBag Data Transfer<br/><br />
In the above figure, it attaches Name property to ViewBag with the dot notation and assigns a string value "Bill" to it in the controller. This can be accessed in the view like @ViewBag.Name.<br/><br>
**Example : StudentController.cs**
```C#
namespace ViewBag.Controllers
{
    public class StudentController : Controller
    {
        List<Student> studentList = new List<Student>() { 
                    new Student(){ StudentID=1, StudentName="Steve", Age = 21 },
                    new Student(){ StudentID=2, StudentName="Bill", Age = 25 },
                    new Student(){ StudentID=3, StudentName="Ram", Age = 20 },
                };
        // GET: Student
       public ViewResult std()
        {
            ViewBag.TotalStudents = studentList.Count();
            return View();
        }
    }
}
```
**std.cshtml**
```C#
<div>
  <label>Total Students:</label>  @ViewBag.TotalStudents
</div>
 ```
---
# Asp.Net MVC - ViewData
* In ASP.NET MVC, ViewData is similar to ViewBag, which transfers data from Controller to View.
* ViewData is of Dictionary type(it contains key-value pairs where each key must be a string), whereas ViewBag is of dynamic type. 
* In ViewData We can only transfer data from Controller to view but if we wish to pass data back again to controller then it is not possible. So it is valid only for the current request.<br>
![viewdata](https://user-images.githubusercontent.com/74582120/132458567-943e845b-afbb-4321-ab41-367519272790.png)
<br/><br>
**Example : StudentController.cs**
```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Mvc;

namespace ViewData.Controllers
{
    public class StudentController : Controller
    {
        public ViewResult std()
        {
            ViewData["Student"] = "Sumanth";
            return View();
        }
    }
}
```
**std.cshtml**
```C#
   <div>
        <h2>UsingViewData</h2> @ViewData["Student"]
  </div>
 ```
---
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






