# Itmx Probeaufgabe

## Project setup
After cloning this repo.

1. create '.env' file and add following code :

        NODE_ENV=development

        APP_PORT=3002
        APP_DOMAIN=localhost
        APP_PROTOCOL=http

        APP_PREVIEW=false
        APP_PREVIEW_URL=dv.ngrok.io


        VUE_APP_SERVER_URL="${APP_PROTOCOL}://${APP_DOMAIN}:${APP_PORT}"



2. 'yarn install'
3. 'yarn build'
4. 'yarn start' or 'xjs start' if you have the xjs-cli installed.

## Note
Before you start make sure you have`dist` folder by running 'yarn build'
