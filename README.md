# Mobile_Dev_TD3
As my affinity with the Java language is close to 0, I did not modify any java file and the build is only a basic Login activity.
I instead focused on the different security aspects of the app, securing the different aspects you asked for, and proposing solutions for the 
questions you asked.

- Explain how you ensure user is the right one starting the app
At the first connexion, we ask the ID of the account and setup a local password. These data will be hashed then stored in the database.
Then we will ask for these info each time the app is opened. 

- How do you securely save user's data on your phone ?
For the login info, I add salt to the data, then encode it in Base64, hash it with the SHA1 Algorithm and store it into the SQLite database.
For the other info that needs to be retrieved, I use a StringXOR algorithm to encrypt the data, then store it in the SQLite database.

- How did you hide the API url ?
 I store the URL inside an environmental variable with Gradle, this way it isn't in the source code and only read and injected at build time.
 I define it into the gradle.properties file under APIBaseURL, then define the Base_URL in the module's build.gradle file

