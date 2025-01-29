### Files and Network Sharing

### Objective
  
Setting up network sharing on Windows Servers allows users and devices to securely access and share files, folders, and resources over a network. It helps streamline collaboration, improve accessibility, and enforce permissions for controlled data access.

### Skills Learned

- Learn how to create shared folders with appropriate permissions
- Set NTFS and share permissions to allow domain users access
- Map network drives to access shared folders
- Configure GPOs to automatically map network drives for users
- Implement quotas and file screening using File Server Resource Manager (FSRM)

### Tools Used

- VMware Workstation Pro
- Windows Server 2022
- Group Policy Management

### Steps

*Ref 1: Setting up File Services*

![image](https://github.com/user-attachments/assets/63225de4-6851-4bf2-9799-aef6fcb31ad6)

*Ref 2: Creating a new folder under local disk (C:) on our server and labeling it "SHARED".*

![image](https://github.com/user-attachments/assets/5eab0fe2-c06a-4d83-911e-63a5468c83b7)

*Ref 3: Right click SHARED folder, go to "sharing" tab, click the box for "share this folder", then click "add" and type in domain in the field. From there "check name" then look for "domain users" and click on it. From there you should see Domain Users under share permissions. Click apply and okay on all the open tabs to apply the settings.*

![image](https://github.com/user-attachments/assets/29408179-c644-4bcd-922b-f6939f01756b)

*Ref 4: Under the "security" tab you can give permissions to a single user or a group depending on the needs of the company or job role.*

![image](https://github.com/user-attachments/assets/69b0626e-85fc-48f2-b2ca-9a85db9ae0ca)

*Ref 5: Set up Client Machines.*

![image](https://github.com/user-attachments/assets/0a9dc45c-ba97-4fdf-93b6-686067dd0e90)

*Ref 6: On client's machine we set up map network drive by right clicking on "this pc" then going to map network drive. From there select a drive you'll want but in this case I selected "S:" for our drive. Under folder, type in your server name and the shared folder. i.e. \\WIN-0G53M1M70MV\SHARED. Don't forget to uncheck "reconnect at sign-in".*

![image](https://github.com/user-attachments/assets/9c22a900-833c-4c54-89a6-49ddba178203)

*Ref 7: Once the task is completed you should see your SHARED file under "network locations".*

![image](https://github.com/user-attachments/assets/1b7cf044-51e3-4ce7-a01f-3c88e0c99f00)

*Ref 8*: Configure GPOs to automatically map network drives for users (this process is better if the user needs constant access to the network shared folder) the pervious implemenation is suitable if the user needs to access the folder on one specific day.*

![image](https://github.com/user-attachments/assets/5ae2f48d-39dc-484a-8b95-eb46bc052f5b)

*Ref 9: Back on our server, we open up the GPO task window and from there right click on "Group Policy Objects" folderr to create a new GPO folder and naming it "Mapped Drives".*

![image](https://github.com/user-attachments/assets/3027f689-9ed7-4fe5-9fc9-896dacc52725)

*Ref 10: Right click on the "Mapped Drives" folder and click edit. Then User Configuration->Windows Settings->Drive Map->New->Mapped Drive.*

![image](https://github.com/user-attachments/assets/73a1e0a0-7a43-4679-9599-ef1757491ad5)

*Ref 11: For location, you'll want to enter your \\server\share i.e. \\WIN-0G53M1M70MV\SHARED. Label as "SHARED" and change the drive to S:, for simplicity. CLick apply and okay.*

![image](https://github.com/user-attachments/assets/ce030be0-f95c-44dd-b261-4e0955785e2f)

*Ref 12: Click and drag your new Mapped Drives GPO into the user folder to apply it.*

![image](https://github.com/user-attachments/assets/a9869242-eeb0-4278-8bac-7f082a11c948)

*Ref 13: Going back to the the client machhine to test if the map drive GPO is applied correctly. Since it didn't show up we need to force the update from the command prompt*

![image](https://github.com/user-attachments/assets/79d50060-39f5-4e7a-b597-f6cea64f8ce7)

*Ref 14: Using the command "gpupdate /force" in the command prompt to force the update*

![image](https://github.com/user-attachments/assets/1c61f371-cc16-48e7-9565-3fa4345c7f6e)

*Ref 15: Once the update is complete, go ahead and restart the computer to see if the update has been applied and we can see the map drive under shared network*

![image](https://github.com/user-attachments/assets/5b26cfaf-4f83-4bd4-830d-dbdf2552df62)

*Ref 16: Map drive GPO was successfully implemented on client's machine and it'll remain there even after rebooting*

![image](https://github.com/user-attachments/assets/60b9f382-899f-461c-995d-ebb24343f996)

*Ref 17: Activity 4: Implementing quotas and file screening using File Server Resource Manager (FSRM) 

![image](https://github.com/user-attachments/assets/46918186-9b6e-48c6-b552-850ea9b75c69)

