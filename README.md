from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Edge()
driver.get("https://www.google.com")

time.sleep(5)   # wait for 5 seconds

e = driver.find_element(By.NAME, "q")

print(e.tag_name, e.get_attribute("type"))

driver.quit()


from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Edge()
driver.get("https://www.google.com")

search = driver.find_element(By.NAME, "q")
btn = driver.find_element(By.NAME, "btnK")

print(search.is_displayed(), btn.is_enabled())

search.send_keys("Selenium")

driver.quit()

from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Edge()
driver.get("https://www.facebook.com")

driver.find_element(By.ID, "email")
driver.find_element(By.ID, "pass")
driver.find_element(By.NAME, "login")

print("Login page elements found")

driver.quit()




2
cd C:\Users\kallu\hello-docker
notepad index.html
notepad Dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
dir
ren Dockerfile.txt Dockerfile
docker build -t hello-app .
docker run -d -p 8080:80 hello-app
http://localhost:8080
3
mkdir alpine-nano
cd alpine-nano
Create Dockerfile 
FROM alpine:latest
RUN apk add --no-cache nano
CMD ["sh"]
Build image 
docker build -t alpine-nano .
Run container 
docker run -it --name nano-test alpine-nano
Verify Nano
Inside the container, type:
Nano  # If Nano opens, it is installed successfully.
4
mkdir mysql-docker
cd mysql-docker
Create Dockerfile 
FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=root123
ENV MYSQL_DATABASE=testdb
EXPOSE 3306
Build Docker Image 
docker build -t mysql-app .
Run MySQL Container 
docker run -d -p 3307:3306 --name mysql-container mysql-app
Access MySQL inside Container 
docker exec -it mysql-container mysql -u root -p
Enter password: root123
Execute Simple Query 
SHOW DATABASES;
Create Table and Insert Data
USE testdb;

CREATE TABLE student (
    id INT,
    name VARCHAR(50)
);
INSERT INTO student VALUES (1, 'Tharun');
SELECT * FROM student;

5
Create the project folder 
mkdir mysql-phpmyadmin
cd mysql-phpmyadmin
Create the Dockerfile 
FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=root123
ENV MYSQL_DATABASE=sampledb
EXPOSE 3306
Build the MySQL image 
docker build -t my-mysql-image .
Run the MySQL container 
docker run -d --name mysql-container1 -p 3307:3306 my-mysql-image
Run phpMyAdmin container 
docker run -d --name phpmyadmin-container -e PMA_HOST=host.docker.internal -e PMA_PORT=3307 -p 8081:80 phpmyadmin/phpmyadmin
Open phpMyAdmin 
http://localhost:8081
Login 
Username: root















Experiment No- 4
AIM:
To explore and practice basic Git and GitHub commands.
OBJECTIVES:
•	Understand version control concepts.
•	Learn basic Git commands for local repository management.
•	Explore GitHub for remote repository handling.
MATERIALS REQUIRED:
•	A computer with Git installed.
•	A GitHub account.
•	Internet connection.
THEORY:
Git is a distributed version control system used for tracking changes in source code during software development. GitHub is a cloud-based hosting service that helps developers manage Git repositories collaboratively.
PROCEDURE:
Step 1: Install Git
1.	Check if Git is installed:
git --version
2.	If not installed, download and install Git from https://git-scm.com/.
Step 2: Configure Git
1.	Set up user information:
2.	git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
Step 3: Initialize a Local Repository
1.	Create a new directory and navigate into it:
2.	mkdir my-project
cd my-project
3.	Initialize Git:
git init
Step 4: Create and Commit Files
1.	Create a new file:
echo "Hello, Git!" > README.md
2.	Add the file to staging:
git add README.md
3.	Commit the changes:
git commit -m "Initial commit"
Step 5: Connect to GitHub
1.	Create a new repository on GitHub (without initializing README).
2.	Add the remote repository:
git remote add origin https://github.com/your-username/my-project.git
Step 6: Push Changes to GitHub
1.	Push the local commits to GitHub:
2.	git branch -M main
git push -u origin main
Step 7: Clone a Repository
1.	Clone a GitHub repository:
git clone https://github.com/your-username/my-project.git
Step 8: Pull and Fetch Changes
1.	Fetch the latest changes from the remote repository:
git fetch
2.	Pull changes into your local repository:
git pull origin main
Step 9: Branching and Merging
1.	Create a new branch:
git branch feature-branch
2.	Switch to the new branch:
git checkout feature-branch
3.	Merge the branch:
4.	git checkout main
git merge feature-branch
Step 10: Undoing Changes
1.	Revert the last commit:
git revert HEAD
2.	Reset to a previous state:
git reset --hard <commit-hash>
OBSERVATIONS:
•	Noted how Git tracks changes in files.
•	Understood the role of GitHub in collaboration.
•	Learned different Git commands for version control.
CONCLUSION:
This experiment helped in understanding the fundamental Git and GitHub commands used in version control and collaborative development.




















 
Experiment No- 5
AIM:
Creating a New Git Repository and Pushing Changes to a Remote Repository

Objective:
 To understand and implement the process of creating a Git repository, adding a README file, committing changes, and pushing them to a remote repository.
Requirements:
•	Git installed on your system
•	A GitHub account
•	Internet connection
Algorithm:
1.	Initialize a Git Repository:
Open the terminal or command prompt.
Navigate to the desired directory where you want to create the repository.
Run the following command to initialize the repository:
      git init
2.	Create a README File:
Use the following command to create a README file:
echo "# My New Repository" > README.md
Alternatively, create the file manually and add some content.
3.	Add the README File to Staging Area:
Use the following command to add the file to the staging area:
git add README.md
4.	Commit the Changes:
Commit the added file using the following command:
git commit -m "Initial commit: Added README file"
Create a Remote Repository on GitHub:
Log in to your GitHub account.
Click on the "+" icon and select "New repository".
Enter a repository name and description.
Choose "Public" or "Private" as per requirement.
Click "Create repository".
5.	Link the Local Repository to Remote Repository:
o	Copy the repository URL from GitHub.
o	Run the following command to add the remote origin:
git remote add origin <repository_url>
6.	Push the Changes to Remote Repository:
o	Use the following command to push the changes:
git push -u origin main
o	If the default branch is "master", use:
git push -u origin master
Verification:
•	Go to your GitHub repository page and verify that the README file has been uploaded successfully.
Conclusion: By following these steps, we successfully created a Git repository, added a README file, committed the changes, and pushed them to a remote repository on GitHub.



 
Experiment No- 6
AIM:
Create a new branch called "MITS" and make some changes to a file. Commit the changes and merge the branch with the main branch.
	
 Objective:
To understand the process of creating a new branch in Git, making changes to a file, committing those changes, and merging the branch back into the main branch.
Requirements:
Git installed on the system
A working terminal or command prompt

Procedure:

Step 1: Initialize a Git Repository
```bash
git init
```
This command initializes a new Git repository in the current directory.

Step 2: Create a New Branch
```bash
git checkout -b MITS
```
This command creates a new branch named "MITS" and switches to it.

Step 3: Make Changes to a File
```bash
echo "This is a test change in the MITS branch." > sample.txt
```
This command creates a new file named `sample.txt` and writes some content into it.

Step 4: Add and Commit the Changes
```bash
git add sample.txt
git commit -m "Added sample.txt with initial content in MITS branch"
```
These commands stage and commit the changes made to `sample.txt`.

Step 5: Switch Back to the Main Branch
```bash
git checkout main
```
This command switches back to the main branch.

Step 6: Merge the MITS Branch with the Main Branch
```bash
git merge MITS
```
This command merges the `MITS` branch into the `main` branch.

Step 7: Delete the MITS Branch (Optional)
```bash
git branch -d MITS
```
This command deletes the `MITS` branch after merging.

Expected Output:
- A new branch `MITS` is created.
- Changes are made to `sample.txt`.
- The changes are committed and merged back into the `main` branch.
- The `MITS` branch is deleted after merging.

Conclusion:
This experiment demonstrates the fundamental operations of branching, modifying files, committing changes, and merging branches in Git, which are essential for version control in software development.


 
Experiment No-7
AIM:
Use Git log to view the commit history of a repository and find the commit hash of a specific commit.

Objective: 
To understand how to use git log to view the commit history of a Git repository and retrieve the commit hash of a specific commit.
Requirements:
•	A computer with Git installed
•	A pre-existing Git repository or a newly initialized repository
•	Basic knowledge of Git commands
Procedure:
1.	Setting Up the Environment:
Open a terminal (Command Prompt, Git Bash, or Terminal).
Navigate to the repository using the cd command.
cd path/to/your/repository
2.	Viewing the Commit History:
Use the git log command to display the commit history.
git log
This command will show the commit history with details like commit hash, author, date, and commit message.
3.	Finding a Specific Commit Hash:
Scroll through the commit history and locate the commit message corresponding to the commit of interest.
The commit hash is the long alphanumeric string at the beginning of each commit entry.
4.	Filtering the Commit History:
Use the --oneline option to display a simplified history.
git log --oneline
This shows only the commit hashes and messages in a single line per commit.
Example output:
a1b2c3d Update README file
e4f5g6h Fix login bug
i7j8k9l Initial commit
Identify the hash of the required commit from this output.
5.	Searching for a Specific Commit Message:
Use git log --grep="commit message" to search for a commit by message.
git log --grep="Fix login bug"
6.	Viewing Commit Details Using Commit Hash:
Once the commit hash is identified, use it to view detailed information about the commit.
git show a1b2c3d
Observations:
•	The commit history provides a chronological view of repository changes.
•	The commit hash uniquely identifies each commit.
•	Filtering options help quickly locate a specific commit.


 

Experiment No- 8
AIM:
Cloning a Git Repository from a Remote Repositor

Objective: To understand and perform the process of cloning a Git repository from a remote repository using Git commands.
Prerequisites:
1.	Basic understanding of Git and version control.
2.	Git installed on the system.
3.	An active internet connection.
4.	A GitHub, GitLab, or Bitbucket account.
Materials Required:
1.	A computer with Git installed.
2.	A pre-existing repository URL from a remote platform (GitHub, GitLab, etc.).
Step 1: Verify Git Installation
Step 1: Verify Git Installation
1.	Open the terminal or command prompt.
2.	Run the following command to check if Git is installed:
git --version
3.	If Git is not installed, download and install it from Git Official Website.
Step 2: Navigate to the Desired Directory
1.	Choose a directory where you want to clone the repository.
2.	Use the cd command to navigate to that directory:
cd path/to/your/directory
Step 3: Clone the Repository
1.	Copy the repository URL from the remote platform (GitHub, GitLab, etc.).
2.	Run the following command to clone the repository:
git clone <repository_url>
Example:
git clone https://github.com/example-user/example-repo.git
3.	This command downloads the repository to your local system.
Step 4: Verify Cloning
1.	Navigate into the cloned repository:
cd example-repo
2.	List the files to check the contents:
3.	ls  (Linux/macOS)
dir (Windows)
4.	Check the remote repository link:
git remote -v
Step 5: Make a Change and Push to Remote (Optional)
1.	Create a new file inside the cloned repository:
echo "Hello Git" > testfile.txt
2.	Add the file to the staging area:
git add testfile.txt
3.	Commit the changes:
git commit -m "Added testfile.txt"
4.	Push the changes to the remote repository:
git push origin main

Expected Outcome: Students should be able to successfully clone a Git repository, navigate within it, and optionally make changes and push updates to the remote repository.


 
Experiment No- 9
AIM:
Pushing Changes from Local Repository to Remote Repository Using Git.
Objective: To understand and perform the process of pushing local repository changes to a remote repository using Git.
Prerequisites:
•	Basic knowledge of Git and GitHub.
•	Git installed on the system.
•	A GitHub account.
Software & Tools Required:
•	Git
•	GitHub
•	Command Line Interface (CLI) or Git Bash
Theory: Version control systems help track changes in code over time. Git is a distributed version control system that allows multiple developers to work collaboratively. Pushing changes means transferring committed changes from a local repository to a remote repository.
Experimental Setup:
1.	Install Git (if not installed):
Windows: Download from https://git-scm.com/ and install.
Linux: Use sudo apt install git (Debian-based) or sudo yum install git (RHEL-based).
MacOS: Use brew install git.
2.	Set Up Git (First-time users)
3.	git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
Procedure:
1.	Create a Local Repository
2.	mkdir MyProject
3.	cd MyProject
git init
This initializes a new Git repository in the MyProject directory.
4.	Create a File and Make Initial Commit
5.	echo "Hello, Git!" > file.txt
6.	git add file.txt
git commit -m "Initial commit"
This creates a file, adds it to the staging area, and commits it.
7.	Create a Remote Repository on GitHub
Log in to GitHub and create a new repository.
Copy the repository URL.
8.	Connect Local Repository to Remote Repository
git remote add origin <repository_URL>
9.	Push Changes to Remote Repository
10.	git branch -M main
git push -u origin main
This pushes the committed changes to the remote repository.	


Expected Output:
A new repository is created on GitHub with the committed file.
The repository reflects the changes made locally.


Password: root123




