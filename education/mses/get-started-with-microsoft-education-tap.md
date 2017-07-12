---
title: Deploy and manage a full cloud IT solution with Microsoft Education
description: Learn how to use the new Microsoft Education system to set up a cloud infrastructure for your school, acquire devices and apps, and configure and deploy policies to your Windows 10 devices.
keywords: education, Microsoft Education, Microsoft Education system, full cloud IT solution, school, deploy, setup, manage, Windows 10, Intune for Education, Office 365 for Education, Microsoft Store for Education, Azure AD, Set up School PCs
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: edu
author: CelesteDG
---

# Get started: Deploy and manage a full cloud IT solution with Microsoft Education

![Learn how to deploy and manage a cloud solution with MSES!](images/mses_getstarted_banner.png)

**Applies to:**

-   Office 365 for Education, School Data Sync, Microsoft Intune for Education, Microsoft Store for Education, Windows 10 Creators Update, Set up School PCs

Hello, IT administrators! In this walkthrough, we'll show you how you can quickly and easily use the new Microsoft Education system, consisting of new and existing cloud services and tools, to implement a full IT cloud solution for your school.

## What is Microsoft Education?
**Microsoft Education** consists of these new and existing services and tools from Microsoft:
- **Microsoft Intune for Education** for simple set up, control, and management of the resources for your school including apps, devices, and settings
- **Office 365 for Education** provides online apps for work from anywhere and desktop apps for advanced functionality, built for working together and available across devices, and it's free for schools, teachers, and students
  - **School Data Sync** to help automate the process for importing and integrating School Information System (SIS) data that you can use with Office 365
  - **OneNote Class Notebook** to organize course content, create and deliver interactive lessons to some or all students, collaborate and provide private feedback to individual students, and connect with major LMS and SIS partners for assignment workflow
- **Microsoft Teams** to bring conversations, content, and apps together in one place and create collaborate classrooms, connect in professional learning communities, and communicate with school staff 
- **Learning Tools** are moving beyond the OneNote desktop app and is now available in Office Lens, OneNote Online, Word Online, and Word desktop
- **Whiteboard** to create interactive lessons on the big screen, share and collaborate real-time by connecting to Class Notebook and Classroom
- **Windows 10, version 1703 (Creators Update)** which brings 3D for everyone and other new and updated Windows features
- **Minecraft: Education Edition** which provides an open and immersive environment to promote creativity, collaboration, and problem-solving 

With Microsoft Education, schools can:
- **Use affordable devices and simple setup** - Boost creativity and get started instantly with Windows 10 devices that support Windows Ink. Set up devices in minutes and stay in control with the new Intune for Education.
- **Collaborate in a modern classroom** - Help students become career-ready with Office apps like Word, Excel, PowerPoint, and OneNote. Increase comprehension and outcomes with the most advanced teaching apps like integrated Learning Tools.
- **Go beyond the browser with inspiring apps for classroom learning** - Inspire with Minecraft: Education Edition and innovative apps from the Microsoft Store for Education.

Go to the <a href="https://www.microsoft.com/en-us/education" target="_blank">Microsoft Education site</a> to learn more. See <a href="https://www.microsoft.com/en-us/education/buy-license/overview-of-how-to-buy/default.aspx?tabshow=schools" target="_blank">How to buy</a> to learn about pricing and purchasing options for schools, students, and teachers as well as academic pricing and offers for qualified K-12 and higher education institutions.

## What we're doing
In this walkthrough, we'll show you the basics on how to:
- Acquire an Office 365 for Education tenant, if you don't already have one
- Import school, student, teacher, and class data using School Data Sync (SDS)
- Manage apps and settings deployment with Intune for Education
- Acquire additional apps in Microsoft Store for Education
- Use the Set up School PCs app to quickly set up and provision your Windows 10 education devices
- Log in and use the devices

This diagram shows a high-level view of what we cover in this walkthrough. The numbers correspond to the sections in the walkthrough and roughly correspond to the flow of the overall process; but, note that not all sections in this walkthrough are shown in the diagram.

![Deploy and manage a full cloud IT solution using Microsoft Education](images/microsoft_education_it_getstarted_workflow.png)

## Prerequisites
Complete these tasks before you start the walkthrough:
- Make sure all the devices that you want to configure, such as student PCs, have the latest Windows 10, version 1703 image installed.

  We recommend Windows 10, version 1703 to take advantage of all the new features and functionality that Windows supports. This version of Windows is also compatible with the latest version of the Set up School PCs app and the versions must match in order for Set up School PCs to provision the devices. 

  If you don't have Windows 10, version 1703 installed on your devices, we recommend upgrading. This process takes a while so start this task before proceeding with this walkthrough. 

- Open an InPrivate session on your browser.

  > [!IMPORTANT] 
  > **This document is for internal use only**. To get started, click on this link: https://aka.ms/intuneforedutrial



## 1. Set up a new Office 365 for Education tenant
Schools can use Office 365 to save time and be more productive. Built with powerful tools and accessible from any device, setting it up is the first step in getting your school to the cloud. 

**To set up Office 365**

1. Create an account and a user ID and password to use to sign into your account. 

  **Figure 1** - Office 365 account creation

  ![Create an Office 365 account](images/o365_createaccount.png)

2. Save your sign-in info so you can use it to sign into https://portal.office.com (the sign-in page). Click **You're ready to go...** 
3. In the **Verify eligibility for Microsoft Office 365 Education** screen:
  1. In the **welcome** screen, click **Next**.
  2. In the **type a domain name** screen, click **I'll verify later** and then click **Yes** on the confirmation window that pops up. 
4. Once the confirmation window goes away, you should see the Office 365 admin center.

   **Figure 2** - Office 365 admin center

   ![Office 365 admin center](images/o365_admincenter_welcome.png)

5. **Optional**. On the **Welcome to the new Office 365 admin center** pop-up window, click **Next** to get a brief tour of the admin center.

As part of setting up a basic cloud infrastructure, you don't need to complete the rest of the Office 365 for Education setup so we will skip the rest of setup for now and start importing school data. You can pick up where you left off with Office 365 for Education setup once you've completed the rest of the steps in the walkthrough. See [6.3 Complete Office 365 for Education setup](#63-complete-office-365-education-setup) for info.

## 2. Use School Data Sync to import student data
School Data Sync (SDS) helps you import Student Information System (SIS) data into Office 365. It helps automate the process for importing and integrating SIS data that you can use with Office 365 and apps like Classroom and OneNote Class Notebooks. To learn more about School Data Sync (SDS) and the deployment methods available to you, see <a href="https://aka.ms/sdsoverview" target="_blank">Overview of School Data Sync and Classroom</a>. We recommend using comma separated value (CSV) files with SDS to synchronize SIS users with Office 365. However, SDS supports many other deployment options such as PowerSchool Sync, Clever Sync, and OneRoster CSV files. See the *For IT admins* section in [Get more info](#get-more-info) to learn more about these other deployment options.

In this section of the walkthrough, we created a new education tenant and we need to add new users. To simplify this process, we will use sample SDS files to prepopulate our tenant with school data. 

**<a name="downloadcsvsamples"></a>Download sample school data**

1. Go to the <a href="https://aka.ms/sdsscripts" target="_blank">O365-EDU-Tools GitHub site</a>.
2. Click the green **Clone or download** button to download the SDS sample files.

  **Figure 3** - Download the SDS sample files from GitHub

  ![Download the SDS sample files from GitHub](images/sds_github_downloadsample.png)

3. In the **Clone with HTTPS** pop-up window, choose **Download ZIP** and note the location where you're saving the folder.
4. Go to the folder where you saved the .zip and unzip the files.
5. Open the **O365-EDU-Tools-master** folder and then open the **CSV Samples** subfolder. Confirm that you can see the following sample CSV files.

  **Figure 4** - Sample CSV files

  ![Use the sample CSV files](images/sds_sample_csv_files_us_uk.png)

  > [!NOTE] 
  > - The sample CSV files uses sample accounts and passwords. If you are using the sample files for testing, remember the accounts and their corresponding passwords. You may be asked to change the password during your first sign in. 
  > - If you are modifying the sample CSV files to use in your organization, change the accounts and passwords to match the user accounts and passwords in your organization.
  > - If you are using CSV files from your existing production environment, see the detailed instructions in step 5 in the next section.

To learn more about the CSV files that are required and the info you need to include in each file, see <a href="https://aka.ms/sdscsvattributes" target="_blank">CSV files for School Data Sync</a>. If you run into any issues, see <a href="https://aka.ms/sdserrors" target="_blank">School Data Sync errors and troubleshooting</a>.

**<a name="assignclassroom"></a>Assign Classroom license**

The Classroom application is retired, but you will need to assign the Classroom Preview license to global admin accounts that will be used to administer SDS. The single license allows global admins to access both Classroom Preview and School Data Sync.

1. In the <a href="https://portal.office.com/adminportal" target="_blank">Office 365 admin center</a>, select **Users > Active users**.
2. Select the checkbox for your global admin account.
3. In the account details window, under **Product licenses**, click **Edit**.
4. In the **Product licenses** page, turn on **Microsoft Classroom** and then click **Save**.
5. Confirm that you can access SDS. To do this:
  - Navigate to <a href="http://sds.microsoft.com" target="_blank">https://sds.microsoft.com</a> and click **Sign in**. When prompted, enter your global admin username and password to access the SDS portal. Or,
  - From the Office 365 admin portal, go to **Admin centers** and click on **School Data Sync** to go to the SDS portal.

  > [!NOTE]
  > Only global admins can access SDS.

**<a name="usesdstoimportdata"></a>Use SDS to import student data**

1. If you haven't done so already, go to the SDS portal, <a href="http://sds.microsoft.com" target="_blank">https://sds.microsoft.com</a>.
2. Click **Sign in**. You will see the **Settings** option for **Manage School Data Sync**.

  **Figure 5** - Settings for managing SDS

  ![Settings for managing SDS](images/sds_sds_and_classroom_off.png)

3. Turn on **School Data Sync**. You will get a notification that it is turned on. Click **OK**.

  New menu options will appear on the left of the SDS portal.

  **Figure 6** - New menu options appear after SDS is turned on

  ![New menu options appear after SDS is turned on](images/sds_sds_on_newmenu_items.png)

4. Click **+ Add Profile** from the sync dashboard or from the menu on the left to start syncing school data.

  This opens up the new profile setup wizard within the main page.

  **Figure 7** - New SDS profile setup wizard

  ![New SDS profile setup wizard](images/sds_updated_addnewprofile.png)

6. For the new profile, in the **Before you begin...** screen:
  1. Enter a name for your profile, such as *Contoso_Profile_1*.
  2. Select a sync method for your profile. For this walkthrough, select **CSV Files**.

    Note that for any sync method that you choose, you can click the **View steps** link to get more information about the steps you need to take depending on the sync method of your choosing.
    
  3. Click **Start**.

7. In the **Sync options** screen:
  1. In the **Select new or existing users** section, you can select either **New users** or **Existing users** based on the scenaro that applies to you. For this walkthrough, select **New users**.
  <!--
    - Choose **New users** if this is a brand new tenant and this is the first time that you're adding users.

        Choose the **New users** option if you are using an unaltered version of the sample CSV files from [Download sample school data](#downloadcsvsamples) or if you created your own CSV files with new users.

    - Choose **Existing users** if you already have a live production tenant, with teachers and students that already have active accounts in Office 365 (cloud only or synced from on-premise Active Directory).

        Using the **Existing users** option, SDS will not attempt to create new users. Instead, it uses the identity matching options in the next section of the setup wizard to match the students and teachers in your CSV files to the user accounts that already exist in Azure. All additiional details for the students and teachers contained within the CSV files will be written as extension attributes on top of the already existing user objects. You can find more information about these settings on the main SDS deployment page for CSV-based deployments in <a href="http://aka.ms/sdscsv" target="_blank">How to deploy School Data Sync by using CSV files</a>.
  -->
  2. In the **Import data** section:
    1. Click **Upload Files** to bring up the **Select data files to be uploaded** window.
    2. In the **Select data files to be uploaded** window, click **+ Add Files** and navigate to the directory where you saved the six CSV files required for data import.
    3. In the File Explorer window, you will see a folder for the sample CSV files for the UK and six sample CSV files for the US. Select the CSV files that match your region/locale, and then click **Open**.
    4. In the **Select data files to be uploaded** window, confirm that all six CSV files (School.csv, Section.csv, Student.csv, StudentEnrollment.csv, Teacher.csv, and TeacherRoster.csv) are listed and then click **Upload**.
    4. After all the files are successfully uploaded, click **OK**. 
  3. Select the domain for the schools/sections. This domain will be used for the Section email addresses created during setup. If you have more than one domain, make sure you select the appropriate domain for the sync profile and subsequent sections being created.
  4. In the **Select school and section properties** section, ensure the attributes that have been automatically selected for you align to your CSV files. If you select additional properties, or deselect any properties, make sure you have the properties and values contained within the CSV files. For the walkthrough, you don't have to change the default.
  5. In the **Sync option for Section Group Display Name**, check the box if you want to allow teachers to overwrite the section names. Otherwise, SDS will always reset the display name value for sections to the value contained within the CSV files.
  6. In the **License Options** section, check the box to enable the Classroom Preview license for all synced students and teachers within the sync profile.
  7. Check the **Intune for Education** checkbox to allow users to receive the Intune for Education license and to create the SDS dynamic groups and security groups, which be used within Intune for Education.
  8. Click **Next**.

    **Figure 8** - Sync options for the new profile

    ![Specify sync options for the new SDS profile](images/sds_profile_syncoptions.png)

8. In the **Teacher options** screen:
  1. Select the domain for the teachers. SDS appends the selected domain suffix to the teacher's username attribute contained in the CSV file, to build the UserPrincipalName for each user in Office 365/Azure Active Directory during the account creation process. The teacher will log in to Office 365 with the UserPrincipalName once the account is created.
  2. In the **Select teacher properties** section, make sure the attributes that have been automatically selected for you align to your CSV files. If you select additional properties or deselect any properties, make sure you have the corresponding properties and values contained within the CSV files. For this walkthrough, you don't have to change the default.
  3. In the **Teacher licenses** section, choose the SKU to assign licenses for teachers. For this walkthrough, choose **STANDARDWOFFPACK_FACULTY**.
  4. Click **Next**.

    **Figure 9** - Specify options for teacher mapping

    ![Specify options for teacher mapping](images/sds_profile_teacheroptions.png)

9. In the **Student options** screen:
  1. Select the domain for the students. SDS appends the selected domain suffix to the student's username attribute contained in the CSV file, to build the UserPrincipalName for each user in Office 365/Azure Active Directory during the account creation process. The student will log in to Office 365 with the UserPrincipalName once the account is created.
  2. In the **Select student properties** section, make sure the attributes that have been automatically selected for you align to your CSV files. If you select additional properties or deselect any properties, make sure you have the corresponding properties and values contained within the CSV files. For this walkthrough, you don't have to change the default.
  3. In the **Student licenses** section, choose the SKU to assign licenses for students. For this walkthrough, choose **STANDARDWOFFPACK_STUDENT**.
  4. Click **Next**.

    **Figure 10** - Specify options for student mapping

    ![Specify options for student mapping](images/sds_profile_studentoptions.png)

10. In the profile **Review** page, review the summary and confirm that the options selected are correct. Click **Create profile**.

  You will see a notification that your profile is being created.

11. You will see a page for your profile. The status might indicate that it's still being set up. 

  **Figure 11** - SDS profile page

  ![SDS profile page](images/sds_profile_profilepage.png)

12. After the profile is created and finished **Setting up**, confirm that the status for your profile now says **Sync enabled**.

  If the status still indicates that the profile is being set up, try refreshing the page until you see the status change to **Sync enabled**.

  **Figure 12** - New profile is sync enabled

  ![Confirm that the new profile is sync enabled](images/sds_profile_syncenabled.png)

  > [!TIP]
  > If you get errors during the pre-sync validation process, your profile status will change to **x Error**. To continue, review or resolve any pre-sync validation errors, and then click **Resume Sync** to start the synchronization cycle.

  Sync times, like file download times, can vary widely depending on when you start the sync, how much data you are syncing, the complexity of your data (such as the number of users, schools, and class enrollments), overall system/network load, and other factors. Two people who start a sync at the same time may not have their syncs complete at the same time.

  You can refresh the page to confirm that your profile synced successfully.

That's it for importing sample school data using SDS.

## 3. Enable Microsoft Teams for your school
Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place. Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services. Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education. 

To get started, IT administrators need to use the Office 365 Admin Center to enable Microsoft Teams for your school. 

**Enable Microsoft Teams for your school**

1. Sign in to <a href="https://portal.office.com" target="_blank">Office 365</a> with your work or school account.
2. Click **Admin** to go to the Office 365 admin center.
3. Go to **Settings > Services & add-ins**.
4. On the **Services & add-ins** page, select **Microsoft Teams**.

  **Figure 13** - Select Microsoft Teams from the list of services & add-ins

  ![Enable Microsoft Teams for your school](images/o365_settings_services_msteams.png)

5. On the Microsoft Teams settings screen, select the license that you want to configure, **Student** or **Faculty and Staff**.

  **Figure 14** - Select the license that you want to configure

  ![Select the Microsoft Teams license that you want to configure](images/o365_msteams_settings.png)

6. After you select the license type, set the toggle to turn on Microsoft Teams for your organization.

  **Figure 15** - Turn on Microsoft Teams for your organization

  ![Turn on Microsoft Teams for your organization](images/o365_msteams_turnon.png)

7. Click **Save**.

You can find more info about how to control which users in your school can use Microsoft Teams, turn off group creation, configure tenant-level settings, and more by reading the *Guide for IT admins** getting started guide in the <a href="https://aka.ms/MeetTeamsEdu" target="_blank">Meet Microsoft Teams</a> page.

## 4. Configure Microsoft Store for Education
You'll need to configure Microsoft Store for Education to accept the service agreement and make sure your Microsoft Store account is associated with Intune for Education.

**Associate your Microsoft Store account with Intune for Education**
1. Sign into <a href="https://businessstore.microsoft.com" target="_blank">Microsoft Store for Education</a>.
2. Accept the Microsoft Store for Business and Education Services Agreement. 

  This will take you to the Microsoft Store for Education portal.

  **Figure 16** - Microsoft Store for Education portal

  ![Microsoft Store for Education portal](images/msfe_store_portal.png)

3. In the Microsoft Store portal, click **Manage** to go to the Microsoft Store **Overview** page.
4. Find the **Overview** page, find the **Store settings** tile and click **Management tools**.

  **Figure 17** - Select management tools from the list of Store settings options

  ![Select management tools from list of Store settings options](images/msfe_storesettings_select_managementtools.png)

4. In the **Management tools** page, find **Microsoft Intune** on the list and click **Activate** to get Intune for Education ready for use with Microsoft Store for Education.

  **Figure 18** - Activate Intune for Education as the management tool

  ![Activate Intune for Education as the management tool](images/msfe_managementtools_activateintune.png) 

Your Microsoft Store for Education account is now linked to Intune for Education so let's set that up next.

## 5. Use Intune for Education to manage groups, apps, and settings
Intune for Education is a streamlined device management solution for educational institutions that can be used to quickly set up and manage Windows 10 devices for your school. It provides a new streamlined UI with the enterprise readiness and resiliency of the Intune service. You can learn more about Intune for Education by reading the **[Intune for Education documentation](https://docs.microsoft.com/intune-education)**. 

### Example - Force a sync, set up Intune for Education, buy apps from the Store, and install the apps
In this walkthrough, we'll go through a sample scenario and walk you through the steps to:
- [Use express configuration to quickly set up Intune for Education](#setupintune)
- [Use Intune for Education to buy apps from the Microsoft Store for Education](#addappsfrommsfe)
- [Use Intune for Education to install the apps for all users in your tenant](#installappsallusers)

Note that for verified education tenants, Microsoft automatically provisions your app catalog with these apps so you will see them appear on your Intune for Education catalog even before you've bought any apps:
- Excel 
- Fresh Paint
- Minecraft: Education Edition
- OneNote
- PowerPoint
- Sway
- Word

  > [!NOTE]
  > Apps that you own in the Microsoft Store for Education are automatically available in Intune for Education. Any changes you make to your purchases get reflected in Intune for Education.


**<a name="setupintune"></a>Set up Intune for Education**

Intune for Education provides an **Express configuration** option so you can get going right away. We'll use that option here.

1. Log into the <a href="https://intuneeducation.portal.azure.com/" target="_blank">Intune for Education console</a>. You will see the Intune for Education dashboard once you're logged in.

  **Figure 19** - Intune for Education dashboard

  ![Intune for Education dashboard](images/i4e_portal.png)

2. On the dashboard, click **Launch Express Configuration**, or select the **Express configuration** option on the menu on the left.
3. In the **Welcome to Intune for Education** screen, click **Get started**.
  
  **Figure 20** - Click Get started to set up Intune for Education

  ![Click Get Started to configure groups, apps, and settings](images/i4e_expressconfiguration_welcome.png)

4. In the **Get school information (optional)** screen, it should indicate that SDS is already configured. Click **Next**.

  **Figure 21** - SDS is configured

  ![SDS is already configured](images/i4e_expressconfiguration_sdsconfigured.png)

5. In the **Choose group** screen, select **All Users**. All apps and settings that we select during express setup will apply to this group. 

  You can choose another group during this step, but note that your experience may vary from what we show in the walkthrough.

6. The **Next** button will appear at the bottom of the screen after you select **All Users**. Click **Next**.

  > [!TIP]
  > At the top of the screen, did you notice the **Choose group** button change to a green check mark? This means we are done with that step. If you change your mind or need to make changes, simply click on the button to go back to that step. Try it!
  >
  > **Figure 22** - Click on the buttons to go back to that step
  >
  > ![Click on the buttons to back to that step](images/i4e_expressconfiguration_choosebuttontogoback.png)

7. In the **Choose apps** screen, you will see a selection of Web apps, Microsoft Store apps, and desktop (Win32) apps. You will also see a list of popular apps from each category. 

  - Add or remove apps by clicking on them. A blue checkmark means the app is added and will be installed for all members of the group selected in the **Choose group** step.
  
    In this walkthrough, it's up to you to select the apps you choose to install. Just remember what they are so that later in the walkthrough you can verify that the apps were installed correctly on the device.

    > [!TIP]
    > Web apps are pushed as links in the Windows Start menu under **All apps**. If you want apps to appear in Microsoft Edge browser tabs, use the **Homepages** setting for Microsoft Edge through **Express configuration** or **Manage Users and Devices**.

  **Figure 23** - Choose the apps that you want to install for the group

  ![Choose apps to install for the group](images/i4e_expressconfiguration_chooseapps_selected_cropped.png)

8. When you're done choosing apps, click **Next** at the bottom of the screen.

  If you select Microsoft Store apps, you will see a notification that Intune for Education is getting these apps.

8. In the **Choose settings** screen, we will set the settings to apply to the group. Click the reverse caret (downward-facing arrow) to expand the settings group and get more information about each setting in that settings group.

  **Figure 24** - Expand the settings group to get more details

  ![Expand the settings group to get more info](images/i4e_expressconfiguration_choosesettings_expandcollapse_cropped.png)

9. For this walkthrough, set the following settings:
  - In the **Internet browser settings** group, change the **Send Do Not Track requests to help protect users' privacy** setting to **Block**.
  - In the **App settings** group, change the **Microsoft Store for Business apps** setting to **Block**, and then set the **Private Microsoft Store for Business apps** to **Allow**.

  **Figure 25** - Set some additional settings

  ![Set some additional settings](images/i4e_expressconfiguration_choosesettings_additionalsettingsconfigured_cropped.png)

10. Click **Next**. In the **Review** screen, you will see a summary of the apps and settings you selected to apply.

  **Figure 26** - Review the group, apps, and settings you configured

  ![Review the group, apps, and settings you configured](images/i4e_expressconfiguration_review.png)

11. Click **Save** to end express configuration.
12. You will see the **You're done!** screen which lets you choose one of two options. 

  **Figure 27** - All done with Intune for Education express configuration

  ![Done with Intune for Education express configuration](images/i4e_expressconfiguration_alldone.png)

13. Click **All done** or click the **X** on the upper-right corner of the screen to dismiss this screen and go back to the dashboard.


**<a name="addappsfrommsfe"></a>Add apps bought from Microsoft Store for Education**

- **Example 1 - Minecraft: Education Edition**

  If you would like to purchase Minecraft: Education Edition or want to learn more about volume licensing, see <a href="https://technet.microsoft.com/en-us/edu/windows/school-get-minecraft" target="_blank">For IT administrators - get Minecraft: Education Edition</a>.

- **Example 2 - Free educational/reference apps**

  1. In the <a href="https://intuneeducation.portal.azure.com/" target="_blank">Intune for Education console</a>, click **Apps** from the menu on the left.

    **Figure 28** - Click on **Apps** to see the list of apps for your tenant

    ![Click Apps to see the list of apps for your tenant](images/i4e_dashboard_clickapps.png)

  2. In the **Store apps** section, click **+ New app**. This will take you to the Microsoft Store for Education portal and you will already be signed in.

    **Figure 29** - Select the option to add a new Store app

    ![Select the option to add a new Store app](images/i4e_apps_newstoreapp_selected.png)

  3. In the Microsoft Store page, check some of the categories for suggested apps or search the Store for a free educational or reference app. Find ones that you haven't already installed during express setup for Intune for Education.
  
    For example, these apps are free:
    - Duolingo - Learn Languages for Free
    - Flashcards Pro 
    - Khan Academy
    - My Study Life

  4. Find or select the app you want to install and click **Get the app**.
  5. In the app's Store page, click the **...** button and select **Add to private store**.
  6. Repeat steps 3-5 to install another app or move to the next step.
  7. In the Microsoft Store for Education portal, select **Manage > Apps & software > Manage apps** to verify that the apps you purchased appear in your inventory.

    For example, if you bought Duolingo and Khan Academy, they will show up in your inventory along with the apps that Microsoft automatically provisioned for your education tenant.

    **Figure 30** - Apps inventory in Microsoft Store for Education

    ![Apps inventory in Store for Business](images/msfe_manageapps_inventory_grouped.png)

    In the **Private store** column of the **Apps & software** page, the status for some apps will indicate that it's "In private store" while others will say "Not in private store". We won't go over this in the walkthrough, but you can learn more about this in [Distribute apps using your private store](https://technet.microsoft.com/en-us/itpro/windows/manage/distribute-apps-from-your-private-store).

    > [!NOTE]  
    > You'll see in the above screenshot that some apps say that **Add is in progress**. Sync happens automatically, but it may take up to 24 hours for your organization's private store and 12 hours for Intune for Education to sync all your purchased apps. 

**<a name="installappsallusers"></a>Install apps for all users**

Now that you've bought the apps, use Intune for Education to specify the group to install the apps for. Here, we'll show you how to install the apps you bought for all devices used by all users in your tenant. 

1. In the <a href="https://intuneeducation.portal.azure.com/" target="_blank">Intune for Education console</a>, click the **Groups** option from the menu on the left.

  **Figure 31** - Groups page in Intune for Education

  ![Groups page in Intune for Education](images/i4e_groupspage.png)

2. In the **Groups** page, select **All Users** from the list of groups on the left, and then click **Users** in the taskbar at the top of the **All Users** page. 

  **Figure 32** - List of all users in the tenant

  ![List of all users in the tenant](images/i4e_groups_allusers_users_steps.png)

3. In the taskbar at the top, select **Apps** and then click **Edit apps** to see a list of available apps.

  **Figure 33** - Edit apps to assign them to users

  ![Edit apps to assign them to users](images/i4e_groups_allusers_appspage_editapps.png)

4. Select the apps to deploy to the group. A blue checkmark will appear next to the apps you select. 

  **Figure 34** - Select the apps to deploy to the group

  ![Select the apps to deploy to the group](images/i4e_groups_allusers_selectappstodeploy.png)

5. Once you're done, click **Save** at the bottom of the page to deploy the selected apps to the group.
6. You'll be notified that app assignments are being updated. The updated **All Users** groups page now include the apps you selected. 

  **Figure 35** - Updated list of assigned apps

  ![Updated list of assigned apps](images/i4e_groups_allusers_updatedappslist.png)

You're now done assigning apps to all users in your tenant. It's time to set up your Windows 10 device(s) and check that your cloud infrastructure is correctly set up and your apps are being pushed to your devices from the cloud.

## 6. Set up Windows 10 devices

### 6.1 Set up devices using Set up School PCs or Windows OOBE
We recommend using the latest build of Windows 10, version 1703 on your education devices. To set up new Windows 10 devices and enroll them to your education tenant, choose from one of these options:
- **Option 1: [Use the Set up School PCs app](#usesetupschoolpcs)** - You can use the app to create a setup file that you can use to quickly set up one or more Windows 10 devices.
- **Option 2: [Go through Windows OOBE and join the device to Azure AD](#usewindowsoobandjoinaad)** - You can go through a typical Windows 10 device setup or first-run experience to configure your device.

**<a name="usesetupschoolpcs"></a>Option 1: Set up a device using the Set up School PCs app**
IT administrators and technical teachers can use the Set up School PCs app to quickly set up PCs for students. A student PC set up using the app is tailored to provide students with the tools they need for learning while removing apps and features that they don't need.

![Set up School PCs app](images/suspc_getstarted_050817.png)

Set up School PCs makes it easy to set up Windows 10 PCs with Microsoft's recommended education settings, using a quick USB setup. This app guides you through the creation of a student PC provisioning package and helps you save it to a USB drive. From there, just plug the USB drive into student PCs running Windows 10 Creators Update (version 1703). It automatically:
- Joins each student PC to your organization's Office 365 and Azure Active Directory tenant
- Enrolls each student PC into a mobile device management (MDM) provider, like Intune for Education, if licensed in your tenant. You can manage all the settings Set up School PCs sets later through MDM.
- Removes OEM preinstalled software from each student PC
- Auto-configures and saves a wireless network profile on each student PC
- Gives a friendly and unique name to each student device for future management
- Sets Microsoft-recommended school PC settings, including shared PC mode which provides faster sign-in and automatic account cleanup
- Enables optional guest account for younger students, lost passwords, or visitors
- Enables optional secure testing account
- Locks down the student PC to prevent mischievous activity:
    * Prevents students from removing the PC from the school's device management system
    * Prevents students from removing the Set up School PCs settings
- Keeps student PCs up-to-date without interfering with class time using Windows Update and maintenance hours
- Customizes the Start layout with Office
- Installs OneDrive for storing cloud-based documents and Sway for creating interactive reports, presentations, and more
- Uninstalls apps not specific to education, such as Solitaire
- Prevents students from adding personal Microsoft accounts to the PC

**To set up a device using the Set up School PCs app**

1. Follow the steps in [Use the Set up School PCs app](https://docs.microsoft.com/en-us/education/windows/use-set-up-school-pcs-app) to quickly set up one or more student PCs.
2. Follow the steps in [5.2 Verify correct device setup](#52-verify-correct-device-setup).


**<a name="usewindowsoobandjoinaad"></a>Option 2: Set up a device using Windows OOBE**

1. If you don't have a Wi-Fi network configured, make sure you connect the device to the Internet through a wired or Ethernet connection.
2. Go through the Windows device setup experience. On a new or reset device, this starts with the **Let's start with region. Is this right?** screen.

  **Figure 36** - Let's start with region

  ![Let's start with region](images/win10_letsstartwithregion.png)

3. Continue with setup. In the **How would you like to set up?** screen, select **Set up for an organization**.

  **Figure 37** - Select setup for an organization

  ![Select setup for an organization](images/win10_setupforanorg.png)

4. Sign in using the user's account and password. Depending on the user password setting, you may be prompted to update the password.
5. Choose privacy settings for the device. Location, speech recognition, diagnostics, and other settings are all on by default. Configure the settings based on the school's policies. 
6. Click **Accept** to go through the rest of device setup.


### 6.2 Verify correct device setup
Verify that the device is set up correctly and boots without any issues.

**Verify that the device was set up correctly**
1. Confirm that the Start menu contains a simple configuration.
2. Confirm that the Store and built-in apps are installed and working. The apps pushed down from Intune for Education will appear under **Recently added**. 

  > [!NOTE]  
  > It may take some time before some apps are pushed down to your device from Intune for Education. Check again later if you don't see some of the apps you provisioned for the user.

  **Figure 38** - Sample list of apps for a user

  ![Apps list contains the apps provisioned for the user](images/win10_start_checkapps.png)

### 6.3 Verify the device is Azure AD joined
Let's now verify that the device is joined to your organization's Azure AD and shows up as being managed in Microsoft Intune for Education.

**Verify if the device is joined to Azure AD**
1. Log in to the <a href="https://intuneeducation.portal.azure.com/" target="_blank">Intune for Education console</a>.
2. Select **Groups** and select **All Devices**.
3. In the **All Devices** page, see the list of devices and verify that the device you're signed into appears on the list.

  **Figure 39** - List of all managed devices

  ![Verify that the device is managed in Intune for Education](images/i4e_groups_alldevices_listofaadjdevices.png)

4. On the Windows 10 education device, click **Start** and go to **Settings**. 
5. Select **Accounts > Access work or school**.
6. In the **Access work or school** page, confirm that the device is connected to the organization's Azure AD.

  **Figure 40** - Confirm that the Windows 10 device is joined to Azure AD

  ![Confirm that the Windows 10 device is joined to Azure AD](images/win10_confirmaadj.png)

**That's it! You're done!** You've completed basic cloud setup, deployment, and management using Microsoft Education. You can continue follow the rest of the walkthrough to finish setup and complete other tasks.


## 7. Finish setup and other tasks

### 7.1 Update group settings in Intune for Education
If you need to make changes or updates to any of the apps or settings for the group(s), follow these steps.

1. Log in to the <a href="https://intuneeducation.portal.azure.com/" target="_blank">Intune for Education console</a>.
2. Click **Groups** and then choose **Settings** in the taskbar at the top of the page.
3. You will see the same settings groups that you saw in express setup for Intune for Education as well as other settings categories such as **Windows Defender settings**, **Device sharing**, **Edition upgrade**, and so on.

  **Figure 41** - See the list of available settings in Intune for Education

  ![See the list of available settings in Intune for Education](images/i4e_groups_settingslist_full.png)

4. Keep the default settings or configure the settings according to your school's policies. 

  For example, you can configure the diagnostic data sent to Microsoft in **Basic device settings > Send diagnostic data**. 

5. Click **Save** or **Discard changes**.

### 7.2 Configure Azure settings
After completing the basic setup for your cloud infrastructure and confirming that it is up and running, it's time to prepare for additional devices to be added and enable capabilities for the user to use.

#### Enable many devices to be added by a single person 
When a device is owned by the school, you may need to have a single persion adding many devices to your cloud infrastructure. 

Follow the steps in this section to enable a single person to add many devices to your cloud infrastructure.

1. Sign in to the <a href="https://portal.office.com" target="_blank">Office 365 admin center</a>.
2. Click **Admin centers** and select **Azure AD** to go to the Azure portal.
3. Configure the device settings for the school's Active Directory. From the new Azure portal, <a href="https://portal.azure.com" target="_blank">https://portal.azure.com</a>, select **Azure Active Directory > Users and groups > Device settings**.

  **Figure 42** - Device settings in the new Azure portal

  ![Configure device settings in the new Azure portal](images/azure_newportal_usersandgroups_devicesettings.png)

4. Find the setting **Maximum number of devices per user** and change the value to **Unlimited**.
5. Click **Save** to update device settings.

#### Enable roaming settings for users
When students move from using one device to another, they may need to have their settings roam with them and be made available on other devices. 

Follow the steps in this section to ensure that settings for the each user follow them when they move from one device to another.

1. Sign in to the <a href="https://portal.office.com" target="_blank">Office 365 admin center</a>.
2. Click **Admin centers** and select **Azure AD** to go to the Azure portal.
3. Configure the device settings for the school's Active Directory. From the new Azure portal, <a href="https://portal.azure.com" target="_blank">https://portal.azure.com</a>, select **Azure Active Directory > Users and groups > Device settings**.
4. Find the setting **Users may sync settings and enterprise app data** and change the value to **All**.

  **Figure 43** - Enable settings to roam with users

  ![Enable settings to roam with users](images/azure_usersandgroups_devicesettings_ers.png)

5. Click **Save** to update device settings.

### 7.3 Complete Office 365 for Education setup
Now that your basic cloud infrastructure is up and running, it's time to complete the rest of the Office 365 for Education setup. You can find detailed information about completing Office 365 setup, services and applications, troubleshooting, and more by reading the <a href="https://support.office.com/en-US/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa#ID0EAAAABAAA=Education" target="_blank">Office 365 admin documentation</a>.

### 7.4 Add more users
After your cloud infrastructure is set up and you have a device management strategy in place, you may need to add more users and you want the same policies to apply to these users. You can add new users to your tenant simply by adding them to the Office 365 groups. Adding new users to Office 365 groups automatically adds them to the corresponding groups in Intune for Education.

See <a href="https://support.office.com/en-us/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc" target="_blank">Add users to Office 365</a> to learn more. Once you're done adding new users, go to the <a href="https://intuneeducation.portal.azure.com/" target="_blank">Intune for Education console</a> and verify that the same users were added to the Intune for Education groups as well.

### 7.5 Connect other devices to your cloud infrastructure
Adding a new device to your cloud-based tenant is easy. For new devices, you can follow the steps in [6. Set up Windows 10 devices](#6-set-up-windows-10-devices). For other devices, such as those personally-owned by teachers who need to connect to the school network to access work or school resources (BYOD), you can follow the steps in this section to get these devices connected.

  > [!NOTE]  
  > These steps enable users to get access to the organization's resources, but it also gives the organization some control over the device.

**To connect a personal device to your work or school**

1. On your Windows device, go to **Settings > Accounts**.
2. Select **Access work or school** and then click **Connect** in the **Connect to work or school** page.
3. In the **Set up a work or school account** window, enter the user's account info.

  For example, if a teacher connects their personal device to the school network, they'll see the following screen after typing in their account information.

  **Figure 44** - Device is now managed by Intune for Education

  ![Device is managed by Intune for Education](images/byob_aad_enrollment_intune.png)

4. Enter the account password and then click **Sign in** to authenticate the user.

   Depending on the organization's policy, the user may be asked to update the password.

5. After the user's credentails are validated, the window will refresh and will now include an entry that shows the device is now connected to the organization's MDM. This means the device is now enrolled in Intune for Education MDM and the account should have access to the organization's resources.

  **Figure 45** - Device is connected to organization's MDM

  ![Device is connected to organization's MDM](images/win10_connectedtoorgmdm.png)

6. You can confirm that the new device and user are showing up as Intune for Education-managed by going to the Intune for Education management portal and following the steps in [6.3 Verify the device is Azure AD joined](#63-verify-the-device-is-azure-ad-joined). 

  It may take several minutes before the new device shows up so check again later.


## Get more info

### For IT admins
To learn more about the services and tools mentioned in this walkthrough, and learn what other tasks you can do, follow these links:
- <a href="https://technet.microsoft.com/en-us/edu/windows/education-scenarios-store-for-business" target="_blank">Working with Store for Business - education scenarios</a>
- *Resources for anyone who uses Office 365* and *Resources for admins* in <a href="https://support.office.com/en-US/article/Get-started-with-Office-365-Education-AB02ABE5-A1EE-458C-B749-5B44416CCF14" target="_blank">Get started with Office 365 for Education</a>
- School Data Sync
  - Deployment using CSV files: <a href="https://aka.ms/sdscsv" target="_blank">How to deploy School Data Sync by using CSV files</a> and <a href="https://aka.ms/sdscsvattributes" target="_blank">CSV files for School Data Sync</a>
  - Deployment using PowerSchool Sync: <a href="https://aka.ms/sdspowerschool" target="_blank">How to deploy School Data Sync by using PowerSchool Sync</a> and <a href="https://aka.ms/sdspowerschoolattributes" target="_blank">School Data Sync required attributes for PowerSchool Sync</a>
  - Deployment using Clever Sync: <a href="https://aka.ms/sdsclever" target="_blank">How to deploy School Data Sync by using Clever Sync</a> and <a href="https://aka.ms/sdscleverattributes" target="_blank">School Data Sync required attributes for Clever sync</a>
  - Deployment using OneRoster CSV files: <a href="https://aka.ms/sdsoneroster" target="_blank">How to deploy School Data Sync by using OneRoster CSV files</a>

### For teachers
Whether it's in the classroom, getting the most out of your devices, or learning some of the cool things you can do, we've got teachers covered. Follow these links for more info:
- [Microsoft Educator Community](https://education.microsoft.com/)
- *Resources for anyone who uses Office 365* in <a href="https://support.office.com/en-US/article/Get-started-with-Office-365-Education-AB02ABE5-A1EE-458C-B749-5B44416CCF14" target="_blank">Get started with Office 365 for Education</a>
- <a href="https://education.microsoft.com/windows-10-online-resources-for-teachers" target="_blank">Windows 10 online resources for teachers</a>

### For students
If you're a student, follow these links to get find out what resources and services are available to you:
- <a href="https://www.microsoft.com/en-us/education/students/resources/default.aspx" target="_blank">Student resources</a>

## Related topics

Microsoft Education documentation and resources
<!-- add missing link here -->