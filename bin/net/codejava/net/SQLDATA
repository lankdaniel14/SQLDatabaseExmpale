package net.codejava.net;

import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Scanner;
import java.sql.Connection;

public class SQLDATA {

	public static void main(String[] args) throws Exception {
		Scanner s = new Scanner(System.in);
		String url = "jdbc:postgresql://localhost:5432/Exercises";
		String username = "postgres";
		String password = "admin";

		boolean isvaild = false;
		while (!isvaild) {
			System.out.println("");
			System.out.println("1 - New Contact");
			System.out.println("2 - Show Contacts");
			System.out.println("3 - Delete all Data");
			System.out.println("0 - Exit");
			int selection = s.nextInt();
			switch (selection) {
			case 1:
				try {

					Scanner s1 = new Scanner(System.in);

					Connection connection = DriverManager.getConnection(url, username, password);
//					System.out.println("Connected");

					Thread.sleep(1000);
					System.out.println("");
					System.out.println("Enter Contact first name: ");
					String tempfirst = s1.next();
					System.out.println("Enter Contact last name: ");
					String templast = s1.next();
					System.out.println("Enter Contact email: ");
					String tempemail = s1.next();

					Thread.sleep(1000);

					String sql = "Insert into cd.\"Customers\" (first_name, last_name, email)" + "values('" + tempfirst
							+ "'" + ",'" + templast + "'" + ",'" + tempemail + "')";

					Statement stat = connection.createStatement();
					int rows = stat.executeUpdate(sql);

					if (rows > 0) {
						System.out.println("Contact Created");
						System.out.println("");
					}
//					isvaild = true;
					connection.close();
				} catch (SQLException e) {

					System.out.println(e.getMessage());
					isvaild = true;
				}

				break;

			case 2:
				SQLSELEC sql = new SQLSELEC();
				sql.select();
//				isvaild = true;
				break;

			case 3:

				Connection con = DriverManager.getConnection(url, username, password);
				String sqldelete = "delete FROM cd.\"Customers\" ";
				Statement statdelete = con.createStatement();
				int rows = statdelete.executeUpdate(sqldelete);
				if (rows == 0) {
					System.out.println("Completed");
				}
				con.close();
//				isvaild = true;
				break;

			case 0:
				System.out.println("Connection terminted");
				isvaild = true;
				break;

			}
		}
	}
}
