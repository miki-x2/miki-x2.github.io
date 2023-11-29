---
layout: essay
type: essay
title: "Recipes to Good Code"
# All dates must be YYYY-MM-DD format!
date: 2023-11-29
published: true
labels:
  - Software Engineering
  - Design Patterns
---
<p align="center">
  <img width="280px" src="../img/cooking.webp"/>
</p>


# The Secret to Cooking Up Good Code
One of my hobbies outside of school is cooking. According to the Myers-Briggs Type Indicator (MBTI), my personality type prefers predictability over intuition and spontaneity. As a result, I prefer following standard cooking patterns and instructions listed in recipes over doing whatever I want at that moment. Design patterns in software engineering are like recipes, providing proven solutions that act as guidance on how to tackle common problems. Similar to how following a recipe yields a successful dish, utilizing design patterns helps developers create consistent and efficient code that consists of best practices in software engineering. 

Whether you are Gordon Ramsay or a software engineering student cooking up a dish for dinner, recipes exist for a reason: To streamline the cooking process and ensure consistency in every dish that is created. Surely, cooking without a recipe is possible. However, there is no guarantee that the dish will taste or even look the same every time. If something goes wrong during the cooking process, it will be difficult for other people of chefs to help if you are inconsistently freestyling. Similarly, coding without following a certain design pattern is certainly not impossible, but with compromised tidiness and inconsistency in code. This results in difficulties for other developers to understand, collaborate, or even assist in achieving the desired outcome. To avoid such conflict, developers of all levels often turn to design patterns to confront challenges in software development, from handling communication between various components to managing code flow. 


# Recipes I Swear By
<p align="center">
  <img width="300px" src="../img/singleton.png"/>
</p>

One of the most commonly used design patterns in software engineering is the Singleton pattern. The Singleton pattern restricts the instantiation of a class while providing a global access point to that instance. I use this pattern the most, especially in my final group project for ICS 314, [UHM Clubhouse](https://github.com/uhm-clubhouse/uhm-clubhouse). The UHM Clubhouse is a website that allows students to browse a directory of all current student clubs with information such as a brief description and contact information. In this project, the Singleton pattern is used for various collections to be exported, so that they can be used throughout the entire project. One example from our code is the ClubsInterestsCollection, which is a collection that holds the interests associated with each club. Here, the Singleton pattern is implemented as the ClubsInterest variable is exported and is an instance of the ClubsInterestsCollection class. Instances of this class cannot be created outside of the module unless it is imported. 

```
import { Mongo } from 'meteor/mongo';
import SimpleSchema from 'simpl-schema';

/** Encapsulates state and variable values for this collection. */
class ClubsInterestsCollection {
  constructor() {
    // The name of this collection.
    this.name = 'ClubsInterestsCollection';
    // Define the Mongo collection.
    this.collection = new Mongo.Collection(this.name);
    // Define the structure of each document in the collection.
    this.schema = new SimpleSchema({
      club: String,
      interest: String,
    });
    // Ensure collection documents obey schema.
    this.collection.attachSchema(this.schema);
    // Define names for publications and subscriptions
    this.userPublicationName = `${this.name}.publication.user`;
    this.adminPublicationName = `${this.name}.publication.admin`;
  }
}

export const ClubsInterests = new ClubsInterestsCollection();
```

# Final Comments
Looking back at some of my code, I realized that design patterns are what enabled my projects to be consistent and efficient, allowing me to manage databases and make modifications for improvements. Design patterns in software engineering are the backbone of a well-structured, efficient code, just like the recipes and cookbooks that cannot be disposed of, no matter how old and dirty they become. When I face a challenge where I am unsure of what the best solution is, design patterns help me find the best approach to software development. As I progress in my software engineering development journey, I will continue to reference my recipes to find the best design pattern while picking up new recipes that will help me craft the best code I can program. 
