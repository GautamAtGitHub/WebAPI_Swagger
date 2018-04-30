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
            services.AddMvc();
            services.AddSwaggerGen(options =>
            {
                options.SwaggerDoc("v1", new Info { Title = "Test API", Version = "v1" });
            });
        }

        // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
        public void Configure(IApplicationBuilder app, IHostingEnvironment env)
        {
            if (env.IsDevelopment())
            {
                app.UseDeveloperExceptionPage();
            }

            // Enable middleware to serve generated Swagger as a JSON endpoint.
            app.UseSwagger();
            // Add swagger UI
            app.UseSwaggerUI(options => {
                options.SwaggerEndpoint("/swagger/v1/swagger.json", "Test API V1");
            });
            app.UseMvc();
        }
  
```
