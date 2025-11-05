# 🚀 Expo SDK Upgrade Guide (from SDK 51 ➝ 53 / 54)

This guide walks you through upgrading your Expo project to **SDK 53 or SDK 54** with clean native rebuild.

> ✅ Tested and works for both managed and prebuild workflows.

---

## 📦 Steps to Upgrade

### 1️⃣ Update Expo version in `package.json`

Open `package.json` and update the Expo SDK version:

```json
"expo": "^53.0.0"
// or
"expo": "^54.0.0"
```

---

### 2️⃣ Remove dependency lock files

Delete one of these depending on your package manager:

```
yarn.lock
package-lock.json
```

---

### 3️⃣ Delete existing `node_modules`

```sh
rm -rf node_modules
```

---

### 4️⃣ Install dependencies again

```sh
yarn install
# or
npm install
```

---

### 5️⃣ Auto-fix Expo dependencies

Ensures that all Expo + React Native dependencies match the SDK version.

```sh
npx expo install --fix
```

---

### 6️⃣ (Optional) Check for dependency issues

```sh
npx expo-doctor
```

---

### 7️⃣ Clean native build (Important!)

Delete native folders:

```sh
rm -rf android ios
```

Generate clean native code:

```sh
npx expo prebuild --clean
```

---

### 8️⃣ Run the app

```sh
npx expo start
```

or run directly on devices:

```sh
npx expo run:android
npx expo run:ios
```

---

## ⚠️ Breaking Changes — Manual Updates Required

Some libraries need updates due to breaking changes in SDK 53/54:

| Package                            | Action Required                                |
| ---------------------------------- | ---------------------------------------------- |
| `react-native-reanimated`          | Upgrade to latest version                      |
| `react-native-unistyles`           | Upgrade to latest version                      |
| Gesture handler / router libraries | Update if prompted during `expo install --fix` |

Use:

```sh
npx expo install <package-name>
```

---

## ✅ You’re Done!

Your project is now upgraded to the latest Expo SDK with fresh native folders.

---

Feel free to **fork this repo**, star it ⭐, or contribute improvements!
