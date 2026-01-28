# AARIK: Flutter Agnostic Architecture
### Enterprise Scalable Mobile Systems
**Developed and Created by: [Aravind](https://www.linkedin.com/in/madaravind)**

![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white)
![Dart](https://img.shields.io/badge/dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)
![License](https://img.shields.io/badge/License-Proprietary-red.svg?style=for-the-badge)

A professional-grade, production-ready Flutter foundation built for teams that demand high scalability, strict decoupling, and zero vendor lock-in. This is not just a template; it is a **Software Engineering Engine.**

---

## 🏛️ The Philosophy: "State as a Detail"
Most Flutter projects are built around a state management library (GetX, BLoC, etc.). If the library dies, the project dies. **AARIK** flips the script. By using **Interface-Driven Design**, the UI remains "blind" to the underlying state management, allowing you to switch engines via a single configuration toggle.

## 💎 The AARIK Kernel
At the heart of this architecture lies the **Agnostic Async Registry & Infrastructure Kernel (AARIK)**. It defines the indestructible set of rules that governs how the system behaves:

* **Agnostic:** Business logic is decoupled from third-party packages. Swap internal tools (like Workmanager or Dio) without refactoring the core.
* **Async:** Engineered for a "Disconnected-First" world, mastering background isolates and deferred execution (e.g., triggering tasks only when internet returns).
* **Registry:** The system's "Brain" uses a centralized Service Locator (`sl`) and Dependency Registry to ensure clean lifecycle management.
* **Infrastructure:** External dependencies (Networking, Database, Background Workers) are treated as swappable outer layers that serve the core.
* **Kernel:** The minimal, high-performance engine that maintains system integrity regardless of UI or State changes.

---

## 🚀 Key Features

### 1. Multi-State Engine (Agnostic Design)
Swap between **GetX, BLoC, Provider, or Riverpod** without changing a single line of code in your UI. Ideal for agencies and large-scale projects.

### 2. High-Level Dependency Injection
A centralized `AppInjector` acts as the "Brain," managing object lifecycles and environment configurations (BaseURL, Timeouts) globally.

### 3. Professional Data Layer (Dio Wrapper)
* **Generic Request Handling:** `getRequest<T>`, `postRequest<T>`, and `postFormData<T>`.
* **Automated Mapping:** Passing mappers ensures type-safety from JSON to Model.
* **Multipart/Form-Data:** Pre-configured for high-performance file uploads.

### 4. Modular MVVM Structure
Strict separation between the **View** (Pixels), **ViewModel** (Logic), and **Model** (Data).

---

# Project Structure
```text
lib/
├── app/
│   ├── config/          # Environment Setup & Global Config
│   └── di/              # AppInjector (Centralized Dependency Injection)
├── features/            # Scalable Feature-First Modules
│   └── login/
│       ├── api/         # Remote Data Sources & Endpoints
│       ├── model/       # Data Entities & Response Models
│       ├── validation/  # Business Logic & Form Validation
│       ├── view/        # Clean UI (Independent of State Framework)
│       └── viewmodel/   # Abstract State Logic & Interface Contracts
├── service/             # Core Engine: Dio Networking & ApiResult Wrappers
├── state_impl/          # The Agnostic Layer (Interchangeable State Engines)
│   ├── bloc/            # BLoC implementation of Feature Interfaces
│   ├── getx/            # GetX implementation of Feature Interfaces
│   ├── provider/        # Provider implementation of Feature Interfaces
│   └── riverpod/        # Riverpod implementation of Feature Interfaces
└── utils/               # Atomic Helpers, Constants & Extensions
```

# How to Use
**Step 1: Set Your State Preference**
In state_config.dart, simply change the currentState:
```dart
const StateType currentState = StateType.bloc; // Options: getX, bloc, provider, etc.
```

**Step 2: Implement the Interface**
Every feature controller must implement the BaseController:
```dart
class LoginBlocController extends Cubit<LoginState> implements LoginControllerBase { ... }
```

**Step 3: Access in UI**
The UI interacts only with the Contract, never the specific library:
```dart
final controller = LoginInjector.instance.getController();
Text(controller.name); // Works regardless of GetX or BLoC
```

# About the Creator
**Aravind** is a **Senior Flutter Engineer** and **Mobile Architect** with a focus on building **enterprise-grade mobile ecosystems**. He specializes in transforming complex business requirements into **scalable, testable, and maintainable** software architectures.

With deep expertise in **Clean Architecture** and **SOLID principles**, Aravind has pioneered the "Agnostic State Management" approach to help development teams avoid framework lock-in and reduce technical debt.

**Technical Specializations:**
**System Architecture:** Designing multi-module Flutter apps using Layered Architecture (Data, Domain, Presentation).

**State Agnostic Design:** Expert-level implementation of BLoC, GetX, Provider, and Riverpod under unified interfaces.

**Networking & Security:** Developing robust, generic networking layers with Dio, handling complex OAuth2 flows, and secure data persistence.

**Performance Optimization:** Advanced profiling of Flutter apps to ensure 60fps UI performance and efficient memory management.

**CI/CD & DevOps:** Setting up automated pipelines for mobile deployment using GitHub Actions, Codemagic, and Fastlane.

**Mission**
"My goal is to bridge the gap between rapid feature delivery and long-term code quality. I build systems that allow developers to focus on creativity while the architecture handles the complexity."

## 🔗 Connect with Me

<p align="start">
<a href="https://www.linkedin.com/in/madaravind">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
</a>
<a href="https://medium.com/@madaravind">
  <img src="https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white" alt="Medium" />
</a>
</p>

**Developed by Aravind** *Senior Flutter Engineer & Mobile Architect*

## 📜 License & Terms
**Proprietary Commercial License** Copyright (c) 2026 Aravind. All Rights Reserved.
+ Use for commercial projects is permitted only with a valid purchase.
+ Redistribution or re-sale of the source code as a template is strictly prohibited.



