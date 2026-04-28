FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

# Install dependencies with retry config
RUN npm config set fetch-retries 5 \
 && npm config set fetch-retry-maxtimeout 600000 \
 && npm config set registry https://registry.npmjs.org/ \
 && npm install --no-audit --no-fund

COPY . .

EXPOSE 3000

CMD ["npm", "start"]