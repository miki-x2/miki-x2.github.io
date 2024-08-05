---
layout: project
type: project
image: img/uhm-digital-bulletin-board-logo.png
title: "UHM Digital Bulletin Board"
date: 2024
published: true
labels:
  - Swift
  - iOS Application 
  - GitHub
  - XCode
summary: "The UHM Digital Bulletin Board is a digital bulletin board iOS application that allows users to share and view campus-related information. The goal of this project was to improve campus-wide engagement by making information more accessible and reducing the inconvenience of using a physical bulletin board."
---
## UHM Digital Bulletin Board
On the University of Hawaii at Manoa campus, there are multiple traditional bulletin boards filled with campus-related information, such as upcoming events, advertisements of student organizations, or campus services. However, they are often crowded with flyers, making them unappealing and difficult for people to navigate. The main objective of this project was to allow users to conveniently advertise and find out about upcoming events or available services.

## Design and Features
The final design of the application consisted of a simple UI with complex features. When the application is first installed on a device, the login view is shown. Pre-existing users can use their credentials when they register to log in. New users can press the “Create an Account” link at the bottom of the page, which takes them to the register view to create an account.

<p align="center">
  <img width="300px" src="../img/uhm-digital-bulletin-board-login.png">
</p>

After logging into the application or creating a new account, the user can access the home page, where all the announcements are displayed as a list. There are three tabs on the bottom to access the home page, map view, and profile page.

<p align="center">
  <img width="300px" src="../img/uhm-digital-bulletin-board-home.png">
</p>

A new announcement can be made by pressing the plus button on the top right corner of the home screen. When this button is pressed, a form is displayed. To create a post, a title, description, location, and date must be entered. All fields are required and the date must be today or newer, otherwise an error message will appear.

<p align="center">
  <img src="../img/uhm-digital-bulletin-board-newpost.png" width="150px" />
  <img src="../img/uhm-digital-bulletin-board-error.png" width="150px" />
</p>


There are two methods the location can be entered when creating a new announcement post. One way is by selecting the “Select a Location” button, which allows the user to zoom into a map and select any location by tapping. The second method is by selecting the “Select Current Location” button, which allows the user to associate their current location with the announcement post.

<p align="center">
  <img src="../img/uhm-digital-bulletin-board-method1.png" width="150px" />
  <img src="../img/uhm-digital-bulletin-board-method2.png" width="150px" />
</p>

For both methods, the location name is displayed in the form after the user confirms their selection. This allows the user to check that their selected location is correct.

<p align="center">
  <img width="300px" src="../img/uhm-digital-bulletin-board-confirm.png">
</p>

Once a valid announcement post has been created and saved, it gets displayed on the home. The posts are displayed as a list with the title, date, location, and description visible. The post can be deleted at any time with a simple swipe.

<p align="center">
  <img width="300px" src="../img/uhm-digital-bulletin-board-list.png">
</p>

The middle tab, “Map” is a map view that displays the events that are associated with every announcement post that has been made. Each location is pinned with the announcement title for a convenient view. If an announcement is taken down, the pin on the map view is also removed and will no longer be visible.

<p align="center">
  <img width="300px" src="../img/uhm-digital-bulletin-board-map.png">
</p>

The final tab is the profile view, which is a simple page that displays the user information such as the date they joined, their full name, and email address. From this page, users can log out, which takes users back to the login or landing page.

<p align="center">
  <img width="300px" src="../img/uhm-digital-bulletin-board-profile.png">
</p>

## Backend Design
The backend design utilized the Firebase application development service for the database and user authentication. The Firebase service is integrated in such a way that when an account is created, the information associated with the account such as the user’s full name, email address, and the date the account was created, is stored as a collection of users in the database. For each user, there is an association with another collection of items, which are the announcements. The information stored in the database for each announcement includes the date the announcement was created, description, title, a boolean that represents whether the announcement was marked as done or not, latitude and longitude of the location, and location as a string. Upon the successful creation and registration of an account and announcement, a unique identification is assigned to the user and the announcement post.

<p align="center">
  <img width="500px" src="../img/firebase1.png">
</p>
<p align="center">
  <img width="500px" src="../img/firebase2.png">
</p>

