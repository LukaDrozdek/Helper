Paketi za skinut:
	Microsoft.EntityFrameworkCore 
	Microsoft.EntityFrameworkCore.Tools	
	Microsoft.EntityFrameworkCore.SqlServer
	
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Data
ApplicationDbContext

	public class ApplicationDbContext : DbContext
    	{
        	public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options)
        	{

        	}
    	}

	public DbSet<Employees> Employees { get; set; }
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Program.cs

	// Add services to the container.
	builder.Services.AddControllersWithViews();
	builder.Services.AddDbContext<ApplicationDbContext>(options => options.UseSqlServer(
    	builder.Configuration.GetConnectionString("DefaultConnection")
    	));



--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
.json ConnectionStrings

"ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;Database=PCWebStore;Trusted_Connection=True;MultipleActiveResultSets=True"
  },
  "Logging": {
