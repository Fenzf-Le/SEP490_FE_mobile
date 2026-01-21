# SEP490_FE_mobile - Manga Mystery Box collect and Trade App

- Abbreviation: **MMB**<br>
A React Native mobile application for an auction and marketplace platform built with Expo. This app enables users to browse auctions, purchase products, rent mystery boxes, manage orders, and interact in real-time through chat functionality.

## Technologies

- **Framework**: React Native with Expo
- **Languages**: TypeScript, JavaScript
- **State Management**: React Context API
- **Navigation**: React Navigation (Stack, Bottom Tabs, Drawer)
- **Real-time Communication**: Socket.io (auctions, chat)
- **Backend Services**: Axios for API calls
- **Database**: Supabase
- **UI Components**: Custom components with React Native
- **Image Management**: Expo Image Picker, Image Proxy API
- **Payment Integration**: PayOS

## Requirements

- **Node.js** (>= 16 recommended)
- **npm** or **yarn**
- **For Expo** (recommended for development):
  - `expo-cli` (optional globally: `npm install -g expo-cli`)
  - Expo Go app on your iOS/Android device (for physical device testing)
- **For React Native CLI** (native builds):
  - **Android**: Android Studio (Android SDK & emulator)
  - **iOS**: Xcode (macOS required)
  - Platform-specific setup: follow the [official React Native environment documentation](https://reactnative.dev/docs/environment-setup)

## Setup & Run

### Using Expo (Recommended for Development)

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd SEP490_FE_mobile
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn
   ```

3. **Configure environment variables** (if needed)
   - Set up Firebase, Supabase, and Socket endpoints in your config files

4. **Start Expo**
   ```bash
   npm start
   # or
   npx expo start
   ```

5. **Open the app**
   - Scan the QR code with Expo Go (Android/iOS), or
   - Press `i` to open the iOS simulator (macOS + Xcode), or
   - Press `a` to open an Android emulator

### Using React Native CLI (Native Builds)

1. **Ensure native prerequisites are configured** (Android Studio / Xcode)

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Run on Android emulator/device**
   ```bash
   npm run android
   # or
   npx react-native run-android
   ```

4. **Run on iOS simulator** (macOS)
   ```bash
   npm run ios
   # or
   npx react-native run-ios
   ```

## Project Structure

```text
SEP490_FE_mobile
├── App.tsx                # Main app entry point
├── index.ts               # App index
├── package.json           # Dependencies and scripts
├── tsconfig.json          # TypeScript configuration
├── metro.config.js        # Metro bundler config
├── babel.config.js        # Babel configuration
├── eas.json               # Expo Application Services config
├── assets/                # Static assets
│   ├── fonts/             # Custom fonts (Oleo Script, Oxanium)
│   └── icons/             # App icons and images
├── src/
│   ├── components/        # Reusable UI components
│   │   ├── ApiImage.tsx
│   │   ├── BoxItem.tsx
│   │   ├── ProductItem.tsx
│   │   ├── CustomHeader.tsx
│   │   ├── CustomText.tsx
│   │   ├── FilterBar.tsx
│   │   ├── MainLayout.tsx
│   │   └── Policy components (Privacy, Terms, Copyright, Regulations)
│   ├── screens/           # Screen components
│   │   ├── Auth/
│   │   ├── Auction/
│   │   ├── Shop/
│   │   ├── Cart & Orders/
│   │   ├── User/
│   │   ├── Chat/
│   │   ├── Other/
│   ├── services/          # API services
│   │   ├── api.auth.js
│   │   ├── api.product.js
│   │   ├── api.auction.js
│   │   ├── api.order.js
│   │   ├── api.cart.js
│   │   ├── api.chat.js
│   │   └── ... (other services)
│   ├── config/            # Configuration files
│   │   ├── axios.js       # Axios instance setup
│   │   ├── firebase.js    # Firebase configuration
│   │   ├── supabase.js    # Supabase configuration
│   │   ├── socket.js      # Socket.io setup
│   │   ├── auctionSocket.ts
│   │   └── ChatSocket.ts
│   ├── context/           # React Context for state management
│   │   └── AuthContext.tsx
│   ├── navigation/        # Navigation configuration
│   │   ├── MainNavigator.tsx
│   │   └── RootNavigation.js
│   ├── constants/         # App constants
│   │   ├── colors.js
│   │   └── gradients.js
│   ├── data/              # Mock/static data
│   │   ├── auctionData.ts
│   │   ├── boxData.ts
│   │   ├── productData.ts
│   │   ├── orderData.ts
│   │   ├── commentData.ts
│   │   ├── exchangeRequestData.ts
│   │   └── userData.ts
│   ├── types/             # TypeScript type definitions
│   └── utils/             # Utility functions
└── android/               # Android native code (Gradle build files)
```

## Features

<details>
<summary><strong>Core Features</strong></summary>

- **Home Screen**: Browse featured auctions and products
- **Search & Filter**: Search products and auctions with filtering options
- **Favorites**: Add products and boxes to favorites
- **Shopping**:
  - Browse products and mystery boxes
  - View detailed product information
  - Add to cart and checkout
  - Order history

</details>

<details>
<summary><strong>Auction System</strong></summary>

- **Auctions**:
  - Browse ongoing auctions
  - Create new auctions
  - Place bids
  - View auction details and bid history
  - Manage your auctions

</details>

<details>
<summary><strong>User Features</strong></summary>

- **User Profiles**:
  - User registration and login
  - Profile management
  - Seller profiles
  - Update profile information
- **Chat**: Real-time chat with other users
- **Notifications**: In-app notifications for orders and auctions

</details>

<details>
<summary><strong>Payment & Financial</strong></summary>

- **Payment Integration**: PayOS payment gateway
- **Top-up Packages**: Purchase account credits
- **Withdraw Requests**: Withdraw funds
- **Order Management**: Track and manage orders

</details>

<details>
<summary><strong>Additional Features</strong></summary>

- **Exchange Requests**: Request product exchanges
- **Comments & Feedback**: Leave feedback on products
- **Real-time Updates**: Socket.io integration for live auction and chat updates
- **Custom UI**: Gradient backgrounds, custom fonts, and themed components

</details>

## Key Architecture Decisions

- **Context API**: Used for authentication state management
- **Socket.io**: Handles real-time auction bidding and chat messaging
- **Axios**: Centralized API request handling with interceptors
- **React Navigation**: Multi-stack and tab-based navigation structure
- **TypeScript**: Partial adoption for type safety in critical components
- **Modular Services**: Separate API service files for different features

## Notes for Review

This is an educational/assignment project demonstrating:
- React Native fundamentals: component composition, navigation, and state management
- Real-time communication using WebSockets
- Integration with third-party services (Firebase, Supabase, PayOS)
- Custom styling with React Native
- TypeScript adoption in React Native projects

**Key files to review**:
- [src/screens/Home.tsx](src/screens/Home.tsx) - Main home screen
- [src/navigation/MainNavigator.tsx](src/navigation/MainNavigator.tsx) - Navigation structure
- [src/context/AuthContext.tsx](src/context/AuthContext.tsx) - Authentication context
- [src/services/](src/services/) - API integration layer

## 📄 License

This project is proprietary and confidential. All rights reserved by MMB-SEP490 Project Team.
