build: clone requirements npm
deploy: app
clone:
        git clone git@github.com:muryginm/node-chat.git
requirements:
        apt install redis nodejs npm
npm:
        cd node-chat && npm install
app:
        cd node-chat && REDIS_HOST=localhost REDIS_PORT=6379 node index.js
