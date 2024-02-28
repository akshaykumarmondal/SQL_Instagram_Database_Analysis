
# Instagram Database Clone Analysis

## Project Overview
I have created an Instagram dummy database clone, incorporating various tables such as followers, followees, tags, likes, photos, and users. After populating the database with relevant data, the goal is to answer key questions that can provide insights into the platform's user behavior and preferences.

## Technologies Used
- MySQL

## Database Schema
Users Table
| Column    | Data Type           | Constraints                 |
|-----------|---------------------|-----------------------------|
| id        | INTEGER             | AUTO_INCREMENT, PRIMARY KEY |
| username  | VARCHAR(100)        | UNIQUE, NOT NULL            |
| created_at| TIMESTAMP           | DEFAULT NOW()               |

Photos Table
| Column      | Data Type           | Constraints                        |
|-------------|---------------------|------------------------------------|
| id          | INTEGER             | AUTO_INCREMENT, PRIMARY KEY        |
| image_url   | VARCHAR(100)        | UNIQUE, NOT NULL                   |
| user_id     | INTEGER             | NOT NULL, FOREIGN KEY (Users.id)   |
| created_at  | TIMESTAMP           | DEFAULT NOW()                      |

Comments Table
| Column        | Data Type           | Constraints                            |
|---------------|---------------------|----------------------------------------|
| id            | INTEGER             | AUTO_INCREMENT, PRIMARY KEY            |
| comment_text  | VARCHAR(255)        | NOT NULL                               |
| photo_id      | INTEGER             | NOT NULL, FOREIGN KEY (Photos.id)      |
| created_at    | TIMESTAMP           | DEFAULT NOW()                          |
| user_id       | INTEGER             | NOT NULL, FOREIGN KEY (Users.id)       |

Likes Table
| Column      | Data Type           | Constraints                        |
|-------------|---------------------|------------------------------------|
| user_id     | INTEGER             | NOT NULL, FOREIGN KEY (Users.id)   |
| photo_id    | INTEGER             | NOT NULL, FOREIGN KEY (Photos.id)  |
| created_at  | TIMESTAMP           | DEFAULT NOW()                      |

Follows Table
| Column         | Data Type           | Constraints                            |
|----------------|---------------------|----------------------------------------|
| follower_id    | INTEGER             | NOT NULL, FOREIGN KEY (Users.id)       |
| followee_id    | INTEGER             | NOT NULL, FOREIGN KEY (Users.id)       |
| created_at     | TIMESTAMP           | DEFAULT NOW()                          |
| PRIMARY KEY    | (follower_id, followee_id) |                                     |

Tags Table
| Column      | Data Type           | Constraints                        |
|-------------|---------------------|------------------------------------|
| id          | INTEGER             | AUTO_INCREMENT, PRIMARY KEY        |
| tag_name    | VARCHAR(100)        | UNIQUE                             |
| created_at  | TIMESTAMP           | DEFAULT NOW()                      |

Photo Tags Table
| Column      | Data Type           | Constraints                             |
|-------------|---------------------|-----------------------------------------|
| photo_id    | INTEGER             | NOT NULL, FOREIGN KEY (Photos.id)       |
| tag_id      | INTEGER             | NOT NULL, FOREIGN KEY (Tags.id)         |
| PRIMARY KEY | (photo_id, tag_id)   |                                         |


## How to Use

### Setting Up the Database

1. Ensure you have MySQL installed on your system.
2. Copy the SQL code for creating tables provided in the README.
3. Execute the SQL code in your MySQL database to create the necessary tables.

### Inserting Dummy Data

1. Use the appropriate `INSERT` statements to add dummy data to each table.
2. Populate the tables with sample users, photos, comments, likes, follows, tags, and photo-tag associations.

### Querying the Database

1. Leverage the structured schema to run SQL queries and analytics on the data.
2. Explore relationships between tables to extract meaningful insights.
3. Utilize JOIN operations to combine information from multiple tables.

## CASE STUDY Questions to Know More About the Customers

### 1. Longest-Tenured Users
- **We want to reward our users who have been around the longest. Find the 5 oldest users.**

### 2. User Registration Patterns
- **What day of the week do most users register on? We need to figure out when to schedule an ad campaign.**

### 3. Targeting Inactive Users
- **We want to target our inactive users with our email campaign. Find the users who have never posted a photo.**

### 4. Photo Contest Winner
- **We are running a new contest to see who can get more likes on a single photo. Who won?**

### 5. User Posting Frequency
- **Our investors want to know how many times does the average user post?**

### 6. Brand Hashtags
- **A brand wants to know which hashtags to use in a post. What are the top 5 commonly used hashtags?**

### 7. Identifying Bots
- **We have a small problem with bots on our site. Find users who have liked every single photo on the site.**


## Contact 
- Feel free to reach on [Linkedin](https://www.linkedin.com/in/akshay-kumar-mondal-%F0%9F%87%AE%F0%9F%87%B3-b8aba720a/)




