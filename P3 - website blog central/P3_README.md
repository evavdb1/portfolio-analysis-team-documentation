==========  Blog Central  ==========

A full-featured blog built using Spring Boot & Spring Security (JWT).
A REST API where users can create blogposts, comment, like posts, and manage their profiles.  


***** PLAYERS *****
This website is developed as a group project.

Tamara: Scrum Master
Chaïma: Project Owner
Viktoriia: Developer
Eva: Developer


***** TECH INFO *****
Java 17+
Spring Boot
Spring Security (JWT, stateless)
Spring Data JPA / Hibernate
MySQL
Maven
Postman (API testing)


***** SECURITY *****
Stateless authentication using JWT
Passwords encrypted with BCrypt
Roles: USER, ADMIN
Authorization enforced at endpoint level
JWT contains username only (roles resolved from DB)


***** ANALYSE *****
Class diagram available in /documentation/analyse
Flow chart available in /documentation/analyse
Sequence diagrams available in /documentation/analyse


***** FEATURES *****
USER
Register a new user
Login and receive JWT
View own profile
Update own profile
Delete own account

BLOG POST
Create a blog post (authenticated)
View all blog posts (public, paginated)
View single blog post with embedded comments
Update blog post (author only)
Delete blog post (author only)
Like a blog post (authenticated)

COMMENT
Add comment to a blog post (authenticated)
Edit own comment
Delete own comment
Blog post author may moderate (delete) comments
Comments are embedded in blog post responses

SEARCH
Global search across: Blog posts, Users, Case-insensitive, Paginated results

STATISTICS
Online users (JWT-based)
Total visitors (unique logins since startup)


***** ENDPOINTS *****
Postman collection available in /documentation/postman

USER
v POST   /api/users/register
v POST   /api/auth/login
v GET    /api/users/{id}
v PUT    /api/users/{id}
v DELETE /api/users/{id}

BLOGPOST
v GET    /api/blogposts
v GET    /api/blogposts/{postId}
v POST   /api/blogposts
v PUT    /api/blogposts/{postId}
v DELETE /api/blogposts/{postId}
v POST   /api/blogposts/{postId}/like

COMMENTS
v POST   /api/blogposts/{postId}/comments
v PUT    /api/comments/{commentId}
v DELETE /api/comments/{commentId}

SEARCH
v GET    /api/search?x=keyword

STATISTICS
v GET    /api/stats/online
v GET    /api/stats/visitors


***** TESTING *****
All endpoints tested using Postman
JWT token must be added as <Authorization: Bearer <token>>


***** DATABASE *****
MySQL
JPA entities: User, BlogPost, Comment
Relationships managed via JPA/Hibernate
Cascading configured where appropriate


***** PROJECT STRUCTURE *****
BlogCentralProject
├── documentation
│   ├── analyse
│   └── postman
├── src
│   ├── main
│   │   ├── java
│   │   │   └── org.intecbrussel
│   │   │       ├── BlogCentralProjectApplication.java
│   │   │       ├── controller
│   │   │       ├── service
│   │   │       ├── repository
│   │   │       ├── model
│   │   │       ├── dto
│   │   │       ├── security
│   │   │       ├── exception
│   │   │       ├── mapper
│   │   │       └── stats
│   │   └── resources
│   │       └── application.properties
│   └── test
│       └── java
│           └── org.intecbrussel
└── pom.xml


***** ASSIGNMENT *****
checklist in directory documentation

v Full CRUD
v JWT security
v Ownership authorization
v Nested resources
v Pagination & sorting
v Search
v Statistics
v Postman-verifiable flows


***** FRONTEND *****
