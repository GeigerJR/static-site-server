<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Static Site Server</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
      background-color: #f8f9fa;
      color: #333;
    }
    h1, h2, h3 {
      color: #005f73;
    }
    code, pre {
      background-color: #e8e8e8;
      padding: 0.5em;
      border-radius: 5px;
      display: block;
      overflow-x: auto;
    }
    .badge {
      display: inline-block;
      margin-right: 10px;
      margin-bottom: 10px;
    }
    .section {
      margin-bottom: 40px;
    }
  </style>
</head>
<body>
  <h1>Static Site Server</h1>

  <p>This project demonstrates how to set up a simple Linux server using <strong>AWS EC2</strong> to serve a static website using <strong>NGINX</strong> and <strong>rsync</strong> for deployment.</p>

  <div class="section">
    <img class="badge" src="https://img.shields.io/badge/NGINX-009900?style=for-the-badge&logo=nginx&logoColor=white" alt="NGINX" />
    <img class="badge" src="https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS EC2" />
    <img class="badge" src="https://img.shields.io/badge/Rsync-000000?style=for-the-badge" alt="Rsync" />
  </div>

  <div class="section">
    <h2>🌐 Live Server</h2>
    <p>You can view the static site hosted at:<br><strong>http://[your-ec2-public-ip]</strong></p>
    <p><em>Replace with your actual EC2 public IP.</em></p>
  </div>

  <div class="section">
    <h2>📁 Project Structure</h2>
    <pre><code>my-site/
├── index.html
├── style.css
├── images/
└── README.md
</code></pre>
  </div>

  <div class="section">
    <h2>🚀 Technologies Used</h2>
    <ul>
      <li><strong>AWS EC2</strong> – Remote Linux server</li>
      <li><strong>NGINX</strong> – Web server to serve static content</li>
      <li><strong>Rsync</strong> – Deployment from local to remote server via SSH</li>
      <li><strong>Termux</strong> – Local development and terminal emulator (Android)</li>
    </ul>
  </div>

  <div class="section">
    <h2>⚙️ Setup Instructions</h2>
    <pre><code># 1. Launch AWS EC2 Instance
# - Use Ubuntu Server
# - Open port 80 (HTTP) in your security group
# - Download your .pem key pair

# 2. SSH into EC2 Server
ssh -i ~/storage/downloads/your-key.pem ubuntu@[your-ec2-public-ip]

# 3. Install NGINX
sudo apt update
sudo apt install nginx -y

# 4. Serve Static Site
echo "Hello from NGINX on AWS!" | sudo tee /var/www/html/index.html
sudo systemctl restart nginx

# 5. Create Site Files
mkdir -p ~/my-site/images
cd ~/my-site
nano index.html
nano style.css

# 6. Upload to Server Using Rsync
rsync -avz -e "ssh -i ~/storage/downloads/your-key.pem" ~/my-site/ ubuntu@[your-ec2-public-ip]:/var/www/html/
</code></pre>
  </div>

  <div class="section">
    <h2>🛠 Future Improvements</h2>
    <ul>
      <li>Add SSL with Let's Encrypt</li>
      <li>Point a custom domain</li>
      <li>Automate deployment with GitHub Actions</li>
    </ul>
  </div>

  <div class="section">
    <h2>🔗 Project Repository</h2>
    <p><strong>GitHub:</strong><br>
    <a href="https://github.com/GeigerJR/static-site-server" target="_blank">https://github.com/GeigerJR/static-site-server</a></p>
  </div>

  <div class="section">
    <h2>🔖 Reference</h2>
    <p>Project inspired by <a href="https://roadmap.sh/projects/static-site-server" target="_blank">roadmap.sh - Static Site Server Project</a></p>
  </div>
</body>
</html>
