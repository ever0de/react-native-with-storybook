# react-native-with-storybook

## How to run?

```shell
# check config in package.json
# searchDir & pattern
# write *.tsx(component) & *.stories.js
yarn storybook
```

## Use Library

1. [storybook](https://github.com/storybookjs/storybook)
2. [react-native-storybook-loader](https://github.com/elderfo/react-native-storybook-loader)
   - A CLI for dynamically importing stories into Storybook for React Native.

## How do I set up a storybook in my react-native project?

1. Setup react-native

   - use the following template

     ```shell
     npx react-native init components --template react-native-template-typescript
     ```

   - execute pod-install

     ```shell
     npx pod-install
     ```

   - Remove deprecated prettier settings

2. Install storybook

   - [Install storybook](https://storybook.js.org/tutorials/intro-to-storybook/react-native/en/get-started/)

     ```shell
     npx -p @storybook/cli sb init --type react_native
     ```

   - [Install react-native-storybook-loader](https://www.npmjs.com/package/react-native-storybook-loader)

     ```shell
     yarn add -D react-native-storybook-loader
     ```

   - Write script in `package.json`

     ```shell
     # in package.json
     "scripts": {
        "prestorybook": "rnstl"
     }
     ```

   - Write `loadStories()` func in `./storybook/index.js`

     ```javascript
     // import stories
     configure(() => {
       // This function is created in the `storyLoader.js` that appears when `prestorybook` is executed.
       loadStories();
     }, module);
     ```

3. Run storybook

   ```shell
   yarn storybook # run prestorybook and storybook
   yarn <platform> # platform = ios | andriod
   ```

4. Generate Component with storybook
   - Write code in `src/components/**`
