# WebAPI_Swagger

Swagger is the world’s largest framework of API developer tools for the OpenAPI Specification(OAS), enabling development across the entire API lifecycle, from design and documentation, to test and deployment.

OpenAPI is the specification, and Swagger is a set of tools that facilitate the implementation.

##### 1. Add the Swagger tool for ASP. NET Core, Swashbuckle

`dotnet add package Swashbuckle.AspNetCore`

##### 2. Add a using statement at the top of the `Startup.cs`

`using Swashbuckle.AspNetCore.Swagger;`

##### 3. Add the swagger generator to the Services. Then configure the WebApi middleware to use the Swagger and finally activate the Swagger UI which will provide the interactive browser based API explorer which acts as a test client as well.

```cs
public void ConfigureServices(IServiceCollection services)
{
}

```
