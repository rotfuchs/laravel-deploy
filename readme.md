
# Laravel Deploy

## Config example:

```
name: Build and Deploy
on:
    push:
        branches:
            -   master

jobs:
    build:
        name: Build and Deploy
        runs-on: ubuntu-latest
        steps:
            -   name: Checkout Repository
                uses: actions/checkout@master
            -   name: Setup Enviroment
                uses: shivammathur/setup-php@v2
                with:
                    php-version: '8.3'
            -   name: Install Packages
                run: composer install --no-dev
            -   name: Deploy to Server
                uses: rotfuchs/laravel-deploy@v0.1.1-alpha
                with:
                    user: user
                    host: host
                    port: port
                    path: path
                    owner: owner
                env:
                    DEPLOY_KEY: ${{ secrets.DEPLOY_KEY }}
```
