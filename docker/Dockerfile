FROM ubuntu as builder

# Set destination for COPY
WORKDIR /app

ADD https://github.com/gohugoio/hugo/releases/download/v0.115.1/hugo_extended_0.115.1_linux-amd64.tar.gz hugo.tar.gz
RUN tar -zxf hugo.tar.gz
COPY . .
RUN ./hugo

FROM busybox:latest

# Create a non-root user to own the files and run our server
RUN adduser -D static
USER static
WORKDIR /home/static

# Copy the static website
# Use the .dockerignore file to control what ends up inside the image!
COPY --from=builder /app/public/ .

EXPOSE 80

# Run BusyBox httpd
CMD ["busybox", "httpd", "-f", "-v", "-p", "80"]

