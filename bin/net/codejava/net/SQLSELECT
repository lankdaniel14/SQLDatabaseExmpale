package net.codejava.net;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;
import java.util.Scanner;

public class SQLSELEC extends Thread {

	public void select() {
		Scanner s = new Scanner(System.in);
		String url = "jdbc:postgresql://localhost:5432/Exercises";
		String username = "postgres";
		String password = "admin";

		try {
			Connection conn = DriverManager.getConnection(url, username, password);
//			System.out.println("Connected");

			String sqlshow = "SELECT * FROM cd.\"Customers\" ";
			Statement statshow = conn.createStatement();
			ResultSet result = statshow.executeQuery(sqlshow);
			while (result.next()) {
				System.out.println("");
				int id = result.getInt("id");
				String firstname = result.getString("first_name");
				String lastname = result.getString("last_name");
				String email = result.getString("email");

				System.out.print(id + " " + firstname + " " + lastname + " " + email + "\n");
				
			}

			conn.close();
		} catch (Exception e) {

			System.out.println(e.getMessage());

		}

	}

}
