# MyPay - BBPS Mobile Application

> 📌 This document is a technical case study of **MyPay** — a React Native mobile application designed following BBPS bill payment flows and standards, enabling seamless utility bill payments and mobile recharges.

![Platform](https://img.shields.io/badge/Platform-iOS%20%7C%20Android-blue)
![Framework](https://img.shields.io/badge/Framework-React%20Native-61DAFB)
![Architecture](https://img.shields.io/badge/Architecture-Nx%20Monorepo-blue)
![State](https://img.shields.io/badge/State-Redux%20Toolkit-764ABC)

---

## 📱 Project Overview

**MyPay** is a comprehensive bill payment application built using React Native, designed to provide users with a seamless experience for paying utility bills and mobile recharges through the BBPS (Bharat Bill Payment System) framework.

### Key Highlights
- **Cross-Platform**: Single codebase for iOS and Android
- **Monorepo Architecture**: Nx-powered workspace for scalable development
- **Real-time Bill Fetching**: Integration-ready architecture for BBPS APIs
- **Secure Payments**: Industry-standard security practices

---

## 🏗️ Technical Architecture

### Technology Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | React Native 0.72+ |
| **Navigation** | React Navigation v6 |
| **State Management** | Redux Toolkit |
| **Build System** | Nx Monorepo |
| **Styling** | StyleSheet (React Native) |
| **Type Safety** | TypeScript |
| **Package Manager** | npm/yarn |

### Project Structure

```
mypay-mobile/
├── apps/
│   └── mypay/
│       └── mobile/              # Main React Native application
│           ├── ios/             # iOS native configuration
│           ├── android/         # Android native configuration
│           └── src/
│               ├── screens/     # Feature screens
│               ├── components/  # App-specific components
│               └── navigation/  # Route configuration
├── libs/
│   ├── shared/
│   │   ├── components/mobile/   # Reusable UI components
│   │   ├── constants/           # App-wide constants & mock data
│   │   ├── hooks/               # Shared React hooks
│   │   └── types/               # TypeScript type definitions
│   ├── hooks/                   # Feature-specific hooks
│   ├── services/                # API services & mock handlers
│   └── assets/                  # Icons, images, fonts
└── tools/                       # Build & development tools
```

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                        PRESENTATION                          │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │   Screens   │  │ Components  │  │    Navigation       │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│                      BUSINESS LOGIC                          │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │Custom Hooks │  │   Redux     │  │   State Selectors   │  │
│  │ (usePayBill)│  │   Store     │  │                     │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│                        DATA LAYER                            │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │  Services   │  │  Mock API   │  │   Type Definitions  │  │
│  │ (API calls) │  │  (Dev mode) │  │                     │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│                       SHARED LIBS                            │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │  Constants  │  │   Assets    │  │   Shared Hooks      │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

---

## ✨ Features Implemented

### 1. Dashboard & Navigation
- **Bottom Tab Navigation**: Home, History, Profile sections
- **Nested Stack Navigation**: Deep linking support for bill flows
- **Dynamic Header**: Context-aware top navigation with back/home actions

### 2. Bill Payment Categories

| Category | Features |
|----------|----------|
| **Electricity** | State/Biller selection, Consumer number validation, Bill fetch, Amount confirmation |
| **Mobile Recharge** | Prepaid/Postpaid toggle, Contact picker, Circle detection, Plan browsing |
| **Gas** | Pipeline gas bill payments |
| **Water** | Municipal water bill payments |
| **DTH** | Direct-to-home TV recharges |
| **Broadband** | Internet bill payments |

### 3. Electricity Bill Payment Flow

```
┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│ Select State │ -> │ Select Biller│ -> │Enter Consumer│
│              │    │              │    │    Number    │
└──────────────┘    └──────────────┘    └──────────────┘
        │
        v
┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│ Fetch Bill   │ -> │ Bill Details │ -> │  Pay Amount  │
│   Details    │    │   & Review   │    │              │
└──────────────┘    └──────────────┘    └──────────────┘
        │
        v
┌──────────────┐    ┌──────────────┐
│   Payment    │ -> │    Bill      │
│   Success    │    │   Receipt    │
└──────────────┘    └──────────────┘
```

### 4. Mobile Recharge Flow

#### Prepaid Flow
- Contact selection from device
- Operator & circle auto-detection
- Browse plans by category (Popular, Data, Talktime, etc.)
- Quick recharge with saved preferences

#### Postpaid Flow
- Operator selection
- Bill fetch with due date
- Bill details view (expandable)
- One-tap bill payment

### 5. Transaction History
- Categorized view (Recent/Previous)
- Status indicators (Success/Pending/Failed)
- Transaction details with receipt access
- Filter and search capabilities

### 6. My Bills (Linked Bills)
- Save frequently paid bills
- Quick access from dashboard
- Auto-fetch bill amounts
- One-tap repeat payments

### 7. Bill Receipt
- Dynamic receipt generation
- Share functionality (native share sheet)
- Transaction details display
- Complaint registration

---

## 🧩 Component Library

Built a reusable component library within the monorepo:

| Component | Description |
|-----------|-------------|
| `TopNav` | Configurable header with back, home, and title |
| `HomeNav` | Bottom tab bar with active state |
| `Card` | Generic card with icon, title, and action |
| `HistoryCard` | Transaction display with status badge |
| `CustomButton` | Styled button with loading states |
| `SelectDropdown` | Native-feel dropdown selector |
| `Spinner` | Loading indicator |
| `RadioButton` | Single/multi-select options |

---

## 🔧 Technical Challenges & Solutions

### Challenge 1: Metro Bundler Path Resolution in Monorepo

**Problem**: Deep relative imports across library boundaries caused Metro bundler failures.

**Solution**: 
- Configured path aliases in `tsconfig.json`
- Moved critical assets to consuming library directories
- Used Nx workspace references for clean imports

### Challenge 2: Native Module Crashes

**Problem**: Third-party native modules (contacts) caused app crashes due to misconfiguration.

**Solution**:
- Implemented defensive coding with try-catch wrappers
- Created mock data layer for development
- Graceful fallbacks when native features unavailable

### Challenge 3: Cross-Screen Data Flow

**Problem**: Maintaining state consistency across complex navigation flows.

**Solution**:
- Utilized React Navigation params for screen-to-screen data
- Redux store for global state (user preferences, history)
- Custom hooks for encapsulating business logic

### Challenge 4: Dynamic Bill Amount Display

**Problem**: Hardcoded values appearing instead of actual transaction data.

**Solution**:
- Implemented proper parameter passing through navigation
- Created typed interfaces for route params
- Added fallback values with clear "N/A" indicators

---

## 📊 State Management

### Redux Store Structure

```
store/
├── auth/          # User authentication state
├── bills/         # Current bill flow state
├── history/       # Transaction history
└── preferences/   # User settings
```

### Custom Hooks Pattern

Implemented feature-specific hooks for clean separation:

- `usePayBill` - Dashboard actions and navigation
- `usePayElectricityBill` - Electricity payment flow logic
- `useMobileRecharge` - Mobile recharge flow logic
- `useRechargePlan` - Plan selection and filtering
- `useContacts` - Device contacts access
- `useTheme` - Dynamic theming support

---

## 🎨 UI/UX Highlights

### Design System
- Consistent color palette with theme support
- Typography scale for hierarchy
- Spacing tokens for layout consistency
- Shadow/elevation standards

### Accessibility
- Proper touch target sizes
- Screen reader compatible labels
- Color contrast compliance

### Performance
- Lazy loading for screens
- Optimized re-renders with proper memoization
- Efficient list rendering with FlatList/ScrollView

---

## 📱 Screenshots & Demo Access

> *Screenshots available upon request - NDA restrictions apply*

### 🎬 Demo Video

Demo available on request (NDA-safe version):

👉 [View Demo on Google Drive](https://drive.google.com/file/d/1Sjh7YeTL_bgxEXIz9z8-sxagTU5nY2MO/view?usp=drive_link)

### Screen Flow Overview

1. **Home Dashboard** - Quick access to all bill categories
2. **Category Selection** - Choose bill type with visual icons
3. **Biller Selection** - State-wise biller listing
4. **Bill Input** - Consumer number entry with validation
5. **Bill Details** - Fetched bill with breakdown
6. **Payment Confirmation** - Amount review and proceed
7. **Payment Success** - Confirmation with receipt option
8. **Bill Receipt** - Detailed transaction receipt
9. **History** - All past transactions

---

## 🔒 Security Considerations

- No sensitive data stored in plain text
- Secure parameter passing between screens
- API-ready architecture with token-based auth hooks
- Input validation and sanitization

---

## 🚀 Development Workflow

### Local Development
```bash
# Start Metro bundler
npm run start

# Run on iOS Simulator
npm run ios

# Run on Android Emulator
npm run android
```

### Build Process
- Monorepo-managed build pipeline
- Environment-specific configurations
- Optimized production builds

---

## 📈 Metrics & Impact

| Metric | Achievement |
|--------|-------------|
| **Screens Developed** | 15+ |
| **Reusable Components** | 10+ |
| **Custom Hooks** | 8+ |
| **Bill Categories** | 6 |
| **Codebase Size** | Medium-scale, multi-module project |

---

## 🎯 Key Learnings

1. **Monorepo Benefits**: Shared code, consistent tooling, simplified dependency management
2. **React Native Debugging**: Metro bundler intricacies, native crash investigation
3. **Navigation Patterns**: Complex nested navigation with proper state management
4. **Mock-First Development**: Enabled frontend development independent of backend

---

## 👤 Role & Contributions

**Role**: Frontend Developer (React Native)

**Key Contributions**:
- Architected and implemented complete BBPS payment flows
- Built reusable component library
- Integrated state management with Redux Toolkit
- Resolved complex Metro bundler and native module issues
- Implemented mock API layer for development
- Ensured cross-platform compatibility (iOS/Android)

---

## 🔗 Related Skills Demonstrated

- React Native / React.js
- TypeScript
- Redux Toolkit
- React Navigation
- Nx Monorepo
- iOS/Android Development
- Component Architecture
- State Management Patterns
- Mobile UI/UX Best Practices

---

## 🔮 Future Improvements

- Add automated test coverage for core flows
- Move toward feature-sliced architecture for better isolation
- Introduce performance monitoring (Flipper/Firebase Performance)

---

## 📬 Contact

For demo video or detailed walkthrough, please reach out.

---

*Note: Source code is not included due to NDA. This document focuses only on architecture, approach, and learnings.*

