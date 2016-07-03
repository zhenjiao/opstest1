# Support for REST API 

> [!NOTE]
> Below contents need to be updated, NEW syntax for REST API can be found in [DocFX](http://dotnet.github.io/docfx/tutorial/intro_rest_api_documentation.html), we will move that section to OPS docs soon.

[Swagger](https://github.com/swagger-api/swagger-core/wiki) is a specification and complete framework implementation for describing, producing, consuming, and visualizing RESTful web services.

Support for Swagger 2.0 is integrated with OP. 

# Syntax

If you are using OA, you used to use the following syntax to invoke Swagger.
    ```RESTAPI_Swagger
    [!INCLUDE [users_swagger2](./users_swagger.json)]  
    ```

In Open Publishing, you should be using the following instead:

The markdown syntax is linke following

    ```RESTAPIdocs
    {
        "api":  "OPSSwagger",
        "operation":    "get me"    
        } 
    }
    ```

And you would also need to put the reference json file at the bottom of the markdown file with the following syntax
    
    [!CODE-RESTAPI_Swagger [users_swagger](./users_swagger.json)]
    
 
 Example:
 
    ```RESTAPIdocs
    {
        "api":  "MeOps",
        "operation":    "get me"
    }
    ```
	   
	[!CODE-RESTAPI_Swagger [me_ops_swagger2](./_data/swagger_test.json)]
     
 Here's how it renders
 
```RESTAPIdocs
{
    "api":  "MeOps",
    "operation":    "get me"
}
```
[!CODE-RESTAPI_Swagger [me_ops_swagger2](./_data/swagger_test.json)]

