# FoodLooks
FoodLooks is an recipe app that can browse options for food.
# Group 5 

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
1. [Schema](#Schema)

## Overview
### Description
FoodLooks Allow indviduals to find a browse food recipies. 

- **Category:** Social Networking / Food
- **Mobile:** This app would be primarily developed for mobile but would perhaps be just as viable on a computer, such as tinder or other similar apps. Functionality wouldn't be limited to mobile devices, however mobile version could potentially have more features.
- **Story:** Analyzes users food choices, and connects them to other users with similar choices. The user can search for a particular item to eat or creat anf the searches becomes avalibale to them. 
- **Market:** Any individual could choose to use this app, and to keep it a safe environment, people would be organized into age groups.
- **Habit:** This app could be used as often or unoften as the user wanted depending on what exactly they're looking for.
- **Scope:** First we would start with displaying recipies and adding our own it could advance to a broader version of a facebook verion of food. 
. User Stories (Required and Optional)




2. Screen Archetypes
*Login
*Register - User signs up or logs into their account
...
*Compose Screen 
*Camera allows user to take photo of food and and recipe or discription of the food.

*Profile Screen
*Allows user to upload recipies , along with pictures.
...
*Explore Screen - Allow you to explore for diffrent recipies. 
...
*Feed Screen - Allow users to see diffrent recipies from users




**Tab Navigation** (Tab to Screen)

* Feed Screen
* Profile
* Explore
* Compose 

**Flow Navigation** (Screen to Screen)
* Forced Log-in -> Account creation if no log in is available
* Compose  ->  Take Photo and enter description
* Explore -> Browse Recipies 





## Schema 
### Models
#### Post

   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | objectId      | String   | unique id for the user post (default field) |
   | image         | File     | image that user posts |
   | caption       | String   | image caption by author |
   

### Networking
#### List of network requests by screen
      <<<<<<< patch-1
   - Home screen
      - (Read/GET) Query recipes 
    
                =======
   - Home recipe Screen
      - (Read/GET) Query all posts where user is author
                >>>>>>> main
         ```swift
         let query = PFQuery(className:"Post")
         query.whereKey("author", equalTo: currentUser)
         query.order(byDescending: "createdAt")
         query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
            if let error = error { 
               print(error.localizedDescription)
    <<<<<<< patch-1
           // TODO: Do something with posts...
            }
         }
         ```
      - (Create/POST) Create a new comment on a post
      - (Delete) Delete existing comment
   - Create Post Screen
      - (Create/POST) Create a new post object
   - Profile Screen
      - (Read/GET) Query logged in user object
      - (Update/PUT) Update user profile image
=======
            } else if let posts = posts {
               print("Successfully retrieved \(posts.count) posts.")
           
            }
         }
         ```
      - (Create/POST) Create a new like on a post
      - (Delete) Delete existing like
      - (Create/POST) Create a new comment on a post
      - (Delete) Delete existing comment
>>>>>>> main







Flow Navigation (Screen to Screen)

Forced Log-in -> Account creation if no log in is available
FeedScreen -> See recipe content
Profile -> Text field to be modified.
 




gif 
*********


