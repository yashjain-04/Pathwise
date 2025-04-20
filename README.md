# 🌍 Pathwise – Smart Route Selector with AI Recommendation Engine

> **Choose Wisely, Commute Smartly**  
> An AI-powered assistant that helps users make sustainable, cost-effective, and time-efficient commuting choices.

---

## 🧠 Problem Statement

Users often struggle to choose the optimal mode of transportation that aligns with their preferences – whether it’s the **fastest**, **cheapest**, or **most eco-friendly**.  
Most navigation and ride-booking apps don’t offer personalized suggestions across **multiple modes of transport**, especially through a smart AI assistant.

---

## 🎯 Objectives

- ✅ Build an intelligent, web-based route planner that lets users choose a **goal**: `Fastest`, `Greenest`, or `Cheapest`.
- ✅ Offer **comparative insights** on estimated time, cost, and CO₂ emissions for all major travel modes.
- ✅ Integrate **AI recommendation engine** (Gemini Pro via OpenRouter) to provide smart, goal-based suggestions.
- ✅ Simulate and track selected trips in real-time, and compare **estimated vs actual** stats.
- ✅ Implement **role-based login system** using Spring Security.

---

## 🚀 Solution Workflow

1. **User Inputs Start & Destination**  
   Users provide pickup and drop-off locations via the UI form.

2. **User Selects Preference**  
   Users choose a goal from: `Fastest`, `Greenest`, or `Cheapest`.

3. **Fetch Transportation Options**  
   Using **Google Maps Directions API**, fetch multiple travel modes:
   - 🚗 Driving (Cab)
   - 🚌 Transit (Bus/Train)
   - 🚲 Bicycling
   - 🚶 Walking

4. **Calculate Cost & CO₂ Emission**  
   - Cost calculated based on distance × rate.
   - CO₂ values estimated per transport mode.

5. **Prompt AI for Recommendation**  
   - Send structured data (mode, time, cost, CO₂) to **Gemini AI**.
   - AI analyzes data and user goal to suggest the best option.

6. **Show Results to User**  
   - Display a **comparison table**.
   - Render AI’s **natural language recommendation** with justification.

7. **Trip Simulation**  
   - After user selects a mode, simulate the trip and dynamically change cost, time, and CO₂.
   - Upon trip completion, display **Estimated vs Actual** comparison.

---

## 🛡️ User Authentication

- Role-based login system:
  - `USER` – Can explore, simulate, and view AI suggestions.
  - `ADMIN` – Reserved for future control features.
- Spring Security handles **login, session management**, and **authorization**.

---

## 🧰 Tech Stack

- **Frontend**: HTML, CSS, JavaScript, JSP
- **Backend**: Java, Spring Boot, Spring MVC, Spring Security, Spring Data JPA
- **Database**: MySQL
- **AI Integration**: Gemini Pro (via OpenRouter)
- **API Integration**: Google Maps Directions API

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

bash
git clone https://github.com/YOUR-USERNAME/pathwise-ai-route-selector.git
cd pathwise-ai-route-selector

Create a database:

CREATE DATABASE pathwise;

# Server Configuration
server.port=8080
server.address=0.0.0.0

# Static Resources
spring.web.resources.static-locations=classpath:/static/

# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/pathwise
spring.datasource.username=root
spring.datasource.password=groot
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA Settings
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

# Spring Boot Settings
spring.main.allow-circular-references=true

# Logging
logging.level.org.springframework.security=DEBUG
logging.level.org.springframework.web=DEBUG

Run using Maven:

./mvnw spring-boot:run

👨‍💻 Team

Yash Jain	Full-stack Developer, API & AI Integration Lead, Backend Architecture, API & Cloud Connectivity
Ritik Kumar	Backend Architecture, API & Cloud Connectivity
Kanishka Dikhit	PPT Creation, Research, Documentation, and Video Production
Vikas Chourasiya	Data Modeling, Route Analysis, Google Maps Integration
Vinay Patidar	UI/UX Design & Frontend Interactivity
