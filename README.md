Download Link: https://assignmentchef.com/product/solved-itse2309-database-programming-oracle-lab-1-the-oracle-data-dictionary
<br>
The Oracle data dictionary is a comprehensive set of tables and views owned by the DBA user <strong>SYS</strong> and <strong>SYSTEM</strong>, which is created when Oracle is initially installed. It is the central source of information for the Oracle RDBMS itself and for all users of Oracle. The tables are automatically maintained by Oracle. The data dictionary contains:




<ul>

 <li>The definitions of all schema objects in the database (tables, views, indexes, clusters, synonyms, sequences, procedures, functions, packages, triggers, and so on)</li>

 <li>How much space has been allocated for, and is currently used by, the schema objects</li>

 <li>Default values for columns</li>

 <li>Integrity constraint information</li>

 <li>The names of Oracle users</li>

 <li>Privileges and roles each user has been granted</li>

 <li>Auditing information, such as who has accessed or updated various schema objects</li>

 <li>Other general database information</li>

</ul>




The data dictionary is structured in tables and views, just like other database data. All the data dictionary tables and views for a given database are stored in that database’s SYSTEM tablespace.




Not only is the data dictionary central to every Oracle database, it is an important tool for all users, from end users to application designers and database administrators.




The data dictionary has three primary uses:




<ul>

 <li>Oracle accesses the data dictionary to find information about users, schema objects, and storage structures.</li>

 <li>Oracle modifies the data dictionary every time that a data definition language (DDL) statement is issued.</li>

 <li>Any Oracle user can use the data dictionary as a read-only reference for information about the database.</li>

</ul>




With some exceptions, the names of the objects in the data dictionary begin with one of three prefixes: “USER”, “ALL”, or “DBA”.  Records in the “USER” views usually record information about objects owned by the account performing the query.




In this lab, you will use SQL statements to access the data dictionary. The data dictionary is read-only, you can issue only use SELECT statements against its tables and views.




Issue the following SQL statements to learn more about the data dictionary.  We will be querying the data dictionary throughout the semester.  Copy each SQL statement and the results of the statement and past it in a file (<strong>one file per SQL statement</strong>).  Create a folder named, <strong>Fullname_Lab1</strong>.  Copy your files to the folder.  Zip the folder and upload it to Blackboard.




<ol>

 <li>SQL&gt; describe dictionary</li>

</ol>




<ol start="2">

 <li>SQL&gt; select * from dictionary; — <strong>(Do not copy output to a file)</strong></li>

</ol>




<ol start="3">

 <li>SQL&gt; select Table_Name, Comments from dictionary where Table_Name like ‘DBA_%’;   — <strong>(Do not copy output to a file)</strong></li>

</ol>




<ol start="4">

 <li>SQL&gt; select Table_Name, Comments from dictionary where Table_Name like ‘USER_%’;  — <strong>(Do not copy output to a file)</strong></li>

</ol>




<ol start="5">

 <li>SQL&gt; describe user_tables;</li>

</ol>




<ol start="6">

 <li>SQL&gt; select Table_Name from user_tables;</li>

</ol>




<ol start="7">

 <li>SQL&gt; select Object_Name from user_objects where object_type = ‘TABLE’;</li>

</ol>




<ol start="8">

 <li>SQL&gt; select Object_Name, object_type from user_objects;</li>

</ol>

— <strong>(Do not copy output to a file)</strong>




<ol start="9">

 <li>SQL&gt; select Table_Name, Column_Name, Comments from dict_columns                where table_name  Like ‘USER_%’;  ;  — <strong>(Do not copy output to a file)</strong></li>

</ol>




<ol start="10">

 <li>SQL&gt; select Table_Name, Column_Name, Comments from dict_columns                 where Column_Name = “BLOCK” and Table_Name Like ‘USER_%’;</li>

</ol>




<ol start="11">

 <li>SQL&gt; describe v$version;</li>

</ol>




<ol start="12">

 <li>SQL&gt; select * from v$version;</li>

</ol>