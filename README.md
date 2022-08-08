Prerequisites:
1. Liquibase Installed
   ![Liquibase Installed](https://user-images.githubusercontent.com/99462555/183362506-f18867fc-46db-4c96-816b-19b70e5c2723.png)

3. Created a New Liquibase.properties file or using the existing Liquibase.properties file included in the installation package.
   ![Liquibase Properties](https://user-images.githubusercontent.com/99462555/183363154-bfcc3aad-27ae-4cbc-b2f4-4d78c17d2bcd.png)

5. For More info about Specifying Properties - https://docs.liquibase.com/concepts/connections/creating-config-properties.html
6. Download JDBC Driver and Install it.
   ![JDBC Driver](https://user-images.githubusercontent.com/99462555/183363622-7c407929-191f-4ccd-a391-1b91ca9f49b0.png)

8. Place the JDBC .jar file in the "liquibase/lib" directory.
   ![JDBC Driver in lib directory](https://user-images.githubusercontent.com/99462555/183364047-91287b74-3a71-401c-9b35-3b76e880e03f.png)

10. Microsoft SQL Server Management Studio Installed.
    ![MS SQL Studio](https://user-images.githubusercontent.com/99462555/183364765-fbd89634-4754-416e-a281-6af1fec23248.png)

    
Steps:
1. Declare Environmental Variables for Liquibase and Classpath variable for JDBC Driver.
2. Check Liquibase is installed in your local or not, open POWERSHELL and Type liquibase --version, click enter to see the liquibase version.
3. Generate Changelog file - we mention our scripts in xml, Json, Yaml, Formatted SQL formats to update or rollback the DB changes.
4. "liquibase --changelog-file=mychangelog.oracle.sql generate-changelog" - using this command we can generate Changelogfile.
5. https://docs.liquibase.com/concepts/connections/creating-config-properties.html - by using the mentioned parameters in the command prompt or terminal we can specify    connection to targeted database 
   using liquibase.
6. Example for Sql Database:
   liquibase --driver=com.microsoft.sqlserver.jdbc.SQLServerDriver 
   --url=jdbc:sqlserver://jdbc:sqlserver://volaris-innovlabs-sqlserver.cloj22qg1okc.us-west-2.rds.amazonaws.com:1433;database=Liquibase;encrypt=true;trustServerCertificate=true;
   --ChangeLogFile=databasechangelog.sql
   --classpath=C:/Program Files/liquibase/lib/sqljdbc_10.2/enu
   --username=user
   --password=1234
   update
 7. by executing the above parameters, we can see 2 tables were created in the Dev database, 
    a. databasechangelog Table
    b. databasechangeloglock Table
 8. We can track the db changes using the above mentioned tables.
 9. https://docs.liquibase.com/commands/home.html - "Liquibase Commands". We can use more commands based on the requirement.

Points to Remembers:

1. "Liquibase.Properties" - in this file we need to mention the parameters to get connect to the target Database.
2. "JDBC Driver" - used to establish the connection between the targeted Databse and Liquibase from the command prompt or any terminal.
3. "Databasechangelogfile" - we should mention in any 4 formats (SQL, JSON, YAML, XML) to update or rollback the target database.

For any Further info Visit:
https://forum.liquibase.org/ - using this website, we can clear our doubts by contacting the liquibase Supporters and also we can post our doubts here to get cleared.
