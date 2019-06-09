
## Liberty docker images

**Download liberty latest image**

    docker pull websphere-liberty
**Build your Liberty image with version**

    docker build -t websphere-liberty:latest -t liberty:2.3 .
**Create container with your image**

    docker run -d --name libtest -p 9080:9080 liberty:2.3
