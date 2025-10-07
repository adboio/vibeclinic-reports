# Deploying your app to the App Store

## Video how-to
- [📺 Part 1](https://www.loom.com/share/4f315890f9d5426a88432d0d1f1febfc)
- [📺 Part 2](https://www.loom.com/share/027f077473a94c27b5d14d4172d80834)

## Dev environment setup

### Project setup
1. Download your code from Bolt. You can do this with their built-in download, or (recommended) clone it from GitHub like this:

```bash
git clone https://github.com/ScaleYourGenius/he-app.git
```

2. Add your environment variables in a new file called `.env` at the root of your project folder. It should look like this:

```
VITE_SUPABASE_URL=your-url
VITE_SUPABASE_ANON_KEY=your-key
```

3. If needed, install `brew`, and then `node`:
  - Follow [Homebrew's install guide](https://brew.sh) (it's easy!)
  - Install node with `brew install node`

4. Build your app to make sure it runs:

```bash
npm install
npm run build
```

5. Run your app locally to make sure it works:
```bash
npm run dev
```

### iOS development setup
1. Download Xcode from the [Apple App Store](https://apps.apple.com/us/app/xcode/id497799835?mt=12)

2. Install the Xcode command line tools:
```bash
xcode-select --install
```

3. Install CocoaPods (make sure you installed `brew` in the earlier steps):
```bash
brew install cocoapods
```

### Capacitor configuration
1. Install capacitor with these three commands:
```bash
npm i @capacitor/core
npm i -D @capacitor/cli
npm install @capacitor/ios
```

2. Initialize Capacitor:
```bash
npx cap init
```

3. Add iOS to your app:
```bash
npx cap add ios
```

4. If needed, update the `capacitor.config.ts` file with your actual project information:
  - `appId`: something like `com.your-organization.app-name`
  - `appName`: the display name for your app

## Testing & deploying your app
### Simulator
```bash
# first, build your project
npm run build

# sync your project to capacitor
npx cap sync

# finally, open the simulator!
npx cap run ios
```

### Test on a real device

1. Open the project in Xcode with this command:

```bash
npx cap open ios
```

2. In Xcode, go to Product > Destination and select your device (might need to plug it into your computer, and/or enable development mode on your device)

3. Click the "play" button to build & send to your phone

### Submit to App Store
1. Open the project in Xcode with this command:

```bash
npx cap open ios
```

2. In Xcode, select to Product > Archive

3. You'll be prompted with instructions for submitting to the App Store. At this step, you may also get some errors for configuration stuff (like signing in to yoru Apple developer account, making sure you have an app icon, etc)
