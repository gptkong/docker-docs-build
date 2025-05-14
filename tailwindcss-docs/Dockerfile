# Use Node.js as the base image  
FROM node:22-alpine AS base  
  
# Install git and other dependencies  
RUN apk add --no-cache git  
  
# Install pnpm (package manager used in the project)  
RUN corepack enable && corepack prepare pnpm@latest --activate  
  
# Set working directory  
WORKDIR /app  
  
# Clone the repository  
RUN git clone https://github.com/tailwindlabs/tailwindcss.com.git .  
  
# Install dependencies  
RUN pnpm install --frozen-lockfile  
  
# Build the application  
RUN pnpm build  
  
# Expose port  
EXPOSE 3000  
  
# Set the command to run the application  
CMD ["pnpm","run", "start"]