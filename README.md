# 📱 MyPay - BBPS Mobile App

> A React Native bill payment application showcasing mobile development expertise

![React Native](https://img.shields.io/badge/React%20Native-0.72-61DAFB?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?logo=typescript)
![Redux](https://img.shields.io/badge/Redux%20Toolkit-1.9-764ABC?logo=redux)
![Nx](https://img.shields.io/badge/Nx%20Monorepo-16-143055?logo=nx)
![Platform](https://img.shields.io/badge/Platform-iOS%20%7C%20Android-lightgrey)

---

## 🎬 Demo
> *Demo video showcasing complete bill payment flows*

<p align="center">
  <a href="https://github.com/thelavi/mypay-react-native-case-study/raw/main/myPay-demo.mp4">
    <img src="./demo.gif" width="280"/>
  </a>
</p>

<p align="center"><sub>Click preview to watch full demo</sub></p>

---

## 📋 About This Project

**MyPay** is a production-grade mobile application for the Bharat Bill Payment System (BBPS), enabling users to pay utility bills and perform mobile recharges.

⚠️ **Note**: Source code is proprietary and under NDA. This repository serves as a portfolio showcase demonstrating technical capabilities and architecture decisions.

---

## 📘 Technical Case Study

If you’d like to explore the architecture, challenges, and design decisions in depth:

👉 **[Read the Technical Case Study](TECHNICAL_CASE_STUDY.md)**

---


## ✨ Features

### Bill Payments
- ⚡ **Electricity** - Multi-state biller support with bill fetch
- 📱 **Mobile Recharge** - Prepaid plans & Postpaid bill payments
- 🔥 **Gas** - Pipeline gas utility payments
- 💧 **Water** - Municipal water bills
- 📺 **DTH** - TV recharge
- 🌐 **Broadband** - Internet bill payments

### Core Functionality
- 🔗 **Linked Bills** - Save frequently paid bills
- 📜 **Transaction History** - Complete payment records
- 🧾 **Digital Receipts** - Share & download receipts
- 👥 **Contact Integration** - Quick mobile recharge from contacts

---

## 🏗️ Architecture

```
┌────────────────────────────────────────────┐
│              PRESENTATION                   │
│   Screens • Components • Navigation         │
├────────────────────────────────────────────┤
│             BUSINESS LOGIC                  │
│   Custom Hooks • Redux Store • Selectors    │
├────────────────────────────────────────────┤
│               DATA LAYER                    │
│   API Services • Mock Layer • Types         │
├────────────────────────────────────────────┤
│              SHARED LIBS                    │
│   Components • Constants • Assets • Utils   │
└────────────────────────────────────────────┘
```

### Tech Stack

| Category | Technology |
|----------|------------|
| Framework | React Native 0.72 |
| Language | TypeScript 5.0 |
| State | Redux Toolkit |
| Navigation | React Navigation v6 |
| Build | Nx Monorepo |
| Platform | iOS 15+ / Android 10+ |

---

## 📱 Screen Flows

### Electricity Bill Payment
```
Select State → Choose Biller → Enter Consumer # → Fetch Bill → Review → Pay → Receipt
```

### Mobile Recharge (Prepaid)
```
Select Contact → Choose Operator → Browse Plans → Select Plan → Pay → Success
```

### Mobile Recharge (Postpaid)
```
Enter Number → Select Operator → Fetch Bill → View Details → Pay → Success
```

---

## 🧩 Component Library

Built reusable, typed components:

| Component | Purpose |
|-----------|---------|
| `TopNav` | Screen header with navigation actions |
| `HomeNav` | Bottom tab bar |
| `Card` | Content card with icon & action |
| `HistoryCard` | Transaction item with status |
| `CustomButton` | Styled CTA button |
| `SelectDropdown` | Native-feel picker |
| `RadioButton` | Selection controls |

---

## 💡 Technical Highlights

### Challenges Solved

1. **Monorepo Module Resolution**
   - Configured Nx workspace for React Native
   - Path aliases for clean imports
   - Shared library architecture

2. **Cross-Platform Consistency**
   - Unified styling approach
   - Platform-specific adaptations
   - Native module handling

3. **Complex Navigation Flows**
   - Nested stack navigators
   - Parameter passing with TypeScript
   - Deep linking support

4. **State Management**
   - Redux for global state
   - React Navigation params for local
   - Custom hooks for logic encapsulation

---

## 📊 Project Stats

| Metric | Count |
|--------|-------|
| Screens | 15+ |
| Components | 10+ |
| Custom Hooks | 8+ |
| Bill Categories | 6 |
| TypeScript Coverage | 100% |

---

## 🛠️ Skills Demonstrated

```
React Native • TypeScript • Redux Toolkit • React Navigation
Nx Monorepo • iOS Development • Android Development
Component Architecture • State Management • Mobile UI/UX
API Integration • Mock-First Development • Cross-Platform
```

---

## 👤 Developer

**Lavi Sharma**

- Designed and implemented complete BBPS payment flows
- Built scalable component library
- Architected monorepo structure
- Resolved complex native module issues

---

## 📬 Contact

Interested in the technical deep-dive or demo walkthrough?

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin)](https://www.linkedin.com/in/sharmalavi)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?logo=gmail)](mailto:sharmalavi1@duck.com)

---

<p align="center">
  <i>Built with ❤️ using React Native</i>
</p>

---

*This repository contains documentation only. Source code is proprietary and protected under NDA.*

