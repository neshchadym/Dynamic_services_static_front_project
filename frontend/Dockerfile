# Step 1: Use Nginx as the base image
FROM nginx:alpine

# Step 2: Copy the static HTML files into Nginx's directory
COPY ./templates /usr/share/nginx/html

# Step 3: Expose port 80
EXPOSE 80

# Step 4: Start Nginx
CMD ["nginx", "-g", "daemon off;"]
