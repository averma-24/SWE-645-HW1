# Use the latest nginx image as the base image
FROM nginx:latest

# Copy the HTML and CSS files into the container
COPY index.html /usr/share/nginx/html/
COPY studentFormStyle.css /usr/share/nginx/html/

# Expose port 80 for HTTP traffic
EXPOSE 80

# Start the nginx server and keep it running
CMD ["nginx", "-g", "daemon off;"]