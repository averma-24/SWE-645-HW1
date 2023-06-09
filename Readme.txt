Name: Abhishek Verma
G#: G01358661




Assignment-1 Part 2 : 

-------------------------------------------------------------------------------------------------------------
Folder Structure:
	1. HTML & CSS
	2. WAR File

The HTML & CSS folder contains the index.html and studentSurvey.css files for the student survey form. The form includes a range of form elements, such as text boxes for entering personal information, checkboxes to indicate campus preferences, radio buttons to select interests, a dropdown to specify the likelihood of recommendation, a raffle field, a textarea to provide additional comments, and buttons to either submit or cancel the form.

Description:
The Student Survey Form HTML code includes a range of form elements, such as text boxes for entering personal information, checkboxes to indicate campus preferences, radio buttons to select interests, a dropdown to specify the likelihood of recommendation, a raffle field, a textarea to provide additional comments, and buttons to either submit or cancel the form.

VALIDATIONS:
1. Required fields: The text boxes for first name, last name, street address, city, state, zip, telephone number, e-mail, and date of survey are mandatory fields.
2. First Name and Last Name: They should only contain alphabets and must have at least one character.
3. Zip Code: It must be 5 digits long.
4. Telephone Number: It must be 10 digits long.
5. Email: It must have an '@' to be considered a valid email address.
6. CheckBoxes: They are multi-select by default.
7. Radio Buttons: They are single-select by default.
8. Raffle Field: It is not required field, thus can be submit as an empty field. But if the user enters a value, it must be a comma-separated list of at least 10 numbers between 1-100 (inclusive).

Submit Button: When all the validations are passed, clicking the Submit button will display an alert message saying "Your form has been submitted successfully."
Cancel Button: It is used to reset all the fields.


The external stylesheet provided in the file "studentFormStyle.css" contains style definitions for different elements of the student survey form, including text boxes, checkboxes, radio buttons, dropdowns, and buttons. The styles are defined for various properties such as George Mason Header, George Mason Background Picture, Border Style, Buttons Styling, font size, margin and padding


-------------------------------------------------------------------------------------------------------------

The WAR file is for deploying the student survey form on an EC2 instance on AWS. It contains all the necessary files for the form to run on a Tomcat server. The installation steps for deploying the WAR file on an EC2 instance on AWS are provided below.


Installation Steps for Deploying a Student Survey Web Application on AWS EC2 using Apache Tomcat packaged by Bitnami


Step 1: Launch an Instance

	1.Login to AWS Management Console and select EC2.
	2.Click on the "Launch Instance" button to start the instance launch wizard.
	3.Select "Apache Tomcat 9 with Java 8" from the "AWS Marketplace AMIs."
	4.Choose an instance type based on your application requirements and configure instance details.
	5.Configure the security group and add inbound traffic rules for port 22 and 8080.
	6.Review instance settings and click "Launch."
	7.Create or choose an existing key pair and download the private key file.

Step 2: Connect to the Instance

	1.Wait for the instance to launch and note down the public IP address.
	2.Connect to the instance using SSH, private key file, and public IP address.
	3.To connect to your instance using SSH, you need to follow these steps:
	4.Set the permissions on the private key file to 400 to ensure that only you can read the file: chmod 400 ec2-keypair.pem
	5.Open an SSH client, such as PuTTY for Windows or Terminal for Mac.
	6.Locate the private key file (in this case, ec2-keypair.pem) that corresponds to the key pair you selected when you launched the instance.
	7.Use the SSH client to connect to the public IP address of your instance. Example: ssh -i "ec2-keypair.pem" bitnami@54.90.54.160
	8.Once connected to the server, navigate to this directory: /opt/bitnami/apache-tomcat/webapps/manager/META-INF
	9.Modify the "context.xml" file and comment out the entire valve section.


Step 3: Deploy the Student Survey Web Application

	1.Open the "Tomcat Web Application Manager" page by navigating to http://<public-ip-address>:8080/manager/html (replace <public-ip-address> with the actual public IP address of the instance).
	2.Navigate to the "WAR file to deploy" section and click on the "Choose file" button.
	3.Select the WAR file of the student survey web application that you wish to deploy/upload and then click on the "Deploy" button.
	4.Once the WAR file has been uploaded/deployed, open the newly deployed instance by clicking on it through the "Path" section in the "Applications" table.
	5.Test the application to ensure that it is running correctly. If there are any issues, refer to the logs in the /opt/bitnami/apache-tomcat/logs directory.

-------------------------------------------------------------------------------------------------------------

Link for Index.html(Part 1):
http://iamabhishek.s3-website-us-east-1.amazonaws.com

Link for Student Survey Form(Part 2):
https://ec2-44-197-169-25.compute-1.amazonaws.com/studentSurveyForm/
