# ------- Build Stage --------
FROM node:21 AS frontend-build
WORKDIR /app
COPY package*.json ./
RUN npm i
COPY . .

# ------- Final Stage --------
FROM node:21-alpine
WORKDIR /app
COPY --from=frontend-build /app .
COPY .env.sample .env.local
EXPOSE 5217
CMD ["npm","run","dev","--","--host"]
