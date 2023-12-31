############
#  Stage 1 #
############
FROM alpine as builder

RUN apk add hugo git

# Set destination for COPY
WORKDIR /app
COPY . .
# RUN git submodule add -f https://github.com/alex-shpak/hugo-book themes/hugo-book

RUN hugo

############
#  Stage 2 #
############
FROM busybox:latest as production

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

