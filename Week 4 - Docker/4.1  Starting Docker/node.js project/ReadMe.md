# Docker End to End - Step 1 to Step 22 📚

## Master Docker: From Beginner to Expert

---

# Step 1 - Why Docker?

Docker revolutionizes application development through containerization. Here's why it's essential:

## 🚀 Kubernetes & Container Orchestration

Docker containers are the foundation for Kubernetes, enabling scalable applications with automatic load balancing, rolling updates, and self-healing capabilities.

## 🔒 Isolated Process Environments

Containers provide complete isolation with dedicated resources, enhanced security, and consistent environments across all platforms - eliminating "works on my machine" issues.

## 💻 Local Development & Services

Start complex applications instantly with `docker-compose up`. Run databases, microservices, and entire architectures locally without complex installations.

## Key Benefits

✅ **Portable** - Build once, run anywhere  
✅ **Efficient** - Lightweight vs virtual machines  
✅ **Consistent** - Same environment everywhere  
✅ **Fast** - Quick setup and deployment

```bash
# Get started
docker run hello-world
docker-compose up -d
```

Docker makes deployment faster, more reliable, and easier to manage at scale.

---

# Step 2 - Containerization

## What are Containers?

Containers are a way to package and distribute software applications that makes them easy to deploy and run consistently across different environments. They allow you to package an application, along with all its dependencies and libraries, into a single unit that can be run on any machine with a container runtime, such as Docker.

## Why Containers?

### The Problem

- **Different Operating Systems** - Everyone has different OS environments
- **Varying Setup Steps** - Installation procedures differ based on OS
- **Dependency Hell** - Extremely harder to keep track of dependencies as projects grow

### Benefits of Using Containers

✅ **Single Configuration File** - Describe your entire setup in one file  
✅ **Isolated Environments** - Run applications without conflicts  
✅ **Easy Local Setup** - Makes local setup of projects a breeze  
✅ **Simple Auxiliary Services** - Installing databases and services is effortless

## Example

For reference, this single command starts MongoDB on **all operating systems**:

```bash
docker run -d -p 27017:27017 mongo
```

> **Note**: Docker isn't the only way to create containers, but it's the most popular and widely adopted solution.

---

# Step 3 - History of Docker

Docker is a Y Combinator backed company that started around **2014**. The founders envisioned a world where containers would become mainstream and people would deploy their applications using them.

**That vision is mostly true today.**

Most projects you find on GitHub will (and should) have Docker files in them - providing a standardized way to create and run containers for any application.

Docker's success has transformed how we think about application deployment, making containerization the industry standard for modern software development.

**Reference**: [Y Combinator Interview with Solomon Hykes (Docker Founder)](https://www.ycombinator.com/blog/solomon-hykes-docker-dotcloud-interview/)

---

# Step 4 - Installing Docker

To get started with Docker, you need to install Docker Engine on your machine.

## Installation

Follow the official Docker installation guide for your operating system:

**📖 [Docker Installation Guide](https://docs.docker.com/engine/install/)**

The guide provides step-by-step instructions for:

- Windows
- macOS
- Linux (Ubuntu, Debian, CentOS, etc.)

## Verify Installation

After installation, make sure you can run the Docker CLI locally by testing these commands:

```bash
# Check Docker version
docker --version

# Verify Docker is running
docker run hello-world
```

If both commands work successfully, you're ready to start using Docker! 🎉

---

# Step 5 - Inside Docker

As an application/full stack developer, you need to be comfortable with these key terminologies:

## 1. Docker Engine

Docker Engine is an open-source containerization technology that allows developers to package applications into containers.

Containers are standardized executable components combining application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.

## 2. Docker CLI

The command line interface lets you talk to the Docker Engine and lets you start/stop/list containers.

```bash
docker run -d -p 27017:27017 mongo
```

> 💡 **Note**: Docker CLI is not the only way to talk to a Docker Engine. You can hit the Docker REST API to do the same things.

## 3. Docker Registry

The Docker registry is how Docker makes money. It's similar to GitHub, but it lets you push **images** rather than source code.

- **Docker's main registry**: [Docker Hub](https://dockerhub.com/)
- **Example**: [MongoDB image on Docker Hub](https://hub.docker.com/_/mongo)

The registry allows developers to share and distribute containerized applications globally.

---

# Step 6 - Images vs Containers

Understanding the difference between Docker images and containers is crucial for working with Docker effectively.

## Docker Image

A Docker image is a lightweight, standalone, executable package that includes everything needed to run a piece of software, including the code, a runtime, libraries, environment variables, and config files.

> 💡 **Mental Model**: Think of an image as **your codebase on GitHub** - it's the blueprint/template that contains all the instructions and files needed.

## Docker Container

A container is a running instance of an image. It encapsulates the application or service and its dependencies, running in an isolated environment.

> 💡 **Mental Model**: Think of a container as **when you run `node index.js` on your machine** from source code you got from GitHub - it's the actual running process.

## Key Difference

- **Image** = The blueprint/template (like source code)
- **Container** = The running instance (like an executing process)

You can create multiple containers from the same image, just like you can run the same code multiple times on different machines.

---

# Step 7 - Port Mapping

Port mapping allows you to connect your host machine's ports to container ports, enabling external access to services running inside containers.

## Understanding Port Mapping

When you run a container, it operates in an isolated environment with its own network. To access services running inside the container from your host machine (or external networks), you need to map ports.

## Port Mapping Syntax

```bash
docker run -d -p [HOST_PORT]:[CONTAINER_PORT] [IMAGE_NAME]
```

- **HOST_PORT**: The port on your local machine
- **CONTAINER_PORT**: The port inside the container where the service is running

## Example: MongoDB Port Mapping

```bash
docker run -d -p 27018:27017 mongo
```

**What this does:**

- Runs MongoDB container in the background (`-d`)
- Maps port `27018` on your host machine to port `27017` inside the container
- MongoDB typically runs on port `27017` inside the container
- You can now connect to MongoDB using `localhost:27018`

## Key Benefits

✅ **Avoid Port Conflicts** - Run multiple services without port collisions  
✅ **Custom Port Assignment** - Use any available port on your host  
✅ **Service Isolation** - Each container can use standard ports internally  
✅ **External Access** - Allow other machines to connect to your containerized services

## Multiple Port Mapping

You can map multiple ports in a single command:

```bash
docker run -d -p 3000:3000 -p 8080:80 my-web-app
```

This maps both port 3000 and 8080 from host to different container ports.

---

# Step 8 - Common Docker Commands

Here are the essential Docker commands every developer should know:

## 1. `docker images`

Shows you all the images that you have on your machine.

```bash
docker images
```

**Output:** Lists all locally stored Docker images with their repository, tag, image ID, creation date, and size.

## 2. `docker ps`

Shows you all the containers you are running on your machine.

```bash
# Show running containers
docker ps

# Show all containers (including stopped ones)
docker ps -a
```

**Output:** Displays container ID, image, command, creation time, status, ports, and names.

## 3. `docker run`

Lets you start a container from an image.

```bash
docker run [OPTIONS] IMAGE [COMMAND]
```

**Common Options:**

- `-p` → Create a port mapping
- `-d` → Run in detached mode (background)
- `--name` → Assign a custom name to container

```bash
# Example
docker run -d -p 3000:3000 --name my-app node:latest
```

## 4. `docker build`

Lets you build an image from a Dockerfile.

```bash
docker build -t my-image:tag .
```

> **Note:** We'll explore this in detail when we learn to create Dockerfiles.

## 5. `docker push`

Lets you push your image to a registry (like Docker Hub).

```bash
docker push username/image-name:tag
```

## 6. Extra Essential Commands

### `docker kill`

Forcefully stop a running container:

```bash
docker kill container-name-or-id
```

### `docker exec`

Execute commands inside a running container:

```bash
docker exec -it container-name bash
```

**Quick Reference Card:**

- `docker images` → List images
- `docker ps` → List containers
- `docker run` → Start container
- `docker build` → Build image
- `docker push` → Upload to registry
- `docker kill` → Stop container
- `docker exec` → Run commands in container

---

# Step 9 - Dockerfile

## What is a Dockerfile?

If you want to create an image from your own code that you can push to Docker Hub, you need to create a **Dockerfile** for your application.

A Dockerfile is a text document that contains all the commands a user could call on the command line to create an image.

## How to Write a Dockerfile

A Dockerfile has **2 main parts:**

1. **Base Image** - The foundation image to build upon
2. **Commands** - Instructions that run on the base image (to install dependencies like Node.js)

## Common Dockerfile Commands

### `FROM`

Specifies the base image to use:

```dockerfile
FROM node:16-alpine
```

### `WORKDIR`

Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY instructions that follow it:

```dockerfile
WORKDIR /app
```

### `COPY`

Allows files from the Docker host to be added to the Docker image:

```dockerfile
COPY . .
COPY package.json .
```

### `RUN`

Executes any commands in a new layer on top of the current image and commits the results:

```dockerfile
RUN npm install
RUN apt-get update && apt-get install -y curl
```

### `EXPOSE`

Informs Docker that the container listens on the specified network ports at runtime:

```dockerfile
EXPOSE 3000
```

### `ENV`

Sets environment variables:

```dockerfile
ENV NODE_ENV=production
ENV PORT=3000
```

### `CMD`

Provides defaults for executing a container. There can only be **one CMD** instruction in a Dockerfile:

```dockerfile
CMD ["node", "index.js"]
CMD ["npm", "start"]
```

## Example Dockerfile

Here's a complete Dockerfile for a Node.js application:

```dockerfile
# Use Node.js 16 with Alpine Linux as base image
FROM node:16-alpine

# Set working directory inside container
WORKDIR /app

# Copy package files first (for better caching)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy application code
COPY . .

# Expose port 3000
EXPOSE 3000

# Set environment variable
ENV NODE_ENV=production

# Command to run when container starts
CMD ["node", "index.js"]
```

## Build Your Image

Once you have a Dockerfile, build your image with:

```bash
docker build -t my-app:latest .
```

The `.` at the end tells Docker to look for the Dockerfile in the current directory.

---

# Step 10 - Building Images

Now that you have a Dockerfile in your project, let's build a Docker image from it!

## Build Your Image

Use the `docker build` command to create an image from your Dockerfile:

```bash
docker build -t image_name .
```

**Example:**

```bash
docker build -t hello-app .
```

- `-t hello-app` → Tags your image with the name "hello-app"
- `.` → Tells Docker to look for Dockerfile in current directory

## Verify Your Image

After building, check that your new image was created:

```bash
docker images
```

You should see your newly created image in the list!

**Example output:**

```
REPOSITORY    TAG       IMAGE ID       CREATED          SIZE
hello-app     latest    abc123def456   2 minutes ago    125MB
node          16-alpine fed456ghi789   2 weeks ago      110MB
```

## 💡 Pro Tip: Use .dockerignore

Create a `.dockerignore` file to prevent unnecessary files from being copied to your Docker image:

```dockerignore
node_modules
npm-debug.log
.git
.gitignore
README.md
.env
.nyc_output
coverage
.DS_Store
```

**Why use .dockerignore?**

✅ **Faster Builds** - Excludes large directories like `node_modules`  
✅ **Smaller Images** - Reduces final image size  
✅ **Better Security** - Prevents sensitive files from being included  
✅ **Cleaner Builds** - Only copies what you actually need

## Best Practices

- **Use specific tags** instead of `latest` for production
- **Layer caching** - Copy `package.json` first, then run `npm install`, then copy source code
- **Multi-stage builds** for production optimization
- **Always use .dockerignore** to exclude unnecessary files

```bash
# Good practice - with version tag
docker build -t my-app:v1.0.0 .

# Even better - with registry prefix
docker build -t myregistry/my-app:v1.0.0 .
```

---

# Step 11 - Running Images

Now that you've built your Docker image, it's time to run it as a container!

## Basic Run Command

Use the `docker run` command to start a container from your image:

```bash
docker run -p 3000:3000 image_name
```

**Example:**

```bash
docker run -p 3000:3000 hello-app
```

## What This Does

- **Creates a container** from your image
- **Maps port 3000** on your host to port 3000 in the container
- **Starts the application** inside the container

## Test Your Application

After running the command, visit **http://localhost:3000** in your browser.

You should see your application running! 🎉

## Common Run Options

### Run in Background (Detached Mode)

```bash
docker run -d -p 3000:3000 hello-app
```

### Run with Custom Name

```bash
docker run -d -p 3000:3000 --name my-app hello-app
```

### Run with Environment Variables

```bash
docker run -d -p 3000:3000 -e NODE_ENV=production hello-app
```

### Run with Volume Mount

```bash
docker run -d -p 3000:3000 -v $(pwd):/app hello-app
```

## Manage Running Containers

### List Running Containers

```bash
docker ps
```

### Stop a Container

```bash
docker stop container-name-or-id
```

### Remove a Container

```bash
docker rm container-name-or-id
```

### View Container Logs

```bash
docker logs container-name-or-id
```

## Example Workflow

1. **Build your image:**

   ```bash
   docker build -t hello-app .
   ```

2. **Run the container:**

   ```bash
   docker run -d -p 3000:3000 --name my-hello-app hello-app
   ```

3. **Visit your app:** Open http://localhost:3000

4. **Check logs:**

   ```bash
   docker logs my-hello-app
   ```

5. **Stop when done:**
   ```bash
   docker stop my-hello-app
   ```

## Port Mapping Reminder

- **Host Port:Container Port** format
- Use different host ports to avoid conflicts
- Example: `-p 8080:3000` maps host port 8080 to container port 3000

Your containerized application is now running! 🚀

---

# Step 12 - Passing Environment Variables

Environment variables are essential for configuring your containerized applications. Docker makes it easy to pass environment variables to your containers.

## Basic Environment Variable Syntax

Use the `-e` flag to pass environment variables:

```bash
docker run -p 3000:3000 -e VARIABLE_NAME="value" image_name
```

## Real-World Example

Here's how to pass a database URL to your Node.js application:

```bash
docker run -p 3000:3000 -e DATABASE_URL="postgres://avnadmin:AVNS_EeDiMIdW-dNT4Ox9l1n@pg-35339ab4-harkirat-d1b9.a.aivencloud.com:25579/defaultdb?sslmode=require" hello-app
```

## Multiple Environment Variables

You can pass multiple environment variables:

```bash
docker run -p 3000:3000 \
  -e NODE_ENV="production" \
  -e DATABASE_URL="postgres://user:pass@localhost:5432/db" \
  -e PORT="3000" \
  -e API_KEY="your-secret-key" \
  hello-app
```

## Using Environment Variables in Node.js

In your Node.js application, access these variables through `process.env`:

```javascript
const express = require("express");
const app = express();

// Access environment variables
const port = process.env.PORT || 3000;
const databaseUrl = process.env.DATABASE_URL;
const nodeEnv = process.env.NODE_ENV || "development";

console.log(`Running in ${nodeEnv} mode`);
console.log(`Database URL: ${databaseUrl}`);

app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
```

## Environment File Alternative

For many variables, create a `.env` file:

```bash
# .env file
NODE_ENV=production
DATABASE_URL=postgres://user:pass@localhost:5432/db
PORT=3000
API_KEY=your-secret-key
```

Then use `--env-file`:

```bash
docker run -p 3000:3000 --env-file .env hello-app
```

## Security Best Practices

### ✅ Do:

- Use environment variables for configuration
- Keep sensitive data in `.env` files (not in code)
- Use Docker secrets for production
- Validate environment variables in your app

### ❌ Don't:

- Hardcode secrets in Dockerfile
- Commit `.env` files to version control
- Use environment variables for large data
- Expose sensitive variables in logs

## Common Environment Variables

```bash
# Development
docker run -p 3000:3000 -e NODE_ENV="development" hello-app

# Production
docker run -p 3000:3000 -e NODE_ENV="production" hello-app

# With debugging
docker run -p 3000:3000 -e DEBUG="app:*" hello-app

# With custom port
docker run -p 8080:8080 -e PORT="8080" hello-app
```

## Docker Compose Alternative

For complex applications, use `docker-compose.yml`:

```yaml
version: "3.8"
services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
      - DATABASE_URL=postgres://user:pass@db:5432/mydb
      - PORT=3000
```

Environment variables make your containers flexible and configurable! 🔧

---

# Step 13 - More Commands

Beyond the basic Docker commands, there are several powerful commands for managing and debugging containers.

## `docker kill` - Forcefully Stop Containers

The `docker kill` command immediately terminates a running container:

```bash
docker kill <container_name_or_id>
```

**Examples:**

```bash
# Kill by container name
docker kill my-app

# Kill by container ID
docker kill abc123def456

# Kill multiple containers
docker kill container1 container2 container3
```

### Difference: `docker stop` vs `docker kill`

- **`docker stop`** - Gracefully stops container (sends SIGTERM, then SIGKILL after timeout)
- **`docker kill`** - Immediately terminates container (sends SIGKILL)

## `docker exec` - Execute Commands Inside Containers

The `docker exec` command runs commands inside a running container:

```bash
docker exec <container_name_or_id> <command>
```

## Common `docker exec` Examples

### List Contents of a Container Directory

```bash
docker exec <container_name_or_id> ls /path/to/directory
```

**Real examples:**

```bash
# List files in the app directory
docker exec my-app ls /app

# List files in the root directory
docker exec my-app ls /

# List files with detailed info
docker exec my-app ls -la /app
```

### Running an Interactive Shell

```bash
docker exec -it <container_name_or_id> /bin/bash
```

**Examples:**

```bash
# Access bash shell in container
docker exec -it my-app /bin/bash

# For Alpine Linux containers (use sh instead of bash)
docker exec -it my-app /bin/sh

# Access shell with specific user
docker exec -it --user root my-app /bin/bash
```

### Other Useful Commands

```bash
# Check Node.js version inside container
docker exec my-app node --version

# View environment variables
docker exec my-app env

# Check running processes
docker exec my-app ps aux

# View file contents
docker exec my-app cat /app/package.json

# Install packages (temporary - lost when container stops)
docker exec my-app npm install lodash

# Check disk usage
docker exec my-app df -h

# Check memory usage
docker exec my-app free -h
```

## Interactive Shell Session

When you run `docker exec -it`, you get an interactive terminal:

```bash
docker exec -it my-app /bin/bash
```

Inside the container, you can:

```bash
# Navigate directories
cd /app

# Edit files (if editors are installed)
nano index.js

# Run Node.js commands
node -e "console.log('Hello from inside container!')"

# Check logs
tail -f /var/log/app.log

# Exit the container shell
exit
```

## Flags Explained

- **`-i`** (interactive) - Keep STDIN open
- **`-t`** (tty) - Allocate a pseudo-TTY
- **`-it`** - Combined: interactive terminal session

## Debugging Workflow

```bash
# 1. List running containers
docker ps

# 2. Access the container shell
docker exec -it my-app /bin/bash

# 3. Debug inside the container
cd /app
ls -la
cat package.json
npm list

# 4. Exit when done
exit

# 5. Kill container if needed
docker kill my-app
```

## Best Practices

### ✅ Do:

- Use `docker exec` for debugging and inspection
- Use `docker kill` only when containers are unresponsive
- Prefer `docker stop` for graceful shutdowns
- Use `-it` flags for interactive sessions

### ❌ Don't:

- Use `docker exec` to make permanent changes (they're lost when container stops)
- Use `docker kill` as the default way to stop containers
- Leave interactive sessions running unnecessarily

These commands are essential for container debugging and management! 🛠️

---

# Step 14 - Pushing to DockerHub

Once you've created your image, you can push it to DockerHub to share it with the world! DockerHub is like GitHub for Docker images.

## Step 1: Sign Up to DockerHub

1. Go to [https://hub.docker.com/](https://hub.docker.com/)
2. Click "Sign Up" and create your account
3. Verify your email address
4. Remember your username - you'll need it for pushing images

## Step 2: Create a New Repository

1. **Login to DockerHub** in your browser
2. **Click "Create Repository"**
3. **Fill in the details:**
   - Repository name: `hello-app` (or your preferred name)
   - Description: Brief description of your app
   - Visibility: Public (free) or Private (paid)
4. **Click "Create"**

## Step 3: Login to Docker CLI

Login to DockerHub from your terminal:

```bash
docker login
```

### If you have 2FA enabled:

You'll need to create an **Access Token** instead of using your password:

1. Go to [DockerHub Account Settings](https://hub.docker.com/settings/security)
2. Click "New Access Token"
3. Give it a name (e.g., "My Development Machine")
4. Click "Generate"
5. Copy the token and use it as your password when prompted

**Reference:** [Docker Access Tokens Documentation](https://docs.docker.com/security/for-developers/access-tokens/)

## Step 4: Tag Your Image

Before pushing, tag your image with your DockerHub username:

```bash
docker tag local-image-name your_username/your_reponame:tagname
```

**Examples:**

```bash
# Tag with latest
docker tag hello-app arjunkumar811/hello-app:latest

# Tag with specific version
docker tag hello-app arjunkumar811/hello-app:v1.0.0

# Tag with multiple tags
docker tag hello-app arjunkumar811/hello-app:latest
docker tag hello-app arjunkumar811/hello-app:v1.0.0
```

## Step 5: Push to DockerHub

Push your tagged image to DockerHub:

```bash
docker push your_username/your_reponame:tagname
```

**Examples:**

```bash
# Push latest version
docker push arjunkumar811/hello-app:latest

# Push specific version
docker push arjunkumar811/hello-app:v1.0.0

# Push all tags at once
docker push arjunkumar811/hello-app --all-tags
```

## Complete Example Workflow

```bash
# 1. Build your image
docker build -t hello-app .

# 2. Tag for DockerHub
docker tag hello-app arjunkumar811/hello-app:v1.0.0

# 3. Login to DockerHub
docker login

# 4. Push to DockerHub
docker push arjunkumar811/hello-app:v1.0.0
```

## Verify Your Push

1. Go to your DockerHub repository page
2. You should see your image with the tag
3. Others can now pull your image:

```bash
docker pull arjunkumar811/hello-app:v1.0.0
```

## Best Practices for DockerHub

### ✅ Do:

- **Use semantic versioning** (v1.0.0, v1.1.0, etc.)
- **Write good descriptions** in your repository
- **Add README.md** to your DockerHub repo
- **Use meaningful tags** (not just "latest")
- **Keep images small** with multi-stage builds

### ❌ Don't:

- **Include secrets** in your images
- **Use only "latest" tag** in production
- **Push unnecessarily large images**
- **Forget to update documentation**

## Common Issues & Solutions

### Issue: "Access Denied"

**Solution:** Make sure repository exists and you have push permissions

### Issue: "Image does not exist locally"

**Solution:** Tag your image with the correct name first

### Issue: "Login failed"

**Solution:** Use access token instead of password if 2FA is enabled

## Example Repository Structure

Your DockerHub repository will show:

- **Image tags** (latest, v1.0.0, etc.)
- **Pull command** for others to use
- **Image size** and layers
- **Last updated** timestamp

Now your Docker image is available worldwide! 🌍
