# CalcDash App 📱

Professional calculator app for iOS & Android with premium features and in-app purchases.

## Features

### Free Tier
- 8 Professional Calculators
  - Basic Calculator
  - BMI Calculator
  - Age Calculator
  - Loan Calculator
  - Mortgage Calculator
  - Tip Calculator
  - Unit Converter
  - Percentage Calculator
- Ad-supported

### Premium ($2.99 one-time purchase)
- ✨ **Calculation History** - Save and manage all your calculations
- ⭐ **Favorites** - Bookmark frequently used calculations
- 📤 **Share Results** - Export and share calculations via email, PDF, and social media
- 🎨 **Custom Themes** - Multiple color schemes
- 📊 **Offline Mode** - Full functionality without internet connection
- 🔔 **No Ads** - Ad-free experience

## Tech Stack

- **React Native** - Cross-platform mobile framework
- **Expo** - Development platform
- **Redux Toolkit** - State management
- **RevenueCat** - In-app purchases (iOS & Android)
- **AsyncStorage** - Local data persistence
- **TypeScript** - Type-safe development

## Getting Started

### Prerequisites
- Node.js (v18+)
- npm or yarn
- Expo CLI: `npm install -g expo-cli`

### Installation

1. Clone the repository:
```bash
git clone https://github.com/DMichele2272/Calcdash-app.git
cd Calcdash-app
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file from template:
```bash
cp .env.example .env
```

4. Add your RevenueCat API keys to `.env`

### Development

Start the development server:
```bash
npm start
```

Run on iOS simulator:
```bash
npm run ios
```

Run on Android emulator:
```bash
npm run android
```

## Building for App Stores

### Build for iOS
```bash
npm run build:ios
```

### Build for Android
```bash
npm run build:android
```

### Submit to App Stores
```bash
eas submit --platform ios
eas submit --platform android
```

## Project Structure

```
Calcdash-app/
├── src/
│   ├── components/          # Reusable components
│   ├── screens/            # App screens
│   ├── services/           # Services (RevenueCat, Storage, etc)
│   ├── store/              # Redux store
│   ├── utils/              # Utility functions
│   └── constants/          # App constants
├── app.json                # Expo configuration
├── eas.json               # EAS build configuration
├── package.json           # Dependencies
├── tsconfig.json          # TypeScript config
└── README.md
```

## Configuration

### RevenueCat Setup

1. Create account at [RevenueCat](https://www.revenuecat.com)
2. Create new project
3. Add products for iOS and Android
4. Create entitlement: `premium`
5. Copy API keys to `.env`

### App Icons & Splash Screen

Replace these files with your images:
- `assets/icon.png` (1024x1024)
- `assets/splash.png` (1242x2436)
- `assets/adaptive-icon.png` (1080x1080 for Android)

## Monetization Strategy

- **Free Tier**: All calculators with ads
- **Premium**: $2.99 one-time purchase removes ads and unlocks premium features
- **Target**: 5-10% conversion rate

## Common Tasks

### Adding a New Calculator

1. Create component in `src/components/calculators/`
2. Add to calculator list in `src/constants/`
3. Component automatically appears in app

### Checking Premium Status

```typescript
import { useAppSelector } from '../store/store';

function MyComponent() {
  const isPremium = useAppSelector(state => state.user.isPremium);
  
  return isPremium ? <PremiumFeature /> : <UpgradePrompt />;
}
```

## Troubleshooting

### RevenueCat not working
- Verify API keys in `.env`
- Check bundle IDs match in `app.json`
- Ensure products are configured in RevenueCat dashboard

### Build failures
- Clear cache: `expo prebuild --clean`
- Reinstall dependencies: `rm -rf node_modules && npm install`
- Check Xcode/Android Studio versions

### History not saving
- Check AsyncStorage permissions
- Verify device storage is available
- Clear app cache and try again

## Support

- **Expo Docs**: https://docs.expo.dev
- **React Native Docs**: https://reactnative.dev
- **RevenueCat Docs**: https://docs.revenuecat.com
- **Redux Docs**: https://redux.js.org

## Related Projects

- **Web Version**: [CalcDash](https://github.com/DMichele2272/CalcDash)

---

**Built with ❤️ using React Native & Expo**

*Keep mobile and web versions separate to avoid confusion!*
