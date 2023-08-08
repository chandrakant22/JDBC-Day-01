# JDBC-Day-01


import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;




public class Test {

	public static void main(String[] args) throws ClassNotFoundException, SQLException {

		//step 1
		Class.forName("com.mysql.jdbc.Driver");
        System.out.println("Step 1");
        //step 2
        Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/batch2023","root","abc123");
        System.out.println("Step 2");
        
        //step 3
        Statement st=con.createStatement();
        System.out.println("Step 3");
        
        //step4
        int a=st.executeUpdate("insert into student_tbl values(222,'geeta','pune','geeta@gmail.com')");// insert update delete 
        System.out.println("Step 4");
        if(a>0)
        {
        	System.out.println("Data Inserted");
        }
        else
        {
        	System.out.println("Data Not Inserted");
        }
        
        //step 5
        con.close();
        System.out.println("Step 5");
        
	}

}
