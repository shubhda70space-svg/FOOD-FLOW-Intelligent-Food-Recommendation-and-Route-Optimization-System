# 🍽️ FOOD FLOW

### Intelligent Food Recommendation and Route Optimization System

<p align="center">

**Smart Takeaway • Smart Dine-In • Smart Delivery**

*A C++ Data Structures & Algorithms based project for personalized food recommendations and route optimization.*

</p>

---

## 🌟 About the Project

**FOOD FLOW** is an intelligent food recommendation and route optimization system designed to help users select the most suitable restaurant based on their **location, food preferences, restaurant rating, preparation time, and available time**.

Traditional food applications often recommend restaurants primarily using distance, ratings, reviews, popularity, or cuisine type. However, the highest-rated or nearest restaurant may not always be the best option for a user at a particular time.

For example, a highly rated restaurant may be nearby but crowded, causing a long waiting time. A user with only one hour available may therefore be better served by another restaurant with a shorter waiting time.

**FOOD FLOW aims to solve this problem by determining not only which restaurant is good, but which restaurant is best suited for a particular user at a particular time.**

The project combines **food recommendation, route optimization, order management, and user preferences** into a single C++ console-based application.

---

## 🎯 Problem Statement

Current restaurant discovery and food-ordering platforms generally recommend restaurants using factors such as:

* 📍 Location
* ⭐ Ratings
* 🍴 Cuisine
* 👍 Popularity
* 🛵 Delivery options

Map-based applications can provide routes and estimated travel times, but **food recommendation and route planning are generally handled as separate tasks**.

FOOD FLOW brings these concepts together by using **Data Structures and Algorithms** to recommend suitable restaurants while also calculating efficient routes.

---

## 💡 Motivation

The main motivation behind FOOD FLOW is to make restaurant recommendations more **practical, personalized, and time-aware**.

A restaurant with the highest rating is not necessarily the best choice if:

* It is too far away.
* It has a long preparation time.
* It is currently crowded.
* The user's available time is limited.
* It does not match the user's preferred cuisine.

FOOD FLOW considers these factors together to provide a more meaningful recommendation.

> **The goal is simple: Don't just find the best restaurant — find the best restaurant for YOU, at the RIGHT TIME.**

---

# ✨ Key Features

### 🔐 1. User Management

The system provides basic user account functionality including:

* User registration
* Login
* Password verification
* User information management

---

### 🚗 2. Smart Takeaway

The **Smart Takeaway** module helps users select a restaurant when they want to pick up food.

The recommendation can consider:

* 📍 Current location
* 🗺️ Route to destination
* 🎯 Destination
* 🍴 Cuisine preference
* ⏱️ Travel time
* 🍳 Food preparation time
* ⭐ Restaurant rating
* ❤️ User preferences

The system uses route information to determine suitable restaurants and can compare the user's travel time with food preparation time.

### ⏱️ Time Matching

A key idea is matching:

**Travel Time ↔ Food Preparation Time**

This helps reduce unnecessary waiting.

For example:

```text
Travel Time       = 13 minutes
Preparation Time  = 15 minutes

Time Difference   = |13 - 15|
                  = 2 minutes
```

A smaller difference can indicate a more suitable takeaway option.

---

# 🍽️ 3. Smart Dine-In

The **Smart Dine-In** module recommends restaurants based on the user's available time and preferences.

Factors include:

* 🍛 Cuisine preference
* 📍 Distance
* ⏰ Available time
* ⭐ Restaurant rating
* 📊 Restaurant congestion
* 🧾 Current orders
* 🏪 Restaurant capacity

The system can provide different recommendations depending on the user's time window.

For example:

```text
Available Time: 1 Hour
        ↓
Prefer nearby restaurants
        ↓
Consider rating & congestion
        ↓
Generate suitable recommendation
```

A user with more available time can consider restaurants that are slightly farther away.

---

# 🛵 4. Smart Delivery

The **Smart Delivery** module recommends restaurants for delivery using multiple factors.

The system considers:

* ⭐ Restaurant rating
* 📍 Distance
* 🍳 Food preparation time
* 🛵 Estimated delivery time
* ❤️ User preferences
* 📊 Restaurant load

The nearest restaurant is therefore **not automatically considered the best restaurant**.

Instead, the system evaluates multiple factors before generating a recommendation.

---

# 🧠 Recommendation Engine

The core of FOOD FLOW is its recommendation logic.

Restaurants can be evaluated using factors such as:

```text
Restaurant Score =
    Rating Score
  + Distance Score
  + Preparation Time Match
  + User Preference Score
  - Congestion Penalty
```

A simplified scoring approach can be represented as:

```text
Score =
    (Rating × Rating Weight)
  - (Distance × Distance Weight)
  - Preparation Time Difference
  + Preference Bonus
  - Congestion Penalty
```

Different food-service modules can prioritize different factors.

### 🚗 Takeaway Priority

1. Restaurant on or near the route
2. Travel time
3. Preparation time match
4. Rating
5. User preference

### 🍽️ Dine-In Priority

1. Available time window
2. Distance
3. Rating
4. Restaurant congestion
5. Cuisine availability

### 🛵 Delivery Priority

1. Rating
2. Distance
3. Delivery time
4. Preparation time
5. User preference

---

# 🗺️ Route Optimization

FOOD FLOW uses a **weighted graph** to represent locations and routes.

```text
Location → Vertex
Road     → Edge
Distance → Weight
```

A simplified representation:

```text
       Location A
       /        \
    2 km        3 km
     /            \
Location B ------ Location C
       \          /
        \        /
         Location D
```

The graph represents:

* Locations
* Roads
* Distances
* Restaurant routes
* User-to-restaurant paths

---

## ⚡ Dijkstra's Algorithm

**Dijkstra's shortest path algorithm** is used to find efficient routes between locations.

The basic flow is:

```text
User Location
      ↓
Restaurant Selection
      ↓
Shortest Route Calculation
      ↓
Travel Time Estimation
      ↓
Recommendation
```

For an implementation using a priority queue, the expected time complexity is:

```text
O((V + E) log V)
```

where:

* `V` = Number of vertices
* `E` = Number of edges

---

# 🧱 Data Structures Used

FOOD FLOW demonstrates the practical use of several Data Structures:

| Data Structure     | Purpose                                                       |
| ------------------ | ------------------------------------------------------------- |
| 🌐 Graph           | Represents locations and roads                                |
| 🗺️ Adjacency List | Stores connected locations                                    |
| 📦 Vector          | Stores restaurants, menus, and other collections              |
| 🔗 Linked List     | Handles dynamic order/cart information                        |
| 📋 Queue           | Handles order-related operations                              |
| 📚 Stack           | Supports sequential/navigation operations                     |
| ⚡ Hash Map         | Provides efficient lookup of users and restaurant information |
| 🚦 Priority Queue  | Supports shortest-path processing                             |

---

# 🔎 Searching & Sorting

Searching and sorting techniques are used to process restaurant and food information.

### Searching

* Linear Search
* Binary Search

### Sorting

Restaurants can be ordered according to factors such as:

* Distance
* Rating
* Preparation time
* User preferences

These techniques help the system efficiently filter and rank available restaurants.

---

# 🍔 Menu & Order Management

After selecting a restaurant, users can view available food items and place orders.

The system supports:

```text
Restaurant
    ↓
Menu
    ↓
Food Selection
    ↓
Order
    ↓
Payment
    ↓
Order History
```

Users can manage their selected food items and confirm their orders.

---

# 💳 Payment Simulation

FOOD FLOW includes a **simulated payment system** for academic purposes.

Possible payment methods include:

* 💵 Cash
* 💳 Online Payment

> No real payment gateway is connected because FOOD FLOW is currently a C++ console-based prototype.

---

# 📜 Order History

Completed orders can be maintained as part of the user's order history.

Order history can help the system understand previous user choices and support more personalized recommendations.

```text
Previous Orders
       ↓
User Preferences
       ↓
Recommendation System
       ↓
Personalized Suggestions
```

---

# ⭐ Reviews & Feedback

The system includes a feedback mechanism where users can provide:

* ⭐ Rating
* 📝 Feedback

This information can be stored for future analysis and improvement of the recommendation system.

---

# 🏗️ System Architecture

The overall system can be represented as:

```text
                    ┌──────────────────┐
                    │      USER        │
                    └────────┬─────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │ Login / Registration│
                  └──────────┬──────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │    MAIN MENU    │
                    └────────┬────────┘
                             │
             ┌───────────────┼───────────────┐
             ▼               ▼               ▼
       Smart Takeaway   Smart Dine-In   Smart Delivery
             │               │               │
             └───────────────┼───────────────┘
                             ▼
                 ┌──────────────────────┐
                 │ Recommendation Engine │
                 └──────────┬───────────┘
                            │
                 ┌──────────┴──────────┐
                 ▼                     ▼
        Restaurant Ranking      Route Optimization
                 │                     │
                 └──────────┬──────────┘
                            ▼
                    ┌───────────────┐
                    │ Order System  │
                    └───────┬───────┘
                            ▼
                  ┌──────────────────┐
                  │ Payment / Review │
                  └──────────────────┘
```

---

# 🛠️ Technology Stack

| Technology               | Usage                             |
| ------------------------ | --------------------------------- |
| **C++**                  | Core programming language         |
| **Data Structures**      | Data management                   |
| **Algorithms**           | Searching, sorting & optimization |
| **Graph**                | Route representation              |
| **Dijkstra's Algorithm** | Shortest path calculation         |
| **C++ STL**              | Implementation support            |
| **VS Code**              | Development environment           |

---

# 📁 Project Structure

```text
FOOD-FLOW/
│
├── README.md
│
├── src/
│   └── FOOD_FLOW.cpp
│
├── docs/
│   └── Project Documentation
│
└── assets/
    └── Screenshots
```

> The structure can be updated according to the actual files present in the repository.

---

# 🎯 Project Objectives

The project aims to:

* Build a C++ based food recommendation system.
* Apply Data Structures and Algorithms to a practical problem.
* Implement shortest route calculation using Dijkstra's algorithm.
* Recommend restaurants based on multiple factors.
* Provide takeaway, dine-in, and delivery options.
* Manage users, menus, orders, and order history.
* Simulate payment and feedback functionality.
* Demonstrate how route optimization and food recommendation can work together.

---

# 📦 Project Outcome

The final system is intended to provide a working **C++ console application** capable of:

✅ Recommending suitable restaurants
✅ Finding efficient routes
✅ Providing takeaway options
✅ Providing dine-in options
✅ Providing delivery options
✅ Processing orders
✅ Simulating payments
✅ Collecting feedback
✅ Maintaining order history

---

# ⚠️ Assumptions & Limitations

FOOD FLOW is currently an **academic C++ console-based prototype**.

Therefore:

* Restaurant information is assumed/simulated.
* Location information is assumed/simulated.
* Travel time is simulated.
* Crowd information is assumed/simulated.
* Payment is simulated.
* Real-time GPS is not currently integrated.
* Online payment gateways are not currently integrated.

---

# 🔮 Future Scope

FOOD FLOW can be further developed by adding:

* 📍 Real-time GPS integration
* 🗺️ Real-world map APIs
* 🚦 Live traffic information
* 🏪 Real-time restaurant availability
* 👥 Live crowd/waiting information
* 💳 Real online payment gateways
* 📱 Mobile application
* 🌐 Web-based interface
* 🤖 More advanced recommendation algorithms
* 📊 Data-driven personalization

---

# 📚 References

1. Bjarne Stroustrup — *The C++ Programming Language*
2. Cormen et al. — *Introduction to Algorithms*
3. C++ Standard Template Library (STL) Documentation
4. E. W. Dijkstra — *A Note on Two Problems Related to Graphs*, 1959

---

# 👥 Project Team

**FOOD FLOW: Intelligent Food Recommendation and Route Optimization System**

**Team ID:** `DSCPP-III-2026-T165`

| Role              | Team Member        |
| ----------------- | ------------------ |
| 👩‍💻 Team Lead   | Ipsita Bansal      |
| 👨‍💻 Team Member | Surya Pratap Tyagi |
| 👩‍💻 Team Member | Shubhda Joshi      |
| 👩‍💻 Team Member | Sehar Gupta        |

---

## ⭐ Project Vision

> **FOOD FLOW — Making food recommendations smarter by considering not only what you like, but where you are, how much time you have, and which option fits your journey best.**

---

<p align="center">

### 🍽️ FOOD FLOW

**Smart Food. Smart Routes. Smarter Decisions.**

</p>
