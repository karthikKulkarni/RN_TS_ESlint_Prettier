# RN_TS_ESlint_Prettier
A boiler plate for React Native 0.61, TS 3.7, ES Lint 6.8, Prettier 1.19, Jest 24.9

Date : 29 Jan 2020 Updated: 29 Jan 2020

Steps:

1. Update react native to latest globally  
   \$ npm install -g react-native@latest
2. Create react native app with typescript template  
   \$ react-native init <ProjectName> --template react-native-template-typescript
3. Update the package name/ bundle identifier if necessary
   a. iOS:
   Open xcode -> <ProjectName> -> Targets <select ProjectName> -> General -> Bundle Identifier
   b. Android:
   Package name can be updated using "react-native-rename" npm. But this also changing of app name.
4. Add project to git - https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line
   $ git init
    $ git add .
   $ git commit -m "Initial commit"
    $ git remote add origin <remote repository URL>
   $ git remote -v
   \$ git push -u origin master
5. Install ESlint, prettier and types for each
   \$ npm install --save-dev eslint prettier eslint-plugin-react eslint-plugin-import eslint-plugin-jsx-a11y @typescript-eslint/eslint-plugin eslint-config-airbnb-typescript eslint-config-prettier eslint-plugin-prettier
6. Config ES lint
   module.exports = {
   root: true,
   extends: ['@react-native-community', 'airbnb-typescript', 'prettier', 'prettier/@typescript-eslint', 'prettier/react'],
   };
7. Config prettier
   {
   "singleQuote": true,
   "trailingComma": "all",
   }
8. Exclude test files from ts in tsconfig.js
   "exclude": [
   "__tests__/**/*-test.ts"
   ]
9. Enable Hermes engine for android - https://facebook.github.io/react-native/docs/hermes
   android/app/build.gradle
   "enableHermes": true // clean and rebuild if changing
   proguard-rules.pro
   -keep class com.facebook.hermes.unicode.\*_ { _; }
10. Build the app
    $react-native run-ios / react-native run-android
    or
    $yarn ios / yarn android
11. Commit all the new git changes
    $ git add . 
    $ git commit -m "Config TS ES prettier"
    \$ git push
