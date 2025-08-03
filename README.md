# Static Site Server

This project demonstrates how to set up a simple Linux server using **AWS EC2** to serve a static website using **NGINX** and **rsync** for deployment.

![nginx](https://img.shields.io/badge/NGINX-009900?style=for-the-badge&logo=nginx&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![rsync](https://img.shields.io/badge/Rsync-000000?style=for-the-badge)

---

## 🌐 Live Server

You can view the static site hosted at:

**http://13.218.176.247**

---

## 📁 Project Structure

my-site/
├── index.html
├── style.css
├── images/
└── README.md
yaml

---

## 🚀 Technologies Used

- **AWS EC2** – Remote Linux server
- **NGINX** – Web server to serve static content
- **Rsync** – Deployment from local to remote server via SSH
- **Termux** – Local development and terminal emulator (Android)

---

## ⚙️ Setup Instructions

### 1. Launch AWS EC2 Instance

- Launch an Ubuntu instance.
- Open port **80 (HTTP)** in your security group.
- Save your keypair `.pem` file securely.

### 2. SSH into the Server

```bash
ssh -i ~/storage/downloads/my-new-key-pair.pem ubuntu@13.218.176.247

3. Install NGINX
sudo apt update
sudo apt install nginx -y

4. Serve Your Static Site
echo "Hello from NGINX on AWS!" | sudo tee /var/www/html/index.html
sudo systemctl restart nginx

5. Create Static Site Files
mkdir -p ~/my-site/images
cd ~/my-site
nano index.html
nano style.css

6. Upload via Rsync
rsync -avz -e "ssh -i ~/storage/downloads/my-new-key-pair.pem" ~/my-site/ ubuntu@13.218.176.247:/var/www/html/

🛠 Future Improvements
• Add SSL using Let's Encrypt
• Setup a custom domain name
• Use GitHub Actions for remote deployment
🔗 Project Link
https://github.com/GeigerJR/static-site-server
🔖 Reference
Inspired by the Static Site Server project on roadmap.sh
https://roadmap.sh/projects/static-site-server# Static Site Server

This project demonstrates how to set up a simple Linux server using **AWS EC2** to serve a static website using **NGINX** and **rsync** for deployment.

![nginx](https://img.shields.io/badge/NGINX-009900?style=for-the-badge&logo=nginx&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![rsync](https://img.shields.io/badge/Rsync-000000?style=for-the-badge)

---

## 🌐 Live Server

You can view the static site hosted at:

**http://13.218.176.247**

---

## 📁 Project Structure




---

## 🚀 Technologies Used

- **AWS EC2** – Remote Linux server
- **NGINX** – Web server to serve static content
- **Rsync** – Deployment from local to remote server via SSH
- **Termux** – Local development and terminal emulator (Android)

---

## ⚙️ Setup Instructions

### 1. Launch AWS EC2 Instance

- Launch an Ubuntu instance.
- Open port **80 (HTTP)** in your security group.
- Save your keypair `.pem` file securely.

### 2. SSH into the Server

```bash
ssh -i ~/storage/downloads/my-new-key-pair.pe
