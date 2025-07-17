# 🏬 Spring MVC – Malls & Shops Management System

**Technologies:** `Java`, `Spring MVC`, `JSP`, `HTML`, `CSS`

---

This is my first **Spring MVC application**, developed as part of a university coursework assignment. The goal was to build a basic mall management system, allowing users to view and register malls and their associated shops, with form validation, view rendering, and routing handled by Spring MVC.

---

## 📋 Overview of Tasks

### ✅ Task 1: Project Configuration
- Configured the project to use **JSP** as the view technology
- JSP views stored in:  
  `src/main/webapp/WEB-INF/views/`

---

### 🧱 Task 2: Domain Classes
#### `Shop`
- `boss`, `headquarters`, `industry`, `founded` (with getters/setters)

#### `Mall`
- `id`, `name`, `website`, `List<Shop> shops` (with getters/setters)

---

### 🌐 Task 3: Main Controller
- Created `MainController` to map GET/POST requests for `/` to `start.jsp`

---

### 🏢 Task 4: Malls Functionality
- Created a list of malls in `Hw1Application` with default data
- Implemented:
  - `/malls` → Shows list of malls (view: `malls/list`)
  - `/newMall` → Form to add new mall (`malls/form`)
  - `/addMall` → POST route to add mall and redirect
- Used `modelAttribute="mall"` to bind form data

---

### 🛍️ Task 5: Shops Functionality
- Implemented:
  - `/shops?mall={id}` → View shops of selected mall (`shops/list`)
  - `/newShop?mall={id}` → Form to add shop to selected mall (`shops/form`)
  - `/addShop` → POST route to save shop and redirect
- Used request parameter `mall` to determine target mall
- Forms used `modelAttribute="shop"` for data binding

---

### ✅ Task 6: Validation

#### `Mall` Validator:
- `id` must be unique across malls
- `name` and `website` must not be empty

#### `Shop` Validator:
- `boss` and `headquarters` must not be empty
- `industry` must be one of:
  - `"Clothes"`, `"Footwear"`, `"Jewellery"`
- `founded` must be between **1950 and 2024**

> In both cases, validation errors redirect to the form with field-level error messages displayed

---

## 💡 Key Learning Outcomes

- Set up and configured a **Spring MVC** project from scratch
- Learned how to handle:
  - Routing with Controllers
  - Form data binding using `@ModelAttribute`
  - Validating user input with custom validators
  - Dynamically generating views with JSP
- Strengthened my understanding of MVC architecture and back-end form processing

---

## 📁 Project Structure

```bash
src/
├── main/
│   ├── java/
│   │   └── co2123/hw1/
│   │       ├── controller/
│   │       │   ├── MainController.java
│   │       │   ├── MallController.java
│   │       │   └── ShopController.java
│   │       ├── domain/
│   │       │   ├── Mall.java
│   │       │   └── Shop.java
│   │       └── Hw1Application.java
│   └── webapp/
│       └── WEB-INF/views/
│           ├── start.jsp
│           ├── malls/
│           │   ├── list.jsp
│           │   └── form.jsp
│           └── shops/
│               ├── list.jsp
│               └── form.jsp

