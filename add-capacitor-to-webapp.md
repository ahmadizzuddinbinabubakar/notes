
# ADD CAPACITOR TO WEB APP

**1. Install the Capacitor CLI locally**<br>
npm install -D @capacitor/cli

**2. Initialize Capacitor in your React project**<br>
npx cap init

**3. Install the required packages**<br>
npm install @capacitor/core @capacitor/ios @capacitor/android

**4. Add the native platforms**<br>
npx cap add ios
npx cap add android
<br>
<br>
# BUILD AND EXPORT

**1. Build project and export the static build**<br>
npm run static

**2. Sync web code into the native platforms**<br>
npx cap sync
