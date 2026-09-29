# CST8915 Lab 1: Algonquin Pet Store on Azure VM

**Student Name**: Collin MacLeod
**Student ID**: macl0379
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/nAvYDlGsea4)

---

## Technical Explanations

### Order Service (Node.js)

[Your explanation here - 1-2 paragraphs]
The Order Service is what receives orders and passes them along to RabbitMQ. The orders received recived from store-front are declares it as durable before being sent to RabbitMQ, this ensures they will survive a restart. To ensure a robust application, the Orders Service and Product Service have been kept seperate to ensure scalability and allow ease of maintenance. This service is built on a Node JS, a framework that runs asynchronously allowing for multiple requests simultaneously. This is useful for an e-commerce application that will want to avoid bottlenecks and give a smooth purchasing experience.

### Product Service (Rust)

[Your explanation here - 1-2 paragraphs]
This is what acts as the back-end for the product catalog. The Product Service receives an API call from store-front when the OrderForm is is loaded and serves all objects in the service. The Product Service is built in Rust using the Warp Web framework. Rust provides a lightweight service with Warp type-safe design and automatic validation for query parameters and request bodies providing the security. Warp also allows for easy chaining of filter making it easy to create complex request handling logic.

### Store Front (Vue.js)

The user interface of this application is built on the Vue.js simple framework. It is incremental with the ability to add on to an application through adding more components or using a Vue.js componenet within a different JS framework giving potential for building into much bigger projects. When running, the Store Front connects with both product-service and order-service to display the order form and functionality.

---

## References

Whitfield B., Jun 03, 2025, What Is Vue JS?
https://builtin.com/software-engineering-perspectives/vue-js

Node.js, Introduction to Node.js
https://nodejs.org/learn/getting-started/introduction-to-nodejs

Chan J., July 23, 2025, Why Node.js is Ideal for Backend: Node.js Best Practices
https://techieidea.hashnode.dev/why-nodejs-is-ideal-for-backend-nodejs-best-practices

Red Sky Digital, January 22, 2026, Comparing Axum, Actix, and Warp: Rust Web Frameworks in 2025
https://redskydigital.com/au/comparing-axum-actix-and-warp-rust-web-frameworks-in-2025/
