# My DevOps Application

A  DevOps demonstration project showcasing modern deployment practices using Git, GitHub, GitHub Pages, and AWS EC2 with Nginx.

##  Table of Contents

- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [What We Built](#what-we-built)
- [Development Workflow](#development-workflow)
- [Deployment Strategies](#deployment-strategies)
- [Live URLs](#live-urls)

##  Project Overview

This project demonstrates a complete DevOps workflow from local development to production deployment. We created a simple web application and deployed it using two different methods to understand various deployment strategies and their use cases.

## 🛠 Technologies Used

- **Version Control:** Git
- **Repository Hosting:** GitHub
- **Static Hosting:** GitHub Pages
- **Cloud Infrastructure:** AWS EC2 (Ubuntu 22.04 LTS)
- **Web Server:** Nginx
- **Languages:** HTML5, CSS3

##  What We Built

We created a responsive web application featuring a modern gradient background, centered content card, and a footer. The application is designed to be simple yet visually appealing, demonstrating proper HTML structure and CSS styling practices.

##  Development Workflow

### Local Development

We started by setting up Git on our local machine, configuring our identity with name and email. Then we initialized a new Git repository in our project directory and created the basic project structure with HTML and CSS files.

We practiced proper version control by making regular commits as we developed features. We used Git's branching feature to work on new features in isolation, creating feature branches for additions like the footer component. After completing work on a feature branch, we merged it back into the main branch.

### GitHub Collaboration

After completing our local development, we created a remote repository on GitHub to host our code. We connected our local repository to GitHub and pushed all our commits to the remote repository.

We practiced collaborative workflows by creating pull requests. When adding new features, we pushed feature branches to GitHub, created pull requests with descriptions of the changes, reviewed the code changes, and merged them through the GitHub interface. This workflow simulates real-world team collaboration where code is reviewed before being merged into production.

##  Deployment Strategies

We deployed this application using two different methods to understand the strengths and use cases of each approach.

### GitHub Pages Deployment

GitHub Pages is a free static site hosting service that deploys directly from your GitHub repository. We configured it by enabling GitHub Pages in our repository settings, selecting the main branch as the source, and specifying the root directory as the deployment folder.

**How It Works:**

GitHub Pages automatically detects when changes are pushed to the main branch and rebuilds the site. The deployment process is completely automated - we simply push our changes to GitHub, and within 1-2 minutes, the updated site is live.

**Best For:**

GitHub Pages is ideal for static websites, documentation sites, portfolios, and frontend applications that don't require server-side processing. It's perfect for this project since we only have HTML and CSS files.

**Advantages:**

- Completely free for public repositories
- Automatic deployment on every push
- No server management required
- Built-in SSL/HTTPS support
- Fast global CDN delivery

**Limitations:**

- Only static files are supported
- No server-side code execution
- No database support
- Limited to 1GB repository size
- 100GB bandwidth per month

### AWS EC2 Deployment

AWS EC2 provides virtual servers in the cloud, giving us full control over the server environment. This deployment method involved several steps to set up a production-ready web server.

**Setting Up the Infrastructure:**

We started by launching an EC2 instance through the AWS Console. We chose Ubuntu Server 22.04 LTS as our operating system and selected the t2.micro instance type, which is eligible for AWS's free tier. During setup, we created a new SSH key pair for secure access to the server and configured security groups to allow web traffic on ports 80 (HTTP) and 443 (HTTPS), as well as SSH access on port 22.

**Securing Access:**

After launching the instance, we downloaded the private key file and set proper permissions to ensure it's secure. We then used SSH to connect to our server remotely, which gave us command-line access to manage the server.

**Installing the Web Server:**

Once connected, we updated the system packages to ensure we had the latest security patches. We then installed Nginx, a high-performance web server known for its efficiency and reliability. Nginx was configured to start automatically when the server boots, ensuring our application stays online even after server restarts.

**Deploying the Application:**

We installed Git on the EC2 instance to clone our repository directly from GitHub. We navigated to Nginx's web root directory, backed up the default welcome page, and cloned our application repository. After moving the files to the proper location, we set correct file permissions to ensure the web server could read and serve our files.

**Testing the Deployment:**

After deployment, we accessed the server's public IP address through a web browser and confirmed that our application loaded correctly with all styling intact.

**Creating an Automated Deployment Script:**

To streamline future updates, we created a shell script that automates the entire deployment process. This script pulls the latest changes from GitHub, sets proper file permissions, and restarts Nginx to apply the updates. Now, whenever we push changes to GitHub, we can deploy them to our EC2 server by simply running this one script.

**How It Works:**

When we want to update the live site, we make changes locally, commit them to Git, and push to GitHub. Then we SSH into our EC2 instance and run our deployment script. The script pulls the latest code from GitHub, ensures all permissions are correct, and restarts the web server. The entire update process takes less than a minute.

**Best For:**

EC2 is ideal for applications that need server-side processing, database integration, custom server configurations, or the ability to scale resources up or down based on demand. It's perfect for production applications that require full control over the hosting environment.

**Advantages:**

- Complete control over server configuration
- Can run any software or programming language
- Supports databases and backend services
- Scalable resources (can upgrade instance size)
- Production-grade infrastructure
- Can install and configure any web server
- Supports complex deployment workflows

**Considerations:**

- Requires server management and maintenance
- Need to handle security updates and patches
- More expensive than static hosting options
- Requires knowledge of Linux server administration
- Responsible for monitoring and backups

##  Deployment Workflow

### GitHub Pages Updates

Updating the GitHub Pages deployment is straightforward. We make changes to our code locally, commit them to Git, and push to the main branch on GitHub. GitHub automatically detects the new commits and redeploys the site within 1-2 minutes. No additional steps are required.

### EC2 Updates

For EC2 updates, after pushing our code to GitHub, we connect to our EC2 instance via SSH and run our deployment script. The script handles everything automatically: pulling the latest code, setting permissions, and restarting the web server. This gives us control over exactly when updates go live in production.

##  What We Learned

Through this project, we gained hands-on experience with:

- Version control best practices using Git
- Collaborative development workflows with GitHub
- Pull request workflows for code review
- Static site deployment with GitHub Pages
- Cloud infrastructure setup on AWS
- Linux server administration basics
- Web server configuration with Nginx
- Automated deployment scripting
- Understanding different deployment strategies and their trade-offs

##  Comparing Deployment Methods

**GitHub Pages** is perfect for simple static websites where you want zero maintenance and automatic deployments. It's free, fast, and handles everything for you.

**AWS EC2** provides the flexibility and power needed for complex applications that require server-side processing, databases, or custom configurations. It requires more setup and maintenance but offers complete control.

For this project, both methods work well since we have a static site. In a real-world scenario, you'd choose based on your application's requirements and your team's infrastructure needs.

##  Live URLs

**GitHub Pages:** https://furaha123.github.io/my-devops-app/

**AWS EC2:** http://13.222.119.235/

---

##  Project Status

This project is complete and serves as a demonstration of DevOps deployment practices. Both deployment methods are functional and can be accessed via the URLs above.

##  Author

**Your Name**
- GitHub: [@Furaha123](https://github.com/Furaha123)

##  License

This project is open source and available for educational purposes.

---
