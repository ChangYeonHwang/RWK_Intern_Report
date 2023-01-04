Day 5 - JDBC 코딩
---
java jdbc에 를 사용하여 csv file을 db테이블에 insert하고 select하는 프로젝트(maven 사용)를 짜고/수행하고 제출하세요

---

메이븐 기초 배우기
---

#### 📎 링크 : [메이븐 활용법 ](https://www.youtube.com/watch?v=VAp0n9DmeEA&list=PLq8wAnVUcTFWRRi_JWLArMND_PnZM6Yja&index=1)

![Maven Create Project](https://user-images.githubusercontent.com/87057782/210033575-36c3c79d-6208-4ab6-a385-d9dba833399a.png)

![Maven Create Project 2](https://user-images.githubusercontent.com/87057782/210033610-035b94d6-6dae-432b-b7e7-0313dede6c7d.png)

이에 따라 기초적인 메이븐 프로젝트를 만들어보고 pom.xml 파일을 업로드하였다

![mysql jar](https://user-images.githubusercontent.com/87057782/210496621-0d42d11a-5973-4ab8-b1c5-1aae172aeea8.png)

mysql connector를 이용해 eclipse에서 연결을 하였다

Mysql 연결
---

```
# import java.sql.Connection;
# import java.sql.DriverManager;
# import java.sql.SQLException;

# public class connectionTest {
	
#     public static void main(String[] args) {
		
# 		  try {
#			  Class.forName("com.mysql.cj.jdbc.Driver");
			
#			 Connection conn =
#			 DriverManager.getConnection("jdbc:mysql://127.0.0.1:3306/DB이름", "jameshwang", "jameshwang"); 
	
#			 System.out.println("mysql db 연결 성공");
			
#			 conn.close();
#			 System.out.println("mysql 연결 해제");
#		 }
#		 catch(ClassNotFoundException error) {
#			 System.out.println("mysql driver 미설치 또는 드라이버 이름 오류");
#		 }
#		 catch(SQLException error) {
#			 System.out.println("DB 접속 오류");
#		 }
#	 }

# }
```

CSV file 읽기
---

▶️ openCSV를 이용해 CSV 라이브러리에 접근하였다

   사용한 메이븐 dependency는 다음과 같다
   
📎[openCSV 링크](https://mvnrepository.com/artifact/com.opencsv/opencsv)
   
```
# <dependency>
#    <groupId>net.sf.opencsv</groupId>
#    <artifactId>opencsv</artifactId>
#    <version>2.0</version>
# </dependency>
```

▶️ CSV 파일 생성을 위한 객체, csv for RWK intern 만들기

```  
# import java.io.BufferedReader;
# import java.io.File;
# import java.io.FileInputStream;
# import java.io.FileReader;
# import java.io.UnsupportedEncodingException;
# import java.nio.charset.Charset;
# import java.util.ArrayList;
# import java.util.List;
# import java.io.IOException;

# import au.com.bytecode.opencsv.CSVReader;
 
#   public class CSVWrite {
 
#       private String filename = "csv_for_RWK_intern.csv";
 
#         public CSVWrite() {}
 
#     public void writeCsv(List<String[]> data) {
#         try {
#             CSVWriter cw = new CSVWriter(new FileWriter(filename), ',', '"');
#             Iterator<String[]> it = data.iterator();
#             try {
#                 while (it.hasNext()) {
#                     String[] s = (String[]) it.next();
#                     cw.writeNext(s);
#                 }
#             } finally {
#                 cw.close();
#             }
#        } catch (IOException e) {
#             e.printStackTrace();
#         }
#    }
# }
```

▶️ main 함수를 만들고 실행하기 위한 코드

```
# import java.util.ArrayList;
# import java.util.List;
# public class App {
#     public static void main(String[] args) {
 
#         List<String[]> data = new ArrayList<String[]>();
 
#         data.add(new String[] { "day", "5", "jdbc코딩" });
#         data.add(new String[] { "cmd", "maven", "eclipse" });
#         data.add(new String[] { "open", "csv", "load" });
 
#         CSVWrite cw = new CSVWrite();
#         cw.writeCsv(data);
#     }
# }
```

▶️ CSV 파일 읽기

```
# import java.io.BufferedReader;
# import java.io.File;
# import java.io.FileInputStream;
# import java.io.FileReader;
# import java.io.UnsupportedEncodingException;
# import java.nio.charset.Charset;
# import java.util.ArrayList;
# import java.util.List;
# import java.io.IOException;
 
# import au.com.bytecode.opencsv.CSVReader;
 
# public class CSVRead {
 
#     private String filename = "csv_for_RWK_intern.csv";
 
#     public CSVRead() {}
 
#     public List<String []> readCsv() {
 
#         try {
#             CSVReader reader = new CSVReader(new FileReader(filename));
#             String[] s;
#             while ((s = reader.readNext()) != null) {
#                 data.add(s);
#             }
#         } catch (FileNotFoundException e) {
#             e.printStackTrace();
#         } catch (IOException e) {
#             e.printStackTrace();
#         }
 
#         return data;
#     }
# }
```

CSV 파일 Insert to Mysql
---

```
# package net.codejava;
 
# import java.io.*;
# import java.sql.*;
 
# public class SimpleCsv2DbInserter {
 
#     public static void main(String[] args) {
#         String jdbcURL = "jdbc:mysql://localhost:3306/DB이름";
#         String username = "jameshwang";
#         String password = "jameshwang";
 
#         String csvFilePath = "csv_for_RWK_intern.csv";
 
#         int batchSize = 20;
 
#         Connection connection = null;
 
#         try {
 
#             connection = DriverManager.getConnection(jdbcURL, username, password);
#             connection.setAutoCommit(false);
 
#             String sql = "INSERT INTO review (course_name, student_name, timestamp, rating, comment) VALUES (?, ?, ?, ?, ?)";
#             PreparedStatement statement = connection.prepareStatement(sql);
 
#             BufferedReader lineReader = new BufferedReader(new FileReader(csvFilePath));
#             String lineText = null;
 
#             int count = 0;
 
#             lineReader.readLine(); // skip header line
 
#             while ((lineText = lineReader.readLine()) != null) {
#                 String[] data = lineText.split(",");
#                 String courseName = data[0];
#                 String studentName = data[1];
#                 String timestamp = data[2];
#                 String rating = data[3];
#                 String comment = data.length == 5 ? data[4] : "";
 
#                 statement.setString(1, courseName);
#                 statement.setString(2, studentName);
 
#                 Timestamp sqlTimestamp = Timestamp.valueOf(timestamp);
#                 statement.setTimestamp(3, sqlTimestamp);
 
#                 Float fRating = Float.parseFloat(rating);
#                 statement.setFloat(4, fRating);
 
#                 statement.setString(5, comment);
 
#                 statement.addBatch();
 
#                 if (count % batchSize == 0) {
#                     statement.executeBatch();
#                 }
#             }
 
#             lineReader.close();
 
#             // execute the remaining queries
#             statement.executeBatch();
 
#             connection.commit();
#             connection.close();
 
#         } catch (IOException ex) {
#             System.err.println(ex);
#         } catch (SQLException ex) {
#             ex.printStackTrace();
 
#             try {
#                 connection.rollback();
#             } catch (SQLException e) {
#                 e.printStackTrace();
#             }
#         }
 
#     }
# }
```

CSV 파일 Insert to Mysql


## 📎참고 링크 [openCSV](https://hasiki.tistory.com/23), [csv 예제](https://spatiumwdev.tistory.com/36), [csv inseert](https://www.codejava.net/coding/java-code-example-to-insert-data-from-csv-to-database)
