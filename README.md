# Duo Auto Accept
### *Disclaimer:*  Use this at your own risk. Automating two factor authentication will reduce security and nullify any advantages provided by it

This document is aimed at providing a solution on Android devices for the annoying number of 2FA requests caused by trying to login to any University of Michigan service. Please note that using this script is as good as *not* having 2FA enabled, so do consider the security implications before proceeding. 

## Android
* Install [Duo Mobile](https://play.google.com/store/apps/details?id=com.duosecurity.duomobile&hl=en_US) on your device and set up your account normally as per this [ITS document](https://documentation.its.umich.edu/2fa/enroll-smartphone-or-tablet-duo). If you are already using Duo Mobile on your device you can skip this step

* Download [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=en_US) from the Play Store ($2.99)

* Download [AutoNotification](https://play.google.com/store/apps/details?id=com.joaomgcd.autonotification&hl=en_US)
    * AutoNotification is a plugin for Tasker that enhances Tasker's ability to manipulate and interact with notifications
    * AutoNotification is part of [AutoApps](https://play.google.com/store/apps/details?id=com.joaomgcd.autoappshub&hl=en_US), a family of plugins developed by [joaomgcd](https://joaoapps.com/)
    * AutoNotification is free with ads and an ad-free version can also be purchased through the AutoApps app 

* Download the [DuoAutoAccept.tsk.xml](https://raw.githubusercontent.com/adishy/AutomateDuo/master/DuoAutoAccept.tsk.xml) from the repository

* Import the task into Tasker (long press the Tasks tab)

<p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/1_ImportTask.jpg" width="256" title="Importing the task that was downloaded">
</p>

* Once you have imported the task you should see it listed under the Tasks tab with the name "T"

<p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/2_ImportedTask.jpeg" width="256" title="Imported task">
</p>

* Feel free to open the task and look at and modify the steps used to automate the process
    * If the script takes too long/fails to work correctly, try to tweak the time interval in Step 4
<p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/3_ViewTask.jpeg" width="256" title="Viewing the task">
</p>

* To link the task to the Duo Mobile app, we must first create a profile that listens for a Notification UI Event and then runs the task when the appropriate event was fired. To do this, first add a new profile

 <p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/4_AddProfile.jpg" width="256" title="Viewing the task">
</p>

* Select "Event" for the Profile type

 <p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/5_AddProfileSelectEvent.jpeg" width="256" title="Viewing the task">
</p>

* Select "UI" for the Event category

 <p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/6_AddProfileSelectEventCategory.jpg" width="256" title="Viewing the task">
</p>

* Select "Notification" for UI Event type

 <p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/7_AddEventSelectUIEvent.jpeg" width="256" title="Viewing the task">
</p>

* Give the profile a title if you desire and then select "Owner Application"

 <p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/8_AddProfileEditUIEventSettings.jpeg" width="256" title="Viewing the task">
</p>

* In the list of apps that appear, select Duo Mobile then tap back

 <p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/9_AddProfileSelectUIEventApp.jpeg" width="256" title="Viewing the task">
</p>

* Tap back again to go to the profile tab. You will be prompted to select a task to link to the profile. Select the imported task. You have now linked the task to the profile!

 <p align="center">
  <img src="https://raw.githubusercontent.com/adishy/AutomateDuo/master/screenshots/10_LinkTaskToAppProfile.jpeg" width="256" title="Viewing the task">
</p>

* Your phone should now accept any Duo Mobile Notifications automatically.