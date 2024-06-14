# .github/workflows/ci.yml
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '14'
    - run: npm install
    - run: npm test
# .github/workflows/deploy.yml
name: Deploy
on:
  push:
    branches:
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Build and Deploy
      run: npm run build && npm run deploy
git init
git remote add origin https://github.com/ItsMohzy/repository.git
git checkout -b feature/awesome-feature
git add .
git commit -m "Implement awesome feature"
git push origin feature/awesome-feature
# Create PR on GitHub
