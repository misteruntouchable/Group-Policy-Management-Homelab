# Group-Policy-Management-Homelab

### [Pictoral Walkthrough Demonstration]

<h2>Description</h2>
 In this lesson I will discuss and demonstrate Group Policy Management found in Active Directory. The plan is to create and set 
 up GPOs (Group Policy Objects). Then the other plan is to implement the GPOs we have create. The purpose of group policy is to allow an administrator 
 to have centralized control of users and computers on a network. 

 <h2>Prerequisites</h2>
   For this lab we will not get into how to install virtual box or Active Directory. Oracle Box should be downloaded and installed, Windows Server 19 
   should have been downloaded and installed. Windows 10 should have been installed and Active Directory Domain Services be installed and configured 
   before this lab configuration.

 <h2>Languages and Utilities Used</h2>
  -<b>Microsoft Windows 10 Pro</b>
  
- <b>Oracle Virtual Box</b>
 - <b>Windows Server 19</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>
  <b>Active Directory Group Policy Management Console</b>


  <h2>Program walk-through:</h2>
<p align="center">
 Installing Group Policy Management Console: <br/>
 <img src="https://imgur.com/aPsGxKP.png" height="80%" width="80%" "/>
<p align="center"> First after we have entered into Windows Server 19 is go to Add Roles and Features and after you have checked Active Directory 
                   Domain Services go to Group Policy Managment and ensure both of these features are installed into the server.</br>

</br>                   
</br>

<p align="center">
   Configuring inside Group Policy Managment Console:</br>
<img src="https://imgur.com/gNzKNia.png" height="80%" width="80%""/>
 <p align="center"> Next inside the Windows Server VM go to the search prompt and type  "Group Policy Management Console and open. 
                    Our intention is to change the group policy. So within the console you need to extend your domain and find Group Policy 
                   Object. Right Click the Object and then go to edit. This should open Group Policy Managment Editor. This is where you can create
                   different policies for your domain.</br>
  </br>
  </br>
  
  </br>
<br />
<p align="center">
 Group Policy Managment Editor: </br>
<img src="https://imgur.com/M31NyDR.png" height="80%" width="80%""/>
 <p align="center">  There are two types of configurations in GPME setting,computer and user. Computer configuration applies to the local 
                      computer and does not change per user. User configuration applies to the users on the local machine and will apply 
                      to any new users in the future on the local computer. An example of both of these definitions is that if you wanted 
                      to create policy or settings for all of your computers in a network you will use computer configuration. But if 
                      you want to apply a policy to people working within a company or business you are going to use the user configuration.
                      <br/>


<br />
<br />


</br>
<br/>
<p align="center">
 Group Policy Managment (Policies and Preferences): </br>
<img src="https://imgur.com/RcA9uxZ.png" height="80%" width="80%""/>
 <p align="center"> Now if we check under the settings of Computer and User Configuration you should see more options or settings available.
                    Two of the main options to be addressed here are policies and preferences. The differences between the two are that policies 
                     can't be changed by users that are enforced. Policies restrict the user's choices and can be enforced by admins. An 
                     example of these are password policies or account lockout policies. Preferences are settings that can be changed by the
                      users. Ex. mapped networks, drivers, printers, desktop shortcuts.<br/>


<br />
<br />


</br>
<br/>
<p align="center">
  Setting Up Group Policy(Password Policy) </br>
<img src="https://imgur.com/HUPYEMU.png" height="80%" width="80%""/>
 <p align="center"> Now let's set up a password policy to enforce a strong password and enhance the security. First we want to the Group
                    Policy Management Console, as we have discuss earlier, then right click on your domain, then click Create a GPO in this Domain.
                    This will open GPOEditor . Go to computer config-->Policies---->Windows Settings--->Security Settings---->Then find Password Policy<br/>


<br />
<br />

</br>
<br/>
<p align="center">
  Setting a Password Policy </br>
<img src="https://imgur.com/cf6V1bb.png" height="80%" width="80%""/>
 <p align="center"> At Password Policy right click on it then click edit. There are different opitons to set polices like Length of a password, Complexity
                    of a password, Age of the Password, etc.. You will have the option to decide the password policy you want to set for the users under your 
                    your domain.<br/>


<br />
<br />

</br>
<br/>
<p align="center">
  Setting Drive Mapping </br>
<img src="https://imgur.com/RQbq8P0.png" height="80%" width="80%""/>
 <p align="center"> This example shows how to use driving mapping in preferences to share files instead of policies and will affect individual users instead of 
                    all the members within a domain. To do this the process is similar to setting policies. We want to the Group
                    Policy Management Console, then right click on your domain, then click Create a GPO in this Domain. But instead of computer configuration go 
                    to the User configuration go to preferences---> windows settings.--->Drive Maps---->right click a hit new map drive..create a path for 
                    a shared folder and apply.  This will give you the ability to move around shared folders.      
                     <br/>


<br />
<br />


  </br>
<br/>
<p align="center">
  Implementing and Testing </br>
<img src="https://imgur.com/JPFd5vm.png" height="80%" width="80%""/>
 <p align="center"> To implement the GPOs we want to implement them where we want to use them. Go to the Group Policy Management Console and for the two tasks 
                    that we have created(Password Policy, and Drive Maps) we will find them in Group Policy Objects then drag and drop them into the 
                    Organizational Units or Users where we want to apply them.  To test go to the client machine. Note: By default, Windows refreshes Group 
                    Policy Setting every 90 minutes but if we need the policy to apply right away go to the command prompt in the Client VM and open. They type 
                   "gpupdate /force" and restart the machine. All the policies that you have created should immediately apply.<br/>


<br />
<br /> 
   
  
  



  
