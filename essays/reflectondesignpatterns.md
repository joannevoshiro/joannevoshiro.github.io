---
layout: essay
type: essay
title: "Serving Up Code with Design Patterns"
# All dates must be YYYY-MM-DD format!
date: 2024-12-05
published: true
labels:
  - Software Engineering
  - Learning
---
## Design Patterns: What are they?
Design patterns are reusable solutions to common problems that are often encountered in software engineering. These patterns provide a structured approach to solving recurring challenges and promotes a code that is more maintainable, scalable, and efficient. Creational Patterns, Structural Patterns, and Behavioral Patterns are all examples of types of patterns for Object Oriented Design. Some of the most common design patterns are Singleton, Factory Method, Observer, and MVC. MVC (Model-View-Controller) is an example of a design pattern that was used in our final project: UHM Marketplace. The review page is an example of how user inputs are taken and processed through a database and displayed back out onto the user interface for users to view. <br>
![](/img/reviews.png)
![](/img/reviewsform.png)

## Understanding how it works
We can look at the MVC design pattern like a restaurant; three separate jobs of the restaurant represent three different jobs of this pattern. The Model *((M)VC)* can be represented as the kitchen, where the core work happens; they store all the raw ingredients (data), create meals (business logic), and the chef (code logic in the model) prepares the food while not directly interacting with the customers. The View *(M(V)C)* can be represented as the dining area, what the customers (users) see and interact with. It's where the food is presented (user interface). Customers can place orders and receive them but don't see the behind-the-scenes work. And last but not least, the Controller *(MV(C))* can be represented by the server. The server in the restaurant acts as the messenger; when a customer places an order (user input), they relay it to the kitchen (model), and once the meal is ready, the server brings it back to the customer to view. Additionally, the server makes sure the right food reaches the customer and deals with any requests or changes.

## Conclusion
In conclusion, design patterns are important because they offer simple and proven solutions to common problems that we face in software engineering. These designs help software engineers to provide a cleaner, more organized, and maintainable code. Overall, the use of design patterns save time, reduce errors, and makes software easier to build, develop, and improve over time.
