# Docker

- When we build an app on our laptop:
- It works because our laptop has Python installed, right version, right libraries.
- But our  teammate’s laptop might be Windows, or have Python 3.10 instead of 3.8 — your app breaks.
- Same when we deploy to AWS → we want it to run exactly the same as it did locally.

- The base OS -> Where to start → FROM
- Files -> What to add → COPY
- Dependencies -> What to run → RUN
- Command to run -> How to start → CMD

# Why Dockerfile?

- Because it turns project folder into a repeatable image.
- If we have 10 devs → we don’t want to say “install Python, then install Flask, then set env vars…”
  we just say: “Build this Dockerfile.” Done.

# Build Image

- $ docker build -t flask-demo .

- we build image once → we get a frozen snapshot of our app’s environment.

# Run container

- $ docker run -d -p 5000:5000 flask-demo

- mapping container port 5000 to machine port 5000

# Why Docker Hub

- To share our  image with others.
- To use the image in CI/CD → Jenkins pulls it.
- To deploy to Kubernetes → K8s pulls it.

# Why docker-compose

- One container is rarely enough.
- Example:
- Flask app needs a database.
- our app alone is useless if DB isn’t there.
- Compose lets you say:

- Spin up web container + DB container → wire them up → same network.

- $ docker-compose up -d

# Why Volumes

- By default → containers are ephemeral → delete container = lose data.

- Example:
- MySQL container → stop → your database is gone.
- So you mount a volume → data lives outside the container → safe even if container dies.

# Why we need Docker in DevOps

- we containerize apps → so developers ship same environment everywhere.
- we push image to Docker Hub → so Jenkins / Kubernetes can pull it automatically.
- we use Compose → for local dev or simple multi-container apps.
- we deploy → K8s orchestrates the containers → auto scaling, load balancing.



