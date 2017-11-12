# Linux Server Configuration

Sixth project from Udacity's [Full-Stack Web Developer Nanodegree Program](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004).

### About
In this project I configured __Linux server__ hosted on AWS and deployed my __User Management App__ created in [Project 4](https://github.com/dimak1/udacity-fsnd-project4).

### Server Info
- Virtual Server: [Amazon Lightsail](https://amazonlightsail.com/)
- Public IP: 52.32.47.125
- SSH Port: 2200
- Live At: http://ec2-52-32-47-125.us-west-2.compute.amazonaws.com/

__NOTE:__ Below is summary of step taken to configure the server. Check __References__ section for details.

### High-Level Steps
1. Create new user, generate public key and login into server
2. Give new user permissions to sudo
3. Update packages and install needed for the project
4. Configure firewall
5. Install git and clone app that will be deployed
6. Ensure git folder is not accessible via web server
7. Update code with correct paths
8. Install PostgreSQL and add user/database
9. Setup and configure virtual environment
10. Configure virtual host with Amazon's servername
11. In Google's App, update 'Authorized JavaScript origins' with Amazon's url
12. Restart apache server and check if app is live

### Installed Packages

- apache2
- git
- libapache2-mod-wsgi
- PostgreSQL
- python3

### Firewall Configuration
Allow incoming connections for SSH (Port 2200), HTTP (Port 80), and NTP (Port 123)
```
$ sudo ufw allow 2200/tcp
$ sudo ufw allow 80/tcp
$ sudo ufw allow 123/udp
$ sudo ufw enable
```

#### References

- [Add and Delete Users](https://www.digitalocean.com/community/tutorials/how-to-add-and-delete-users-on-an-ubuntu-14-04-vps) from DigitalOcean
- [Update Packages](https://wiki.ubuntu.com/Security/Upgrades) from Ubuntu
- [Initial Server Setup](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-14-04) from DigitalOcean
- [Setup and deploy flask app](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps) from DigitalOcean
