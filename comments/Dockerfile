# Install dependencies and build the source code DEFINE YOUR life lirert1234678919783461278898789672334
FROM node:16-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

# Run the application1234567898989
FROM node:16-alpine AS runner
WORKDIR /app
ENV NODE_ENV production
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/package*.json ./
RUN npm install --omit=dev

USER node

EXPOSE 3000

ENV PORT 3000

CMD ["npm", "start"]
