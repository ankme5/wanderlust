# ----- Build Stage ---------
FROM node:21 AS backend-build
WORKDIR /app
COPY . .
RUN npm i

# ----- Final Stage ----------
FROM node:21-alpine
WORKDIR /app
COPY --from=backend-build /app .
COPY .env.sample .env
EXPOSE 5000
CMD ["npm","start"]
