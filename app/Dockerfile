FROM node:20.15.0-alpine as base
RUN mkdir -p /opt/app
WORKDIR /opt/app
RUN adduser -S app
RUN chown -R app /opt/app
COPY package*.json ./

# BUILD TARGET
FROM base as build
RUN npm install && npm cache clean --force
COPY . ./
# RUN mkdir /opt/out && chown -R app /opt/out
RUN npm run export
USER app

# DEVELOPMENT app PROFILE
FROM base as development
ENV NODE_ENV=development
RUN npm install && npm cache clean --force
COPY . ./
EXPOSE 3000
CMD ["npm", "run", "dev"]

# PRODUCTION app PROFILE
FROM nginx:1.22.0-alpine as production
COPY --from=build /opt/app/out /usr/share/nginx/html
RUN rm /etc/nginx/conf.d/default.conf
COPY src/config/nginx.conf /etc/nginx/conf.d
EXPOSE 3000
CMD ["nginx", "-g", "daemon off;"]
