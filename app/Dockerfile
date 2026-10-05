# ---- base : Node + dépendances ----
FROM node:22-alpine AS base
WORKDIR /app
COPY package*.json ./

# ---- dev : hot-reload ----
FROM base AS dev
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "run", "dev"]

# ---- build : compilation de production ----
FROM base AS build
RUN npm ci
COPY . .
RUN npm run build

# ---- prod : image finale légère ----
FROM node:22-alpine AS prod
WORKDIR /app
ENV NODE_ENV=production
COPY --from=build /app/package*.json ./
COPY --from=build /app/.next ./.next
COPY --from=build /app/public ./public
RUN npm ci --omit=dev
EXPOSE 3000
CMD ["npm", "start"]