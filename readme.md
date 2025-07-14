## Description
This readme describes the process of deploying and running a Java app on DigitalOcean.
## Part 1 Create droplet and deploy Java app.

1. Create Droplet
2. Create Firewall
3. SSH into droplet
```sh 
   ssh root@<ip> -i <key>
```
4. Install Java
```sh 
   apt update 
```
type java to see whats available (install Java 8
```sh 
  apt install openjdk-8-jre-headless)
```
5. Build Java project
```sh
    gradle build
```
6. Secure Copy jar file
```sh 
    scp build/libs/java-react-example.jar root@164.92.138.35:/root
```
7. run jar file (detached)
```sh 
    java -jar java-react-example.jar & 
```
8. Open port 7071 in firewall
9. Check if java process is running: ``` ps aux | grep java ```
10. Install netstat and check for servers with active internet connections
    ```netstat -lpnt```

## Part 2 - Create droplet and deploy Java app.
1. add user + sudo permission
```sh
  adduser jay
  usermod -aG sudo jay
```
3. add public key to /home/jay (copy and paste)
```sh 
  mkdir .ssh
  sudo vim .ssh/authorized_keys
```

<hr/>
Original project can be found here: https://github.com/pmendelski/java-react-example 
