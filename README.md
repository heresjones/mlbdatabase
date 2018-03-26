## A Non-Relational Redesign for the Major League Baseball Database Project proposal by Christopher Jones, Eastern CT State University

### Abstract
   In 2015, 73.8 million Major League Baseball tickets were sold[1]. 9% of adults in the United States picked Baseball as their favorite sport, and in 2016, MLB pulled in approximately $10B in revenue [2]. Baseball is a robust statistics-based game[3]. Team managers, fans, and league administration tap these statistics to make decisions and predictions regarding baseball[3]. Sports and academic researchers use this database to understand the nuances of the game.

   The objective of this proposal is to scrutinize the feasibility of a non-relational database model for storing baseball statistics using performance benchmarks as well as an examination of how a non-relational database could be applied. With a new database model, baseball data could be better optimized, organized in a more consistent fashion, and accessed in a more flexible manner. Lessons from this inquiry may also provide value to other sports information management systems.

### 1.	Background and Significance
   ## Background:
   
   The Major League Baseball database was developed originally in the middle of the 20th century by statistician Pete Palmer, digitized in the 1970’s[4]. The information was made available on the internet by Sean Lahman and then moved into a relational database model in the 1990’s with work done by Keith Woolner [4]. 

   The database was created and made available by Sean Lahman for the public to track player information and game outcomes[4]. The database is the effort of several individual contributors from non-technical backgrounds. This means that the database is easy to read by humans, as a set of tables of string values and numbers. But, there has been little investigation done into the viability of the database schema from a computer science standpoint. 

   ## Significance:
   
   Relational databases are designed to protect the end-users from having to sift through the structure of how the information is organized [5]. Indeed, this current database design requires users to sift through the structure of how the data is organized, counter to the philosophy of good relational data principles. 

   Relational database design also requires a user to understand their data in an in-depth manner[6]. But, with focusing on human readability, several common database development fundamentals are neglected or outright ignored. There are dynamic values, such as batting average, being granted their own columns. There are other values, such as age at season start, which are stored. These values could be generated in a software layer on top of the database. In modern framework design, they are.
The goal of a normalized relational database is to limit the amount of redundant data that exists in the tables[7]. In the baseball database, when a player hasn’t achieved a certain stat (such as hit that rewards them with third base) then the column remains as a blank or a zero. These are ad-hoc solutions to sidestep dealing with NULL datatypes. In reality, few players achieve every possible feat, so there are numerous instances of this redundant null data throughout the database. This is where a non-relational implementation could be advantageous.

   Because normalization may not be able to remove all null values without making the database schema harder to read, non-relational solutions such as MongoDB may be more appropriate in representing unstructured baseball data. While previously requiring larger computation power, due to the nature of servers being rented rather than owned, non-relational data manipulation is widely available to any researcher with an internet connection[8]. Using NoSQL is simple, since it uses a key-value store, and there is wide support for database software applications that utilize it. 

   As the speed of computation increases, and web-friendly datatypes such as JSON are surging in use, non-relational databases are being used more frequently. This research aims to prove that an update to the MLB database is a sound idea by studying the speed of querying and the nature of how a non-relational database model can help the culture of baseball, overall. If this investigation shows that a non-relational model matches or exceeds the current relational model in performance and that a non-relational model would work well in the baseball developer community, it is then entirely appropriate that the MLB take advantage of this database revolution.

### 2.	Methodology
   The outcomes of this research will be presented in two segments. The first segment will be the conclusions from the raw tests of querying the data. The second segment will be a discussion on the logistical realities of using non-relational databases vs relational databases in the industry of baseball. 

   Software and Hardware Requirements: The experimentation will be conducted on a single server using both Oracle SQL and MongoDB NoSQL database software. The server shall have  at least 8GB of RAM, and the main testing computer shall have at least 8GB of RAM. The current database schema and data stores are available to the public and located at Sean Lehman’s website or the MLB website.

   ## Process:
   
   The data will be brought into the Oracle SQL database instance. Then, a copy of the database will be created with a conversion that will take place converting the data into JSON formats required for NoSQL. There are standardized tools created by MongoDB for migrating databases from relational to non-relational formats. Once migrated, some code in the NoSQL test code will be written to take over the production of several of the dynamic database values (such as RBI’s), and those values will be removed from the database.  

   The code used to access the servers will be Java running inside of the IntelliJ IDE by Jetbrains. This is determined to be appropriate because both Oracle SQL and MongoDB offer Java libraries for accessing their database software. Tests will be run through console statements, and results will be stored in text files.

   Testing: A typical score card on baseball-reference.com will be used as a template for testing results to be returned. Test result times will be organized adjacent to the stat they retrieved, so the performances can be compared side by side.
 - 	Load Testing: This will include the execution of queries to gather data on players and games. Typical queries that are used to read player stats will be tested.
 - 	Endurance Testing: For endurance testing, rows will be returned on timed intervals and queries will continue to execute over a longer period of time. The purpose of this testing is to observe and compare any weaknesses in the database systems caches or otherwise any other concurrency bottlenecks. 
 - Spike Testing: Similar to endurance testing, but at predetermined intervals large volumes of data will suddenly be required. These spikes will help understand how the database software handles changes in load.
 - Stress Testing: In a stress test, data returned will become progressively larger by adding the number of rows returned with each test. 


Timeline: 

Week 1 (March 26): Acquire necessary software and hardware, install the necessary tools, configure Oracle SQL server and MongoDB server. 

Week 2 (April 2): Begin migration of the relational data into the non-relational database.

Week 3 (April 9): Test the connections of the code libraries. Eliminate the dynamic relational values from the non-relational database.

Week 4 (April 16): Run the performance tests.

Week 5 (April 23): Study the viability and usability of NoSQL databases in context of the sports industry.

Week 6 (April 30): Publish and present findings of research.

### 3.	Statement of Qualifications
   I am currently a senior majoring in Computer Science with a mathematics minor at Eastern Connecticut State University (ECSU). I have previous experience working on large relational databases for Destwin Energy Systems LLC. This work also included clustered servers inside of a Hadoop system containing unstructured non-relational data. Working with building websites and API’s using Hibernate and Jax-RS, and taking advanced database courses at ECSU, I am keenly familiar with working with large datasets. 

### 4.	Expected Outcomes
   The outcome of this inquiry could yield a baseball database that may offer significant improvements not just in performance, but in usability in a wide variety of applications. I expect to find the differences in performance between the relational and non-relational databases to be trivial. A nominal performance by tests of the non-relational model will demonstrate viability. Hypothetically, this new model could be patented and released to the public as an API or a marketable product for software developers. By having a new model for baseball data, statisticians, baseball fans, and researchers could have another computational tool in appreciating America’s pastime.













### Bibliography
[1]	M. Brown, “MLB Sees Nearly 73.8 Million In Attendance For 2015, Seventh-Highest All-Time,” Forbes. [Online]. Available: https://www.forbes.com/sites/maurybrown/2015/10/06/mlb-sees-nearly-73-8-million-in-attendance-for-2015-seventh-highest-all-time/. [Accessed: 02-Mar-2018].

[2]	“Baseball no longer a supergiant but it is still the most American of sports,” The Guardian, 23-Oct-2017.

[3]	J. Albert, “A Baseball Statistics Course,” J. Stat. Educ., vol. 10, no. 2, p. null, Jan. 2002.

[4]	S. Lahman, “Sean Lahman’s Baseball Database Documentation.” [Online]. Available: http://seanlahman.com/files/database/readme2016.txt. [Accessed: 28-Feb-2018].

[5]	E. F. Codd, “A Relational Model of Data for Large Shared Data Banks,” IBM Res. Lab., vol. 13, no. 6, pp. 377–387, Jun. 1970.

[6]	D. Bartholomew, “SQL vs. NoSQL,” Linux J, vol. 2010, no. 195, Jul. 2010.

[7]	A. H. Bahmani, S. K. Shekofteh, M. Naghibzadeh, and H. Deldari, “Parallel algorithms for automatic database normalization,” in 2010 The 2nd International Conference on Computer and Automation Engineering (ICCAE), 2010, vol. 2, pp. 157–161.

[8]	H. R. Varian, “Big Data: New Tricks for Econometrics,” J. Econ. Perspect., vol. 28, no. 2, pp. 3–27, 2014.
 
