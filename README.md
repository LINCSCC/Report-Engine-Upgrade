# Report-Engine-Upgrade
Follow the below instructions:


1.	Users should be logged out of the environment (disable Agresso application in Citrix and close any Agresso sessions open on Citrix)
2.	Logon onto the Business Server and set the Agresso services to manual and stop the services.
3.	Open Powershell and enter : iisreset /stop 
4.	Navigate to the the Report Engine folder that contains the correct version of RE that you wish to depplye and double click on the Seteup.exe.
5.	Once the install is completed, the CCC files should also be updated via AMC. 
6.	Within AMC - delete the Report Engine under Web Applications and Add new report engine. Publish the webpage and ensure the URL does state 'PASS'.
5.	The CCC files should then be updated on each server in the Citrix farm. To do this make make the Citrix team aware and provide them with the network path to the 'BIN' folder.
6.	Agresso services can then be started and the web server restarted (iisreset /start).
7.	Test that Report Engine web service now works.


If any errors occur on step step 5 - when updating files via AMC this will be due to users being logged onto the server.  Need to go to Task Manager - Users tab and disconnect all users.  Re-run the step and it should now go through.

Once installed.

Test to perform are:
Load the Webpage through AMC-Web Applications-Report Engine-Publish-open in browser and ensure 'PASS' is included in the URL
Open Excel and login into Excelator and run query:

sql select * from acuheader		
sql where client = 'EN'		
query		
		
columns	apar_id	apar_name
detail	0	0
		
Click on 'Load' to bring results back and 'unload' to view query again.
