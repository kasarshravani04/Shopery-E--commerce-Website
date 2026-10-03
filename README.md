# Shopery - E-Commerce Food Ordering Website

A responsive, feature-rich food ordering web application built using **Angular (Standalone Architecture & Signals)**, **Tailwind CSS**, and **REST APIs**. The platform allows customers to browse food items by category, manage a persistent shopping cart, simulate checkout workflows, and track past order history.

---

## 🚀 Key Features

* **Dynamic Product Catalog & Filtering**: Real-time browsing of food and grocery products with dynamic category filtering and empty state handling.
* **Customer Authentication**: Account registration and login workflows with customer credential verification and local storage session persistence.
* **Cart Operations & Cross-Component Reactivity**: Modal-based quantity selection and synchronized cart state across the navigation bar and checkout via RxJS Subjects and Angular Signals.
* **Checkout & Order Placement**: Multi-field address form validation and order submission via REST endpoints.
* **Order History Dashboard**: Dynamic order tracking displaying itemized purchases, billing summaries, and order records per customer.
* **Modern UI/UX**: Fully custom, responsive interface styled with **Tailwind CSS**.

---

## 🛠️ Tech Stack & Libraries

* **Framework**: Angular (Standalone Components, Signals, Built-in Control Flow `@if` / `@for`)
* **Styling**: Tailwind CSS (Utility-first styling, Flexbox/Grid responsive layouts)
* **Reactivity & Async**: RxJS (`Observable`, `Subject`, `tap`, `map`) & Angular Signals (`signal()`, `.set()`)
* **Routing**: Angular Router (Functional routing, route parameters)
* **HTTP Client**: Angular `HttpClient` with typed models and centralized API constants
* **Backend API**: Cloud-hosted REST API endpoints (`freeapi.miniprojectideas.com` / `freeapi.gerasim.in`)

---

## 📁 Project Folder Structure

The project strictly follows the architecture from the tutorial, isolating constants, interfaces, and shared state into dedicated modules:

```text
src/
├── app/
│   ├── constant/
│   │   └── constant.ts               # Centralized API method names, endpoints, and storage keys
│   ├── models/
│   │   ├── api.response.model.ts     # Generic API response contract (result, message, data)
│   │   ├── product.model.ts          # Interfaces for Products, Categories, and Cart items
│   │   └── user.model.ts             # Classes/models for Customer Register and Login payloads
│   ├── pages/
│   │   ├── home/                     # Landing page with banner, categories, and product listing
│   │   │   ├── home.component.html
│   │   │   ├── home.component.css
│   │   │   └── home.component.ts
│   │   ├── login/                    # Dynamic toggle between Customer Registration and Login
│   │   │   ├── login.component.html
│   │   │   ├── login.component.css
│   │   │   └── login.component.ts
│   │   ├── checkout/                 # Cart review, delivery address form, and place-order action
│   │   │   ├── checkout.component.html
│   │   │   ├── checkout.component.css
│   │   │   └── checkout.component.ts
│   │   └── my-orders/                # Customer order history and item breakdown
│   │       ├── my-orders.component.html
│   │       ├── my-orders.component.css
│   │       └── my-orders.component.ts
│   ├── services/
│   │   ├── product.service.ts        # API integrations for Products, Categories, Cart, and Orders
│   │   └── user.service.ts           # Authentication APIs, active user state, and event Subjects
│   ├── app.component.html            # Global layout with navigation bar and router outlet
│   ├── app.component.ts              # Syncs navbar cart count and active user session
│   ├── app.config.ts                 # Global providers (provideHttpClient, provideRouter)
│   └── app.routes.ts                 # Route definitions and navigation paths
├── environments/
│   ├── environment.development.ts    # Base API URL for local development
│   └── environment.ts                # Production API endpoint configuration
├── styles.css                        # Global Tailwind CSS imports and base typography
└── index.html
