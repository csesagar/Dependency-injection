 we can also manually injectdependencyobject i.e., service into client class by implementing the below code:
var services = HttpContext.RequestServices;
var obj = (<Interface_Name>)services.GetService(typeof(<Interface_Name>));


 Write the below code in “Startup” Class under “ConfigureServices” Method:
services.AddSingleton<ICustomerDAL, CustomerXmlDAL>();
D
services.AddScoped<ICustomerDAL, CustomerXmlDAL>();
D
services.AddTransient<ICustomerDAL, CustomerXmlDAL>();

 Write the below code in “Program” class just above the statement =>
var app = builder.Build();
builder.Services.AddSingleton<ICustomerDAL, CustomerXmlDAL>();
D
builder.Services.AddScoped<ICustomerDAL, CustomerXmlDAL>();
D
builder.Services.AddTransient<ICustomerDAL, CustomerXmlDAL>();
