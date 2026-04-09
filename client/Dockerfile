# ------------------------------------------------------------------------------
# 🏗️ Stage 1: Frontend Build Stage (Vite / React App)
# ------------------------------------------------------------------------------

FROM node:21 AS frontend-builder

#  Set working directory inside container
WORKDIR /app

#  Copy dependency files (for better caching)
COPY package*.json ./

# Install all dependencies
RUN npm install

#  Copy complete source code to working dir
COPY . .

# Build args declare karo
ARG VITE_BACKEND_URL

#  Set environment to production in this stage no dev dependencies are included
ENV NODE_ENV=production

#  Inject Backend API URL (Build-time variable)
ENV VITE_BACKEND_URL=${VITE_BACKEND_URL}

#  Build the frontend app (creates /dist folder)
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine

RUN rm /etc/nginx/conf.d/default.conf

# Copy build files from stage 1
COPY --from=frontend-builder /app/dist /usr/share/nginx/html

# Permissions grant karein (Ye line crucial hai)
RUN chmod -R 755 /usr/share/nginx/html && chown -R nginx:nginx /usr/share/nginx/html

# Copy your custom nginx.conf
COPY  nginx.conf  /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
# ------------------------------------------------------------------------------
# ✅ Output: Optimized static files inside /app/dist
# Ready to be served via Nginx or any static server
# ------------------------------------------------------------------------------si
