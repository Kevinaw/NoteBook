# Application Licensing in .NET Framework
1.  A good start: [Applications Licensing using the .NET Framework](https://www.developer.com/net/csharp/article.php/3074001/Applications-Licensing-using-the-NET-Framework.htm)
2.  MSDN tutorial: [How to: License Components and Controls](https://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57?f=255&MSPPError=-2147217396)
3.  Licensing strategies: [Top Ten Licensing Types](https://www.itassetmanagement.net/2014/12/08/top-ten-licensing-types/)
4.  [How to generate and validate a software license key](https://stackoverflow.com/questions/599837/how-to-generate-and-validate-a-software-license-key)
5.  Code samples:
    * [A Ready To Use Software Licensing Solution in C#](https://www.codeproject.com/Articles/996001/A-Ready-To-Use-Software-Licensing-Solution-in-Csha)
    * [varification by computer id](https://www.codeproject.com/Articles/15496/Application-Trial-Maker-2)
    

# Application Update Settings
1. Clickonce strategies. [here](https://docs.microsoft.com/en-us/visualstudio/deployment/choosing-a-clickonce-update-strategy?view=vs-2017).

# Logging in C# and .net
1. [Logging in .NET: TraceSource and log4net](https://logmatic.io/blog/logging-in-net-the-power-of-c-logs/)
2. System.Dianostic tutorial. [here](http://www.thejoyofcode.com/from_zero_to_logging_with_system_diagnostics_in_15_minutes.aspx)

 
# Data migration, entity framework

# Testing in .net framework


# Entity Fromework Code First with SQLite Database.
1. [Source and Demo Code](https://github.com/msallin/SQLiteCodeFirst)
2. Create/open database
```c#
   string filename = "";
   OpenFileDialog dlg = new OpenFileDialog();
   if(dlg.ShowDialog() == DialogResult.OK)
   {
       filename = dlg.FileName;

       var conn = DbProviderFactories.GetFactory("System.Data.SQLite").CreateConnection();
       conn.ConnectionString = "data source=" + filename + ";foreign keys=true";

       using(var context = new FootballDbContext(conn, true))
       {
           if (context.Database.Exists() == true)
               MessageBox.Show("opening.");
       }
   }
```
Remember: Change provider name "System.Data.SQLite.EF6" to "System.Data.SQLite" in App.config.
