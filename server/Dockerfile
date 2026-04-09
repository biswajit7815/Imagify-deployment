# ------------------------------------------------------------------------------
# 🏗️ Stage 1: Build Stage
# ------------------------------------------------------------------------------
# create a light-weight base image
FROM node:20-alpine AS backend-builder

# create a working directory
WORKDIR /app

# Build tools zaroori hain bcrypt jaise packages ke liye Alpine mein
RUN apk add --no-cache python3 make g++

# copy the package*.json files
COPY package*.json ./

# run the all dependencies
RUN npm install

# copy source code to working  directory
COPY . .

# ------------------------------------------------------------------------------
# 🚀 Stage 2: Production Stage
# ------------------------------------------------------------------------------

# create a light-weight image
FROM node:20-alpine

# create a working directory
WORKDIR /app

# only production dependencies are their no dev dependencies
ENV NODE_ENV=production

# add the user and group and set the permission it
RUN apk add --no-cache wget \
    && addgroup --system appgroup \
    && adduser -S appuser -G appgroup

# Builder se sirf files laayein
COPY --from=backend-builder --chown=appuser:appgroup /app ./

# Switch user
USER appuser

# expose the port
EXPOSE 4000

# Start the application
CMD ["node", "server.js"]
