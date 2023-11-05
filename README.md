# Build Vue and deploy it to Github Pages 🚀
This Action will Build your Vue Project and deploy it to Github Pages

## Getting Started 🎉


1.
- For Vue 2 : Create the `vue.config.js` file
- For Vue 3 : You should have a `vite.config.js` or a `vite.config.ts` file at the root of your directory. Create one if you don't.
2.
- For Vue 2 : Add this to your `vue.config.js` (and rename "YourRepoName" to your repo name)
```javascript
module.exports = {
    publicPath: '/YourRepoName/'
}
```
- For Vue 3 : Add this to you `vite.config.js` or `vite.config.ts` (and rename "YourRepoName" to your repo name)
```javascript
export default defineConfig({
  ... // Already existing configurations
  base: '/YourRepoName/'
});
```

3. Create a Github Actions Workflow file and add this to it (and replace "YourGithubName" and "YourRepoName" with the names)
```yml
name: Build Vue
on: [push]
permissions:
  id-token: write
  pages: write
jobs:
  build_vue:
    runs-on: ubuntu-latest
    name: Build Vue
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Vue App to Github Pages
        uses: simmca/VuePagesAction@v1.0.0
```
4. Go to `Settings` -> Scroll down to `Pages` -> Build and Development: Source -> `GitHub Actions`
