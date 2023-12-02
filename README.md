# Hive-Sqoop

### Task 1: Sqoop
1. **Import a table from MySQL to HDFS:**
   - Start MySQL: `systemctl start mysqld`
   - Log in to MySQL: `MySQL -uroot`
   - Check databases: `show databases;`
   - Choose a database, e.g., Hive, and use a table (e.g., ROLES): `use hive;` `select * from ROLES;`
   - Use Hadoop command to create a subdirectory: `hadoop fs -mkdir /user/sandeep`

2. **Export data from HDFS to MySQL:**
   - Create a table in MySQL, e.g., TBLS_2
   - Export data using Sqoop: 
     ```bash
     sqoop export --connect jdbc:mysql://sandbox-hdp.hortonworks.com/hive --username root --password hortonworks1 --table TBLS_2 --export-dir /user/Sandeep/testing --fields-terminated-by '|'
     ```

### Task 2: Hive
1. **Upload Book.xml to HDFS and create a table in Hive:**
   - Upload Book.xml to HDFS: `hadoop fs -put Book.xml /user/sandeep/`
   - Start Hive and create a table: 
     ```sql
     create table book (
       -- Define columns based on Book.xml structure
     )
     row format delimited
     fields terminated by '|'
     stored as textfile
     location '/user/sandeep/';
     ```

2. **Download and set up Apache Hive:**
   - Download and extract: `tar zxvf apache-hive-3.1.2-bin.tar.gz`
   - Update bashrc:
     ```bash
     export HIVE_HOME=/usr/local/hive
     export PATH=$PATH:$HIVE_HOME/bin
     ```

3. **Update hive-env.sh file:**
   - Edit hive-env.sh file with necessary configurations.

4. **Install Derby in Hive:**
   - Install Derby in Hive.

5. **Set the path of Derby in bashrc:**
   ```bash
   export DERBY_HOME=/usr/local/derby
   export PATH=$PATH:$DERBY_HOME/bin
   ```

6. **Create the book table in Hive:**
   - Execute the Hive DDL commands to create the book table.

