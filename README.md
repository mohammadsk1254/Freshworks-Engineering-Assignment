# Freshworks-Engineering-Assignment

import java.io.*;
import java.lang.String;
import java.util.*;
import org.json.JSONObject; 
public class BR 
{
 static BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
 public void Insert( ) throws IOException
 {
   Scanner in = new Scanner (System.in);
  System.out.println("Enter the Country_Name: ");
 String country_Name=in.next();
 System.out.println("Enter the Country_capital: ");
 String country_capital=in.next();
 System.out.println("Enter the region: ");
 char  region=in.nextInt();
 System.out.println("Enter the language: ");
 char language=in.nextInt();     
  JSONObject obj=new JSONObject(); 
  obj.put("country_name",country_Name);    
  obj.put("country_capital",country_capital);    
  obj.put("region",region);
  obj.put("language",language);
  PrintWriter pw = new PrintWriter(new BufferedWriter(new FileWriter("BR.txt",true)));
  pw.print(obj);
  System.out.println("Details added successfully.");
  pw.close();
 }
public static void main(String args[]) throws IOException
{
  BR in = new BR();
  in.Insert();
}
 
}

Database performance can be improved beyond connection pooling. Replication, load balancing, and in-memory caching can contribute to efficient database performance.

If a web service is designed to make a lot of read and write queries to a database, then you have multiple instances of a Postgres database in place to take care of write queries from clients through a load balancer such as pgpool-II while in-memory caching can be used to optimize read queries.

Despite the pgpool-II ability to function as a loader balancer and connection pooler, pgbouncer is the preferred middleware solution for connection pooling because it is easy to set up, not too difficult to manage, and primarily serves as a connection pooler without any other functions. 
