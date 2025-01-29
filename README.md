### Files and Network Sharing

### Objective
  
Setting up network sharing on Windows Servers allows users and devices to securely access and share files, folders, and resources over a network. It helps streamline collaboration, improve accessibility, and enforce permissions for controlled data access.

### Skills Learned

-
- 

### Tools Used

- VMware Workstation Pro
- Windows Server 2022

### Steps

*Ref 1: Setting up File Services*

![image](https://github.com/user-attachments/assets/63225de4-6851-4bf2-9799-aef6fcb31ad6)

*Ref 2: Creating a new folder under local disk (C:) on our server and labeling it "SHARED"*

![image](https://github.com/user-attachments/assets/5eab0fe2-c06a-4d83-911e-63a5468c83b7)

*Ref 3: Right click SHARED folder, go to "sharing" tab, click the box for "share this folder", then click "add" and type in domain in the field. From there "check name" then look for "domain users" and click on it. From there you should see Domain Users under share permissions. Click apply and okay on all the open tabs to apply the settings*

![image](https://github.com/user-attachments/assets/29408179-c644-4bcd-922b-f6939f01756b)

*Ref 4: Under the "security" tab you can give permissions to a single user or a group depending on the needs of the company or job role*

![image](https://github.com/user-attachments/assets/69b0626e-85fc-48f2-b2ca-9a85db9ae0ca)

*Ref 5: Set up Client Machines*

![image](https://github.com/user-attachments/assets/0a9dc45c-ba97-4fdf-93b6-686067dd0e90)

*Ref 6: On client's machine we set up map network drive by right clicking on "this pc" then going to map network drive. From there select a drive you'll want but in this case I selected "S:" for our drive. Under folder, type in your server name and the shared folder. i.e. \\WIN-0G53M1m70MV\SHARED. Don't forget to uncheck *

![image](https://github.com/user-attachments/assets/9c22a900-833c-4c54-89a6-49ddba178203)

*Ref 7: Once the task is completed you should see your SHARED file under "network locations"*

![image](https://github.com/user-attachments/assets/1b7cf044-51e3-4ce7-a01f-3c88e0c99f00)

