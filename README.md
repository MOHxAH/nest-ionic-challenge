NestJS Ionic Application
How to Run the Application 
Step 1: Run the Application
Try running the application using Docker Compose:

In the root of your project, run: docker-compose up
If it works, your application will be accessible at http://localhost:3000.

Step 2: Handle Port 3000 Already in Use
If port 3000 is already in use, follow these steps:

Check which process is using port 3000: lsof -i :3000
Example output:
COMMAND   PID   USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
node    10423 moh_ah   23u  IPv6 0xf4b2815a80e01415      0t0  TCP *:hbci (LISTEN)

Kill the process using the port:
kill -9 <PID>
Replace <PID> with the actual process ID from the output.

Rerun Docker Compose: docker-compose up

Step 4: Run from Docker Hub (If Docker Compose Fails)
If Docker Compose doesn't work, you can pull and run the image directly from Docker Hub:

Pull and run the image: docker run -p 3000:3000 moh0ah/nest-ionic-image
If port 3000 is in use, follow the same steps above to free the port or change the port:
docker run -p 8899:3000 moh0ah/nest-ionic-image