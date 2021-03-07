# sql_connection
Connect to SGBD using java , then throw some plsql querys 

1) __Create a Connection :__ 
```java
package java;
import java.sql.*;
public class connection {

	public static void main(String args[]){  
		try{  
			
		Class.forName("com.mysql.jdbc.Driver");
		Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/blog","phpmyadmin","123");  
		Statement stmt=con.createStatement();  
		
		//---------create a result set to include the statments ------
		ResultSet rs=stmt.executeQuery("select * from user");  
		
		//------ read the result in rs then print the next value in the data_base -----
		while(rs.next())  
			System.out.println(rs.getInt(1)+"  "+rs.getString(2)+"  "+rs.getString(3));  
		con.close();  
		
		
		
		
		}catch(Exception e){ System.out.println(e);}  
	
	}  
	
}
```
