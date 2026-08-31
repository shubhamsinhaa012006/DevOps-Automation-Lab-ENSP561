# Use the official lightweight Nginx image based on Alpine Linux
# Alpine is chosen because of its extremely small footprint (~5MB),
# which reduces build time, storage space, and surface area for security vulnerabilities.
FROM nginx:alpine

# Add a label for maintainability (best practice)
LABEL maintainer="Shubham Sinha <2301010013>"
LABEL description="Experiment 03: Docker Containerization Lab"

# Copy the static website files from the host to the container's Nginx html directory.
# This creates a new image layer containing our custom application code.
COPY index.html /usr/share/nginx/html/
COPY style.css /usr/share/nginx/html/

# Expose port 80 to indicate that the container listens on this port at runtime.
# Note: EXPOSE is informational and does not publish the port on its own.
EXPOSE 80

# The default CMD for the nginx image is to start the nginx daemon.
# We explicitly define it here for clarity in a university lab setting.
# daemon off ensures Nginx runs in the foreground, keeping the container alive.
CMD ["nginx", "-g", "daemon off;"]
