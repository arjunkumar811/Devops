#  Week 2 - AWS Deployment using EC2

This week’s focus is on deploying a web application using **Amazon EC2** (Elastic Compute Cloud). Follow the steps below to successfully launch and access your project online.

---

## 🚀 Step 1: What is AWS?

**Amazon Web Services (AWS)** is a cloud computing platform that provides infrastructure as a service. It allows developers to deploy and scale applications without managing physical hardware.

---

## 💻 Step 2: EC2 Servers

**EC2 (Elastic Compute Cloud)** is a service that allows you to launch virtual servers in the cloud. These servers can host websites, applications, and more. You can choose OS, storage, and networking as per your requirements.

---

## 🛠️ Step 3: Creating a New EC2 Server

1. Go to [AWS Console](https://aws.amazon.com/console/).
2. Navigate to **EC2 > Instances > Launch Instance**.
3. Select an **Amazon Machine Image (AMI)** – e.g., Ubuntu 22.04 LTS.
4. Choose an instance type (e.g., **t2.micro** if you're on the free tier).
5. Create or choose a key pair (`.pem` file) – download it and keep it safe.
6. Configure security group:
   - Allow **SSH (port 22)** for terminal access.
   - Allow **HTTP (port 80)** and **HTTPS (port 443)** for web access.
7. Launch the instance.

---

## 🔐 Step 4: SSH into Server

Use your terminal to connect to the EC2 instance:

```bash
chmod 400 your-key.pem
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

> Replace `your-key.pem` with your actual key file and `your-ec2-public-ip` with the server’s public IP.

---

## 📦 Step 5: Install the Repo

Once logged into your server:

```bash
sudo apt update
sudo apt install git -y
git clone https://github.com/your-repo-url.git
cd your-repo-folder
sudo apt install nodejs npm -y
npm install
```

> Replace `your-repo-url` and `your-repo-folder` accordingly.

---

## 🌐 Step 6: Try Hitting the Server

Start your application:

```bash
npm start
```

By default, your app will run on port 3000. You can test it in your browser:

```
http://your-ec2-public-ip:3000
```

> Make sure your EC2 security group allows inbound traffic on port 3000 if you are testing directly.

---

## 🧭 Step 7: Setup NGINX

Install and configure NGINX as a reverse proxy:

```bash
sudo apt install nginx -y
sudo nano /etc/nginx/sites-available/default
```

Update the configuration:

```nginx
server {
    listen 80;
    server_name your-ec2-public-ip;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```

Save and exit the file, then restart NGINX:

```bash
sudo systemctl restart nginx
```

Now visit: `http://your-ec2-public-ip`

---

## 🔒 Step 8: Certificate Management (HTTPS)

Add SSL using Certbot and Let's Encrypt:

```bash
sudo apt install certbot python3-certbot-nginx -y
sudo certbot --nginx
```

Follow the prompts to generate and install the SSL certificate. Once done, your app will be accessible securely at:

```
https://your-ec2-public-ip
```

> Ensure port 443 is allowed in the security group.

---

## ✅ You're Live!

You’ve successfully:
- Launched an EC2 instance
- Cloned and installed a Node.js repo
- Set up NGINX as a reverse proxy
- Secured your site with HTTPS

---

## 📚 References

- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [NGINX Configuration Guide](https://www.nginx.com/resources/wiki/start/)
- [Certbot Setup Guide](https://certbot.eff.org/)

---

Happy Deploying 🚀
