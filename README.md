<div id="hero">
  <p align="center" dir="auto">
      <a href="https://fleetbase.io" rel="nofollow">
        <img src="https://user-images.githubusercontent.com/58805033/191936702-fed04b0f-7966-4041-96d0-95e27bf98248.png" alt="Fleetbase logo" width="500" height="120" style="max-width: 100%;">
      </a>
    </p>
    <p align="center" dir="auto">
      Modular logistics and supply chain operating system
      <br>
      <a href="https://docs.fleetbase.io/" rel="nofollow" target="_fleetbase_docs">Documentation</a>
      ·
      <a href="https://console.fleetbase.io" rel="nofollow" target="_fleetbase_console">Cloud Version</a>
      ·
      <a href="https://console.fleetbase.io/aws-marketplace" rel="nofollow" target="_aws_marketplace">Deploy on AWS</a>
      ·
      <a href="https://tally.so/r/3NBpAW" rel="nofollow">Book a Demo</a>
      ·
      <a href="https://discord.gg/V7RVWRQ2Wm" target="discord" rel="nofollow">Discord</a>
    </p>
    <hr />
</div>

## What is Fleetbase?

Fleetbase is a modular logistics and supply chain operating system designed to streamline management, planning, optimization, and operational control across various sectors of the supply chain industry.

<p align="center" dir="auto">
  <img src="https://flb-assets.s3.ap-southeast-1.amazonaws.com/static/fleetbase_overview.png" alt="Fleetbase Console" width="1200" style="max-width: 100%;" />
</p>
Fleetbase 核心是基于 PHP + Laravel 的后端 API。 


前端 / 控制台（Console）使用 Ember.js（JavaScript）技术栈。 


使用 Node / npm / pnpm 工具来管理前端、构建、打包、扩展等。 


数据存储主要用的是 MySQL（或兼容的关系数据库）作为后端数据库。 


部分即时 /实时通信 /推送功能可能涉及 WebSocket / socket 服务。 


官方推荐通过 Docker + Docker Compose 来部署，这是最简便、可移植性最好的方式。 

## Visual Feature Showcase

<p align="center" dir="auto">
  <img src="https://flb-assets.s3.ap-southeast-1.amazonaws.com/static/order-board-kanban.png" alt="Fleetbase Order Board" width="1200" style="max-width: 100%;" />
  <em>Visualize and manage your orders with a dynamic Kanban board.</em>
</p>

<p align="center" dir="auto">
  <img src="https://flb-assets.s3.ap-southeast-1.amazonaws.com/static/order-workflow-config.png" alt="Fleetbase Order Workflow Configuration" width="1200" style="max-width: 100%;" />
  <em>Create custom order flows and automation with the intuitive workflow builder.</em>
</p>

<p align="center" dir="auto">
  <img src="https://flb-assets.s3.ap-southeast-1.amazonaws.com/static/order-map-view.png" alt="Fleetbase Order Map View" width="1200" style="max-width: 100%;" />
  <em>Track individual orders in real-time on an interactive map.</em>
</p>

<p align="center" dir="auto">
  <img src="https://flb-assets.s3.ap-southeast-1.amazonaws.com/static/live-map-tracking.png" alt="Fleetbase Live Map Tracking" width="1200" style="max-width: 100%;" />
  <em>Get a complete overview of your fleet and active orders on a live map.</em>
</p>

<p align="center" dir="auto">
  <img src="https://flb-assets.s3.ap-southeast-1.amazonaws.com/static/fleet-map-zones.png" alt="Fleetbase Fleet Map with Zones" width="1200" style="max-width: 100%;" />
  <em>Define and manage service areas and zones for your fleet.</em>
</p>

**Quickstart**

```bash
git clone git@github.com:fleetbase/fleetbase.git  
cd fleetbase && ./scripts/docker-install.sh
```

## 📖 Table of contents

  - [Features](#-features)
  - [Install](#-install)
  - [Deploy on AWS](#-deploy-on-aws-in-one-click)
  - [Extensions](#-extensions)
  - [Apps](#-apps)
  - [Roadmap](#-roadmap)
  - [Bugs and Feature Requests](#-bugs-and--feature-requests)
  - [Documentation](#-documentation)
  - [Contributing](#-contributing)
  - [Community](#-community)
  - [Creators](#-creators)
  - [License & Copyright](#-license-and-copyright)

## 📦 Features
- **Extensible:** Build installable extensions and additional functionality directly into the OS via modular architecture.
- **Developer Friendly:** RESTful API, socket, and webhooks to seamlessly integrate with external systems or develop custom applications.
- **Native Apps:** Collection of open-source and native apps designed for operations and customer facing.
- **Collaboration:** Dedicated chat and comments system for collaboration across your organization.
- **Security:** Secure data encryption, adherence to industry-standard security practices, and a comprehensive dynamic Identity and Access Management (IAM) system.  
- **Telematics:** Integrate and connect to hardware devices and sensors to provide more feedback and visibility into operations.
- **Internationalized:** Translate into multiple languages to accommodate diverse user bases and global operations.
- **Framework:** PHP core built around logistics and supply chain abstractions to streamline extension development.
- **Dynamic:** Configurable rules, flows and logic to enable automation and customization.
- **UI/UX:** Clean, responsive user-friendly interface for efficient management and operations from desktop or mobile.
- **Dashboards:** Create custom dashboards and widgets to get full visibility into operations.  
- **Scalability:** Uninterrupted growth with scalable infrastructure and design, capable of handling increasing data volume and user demand as your business expands.
- **Continuous Improvements:** Commitment to continuous improvement, providing regular updates that seamlessly introduce optimizations, new features, and overall enhancements to the OS.
- **Open Source:** Deploy it either on-premise or in the cloud according to your organization's needs and preferences.

## 💾 Install
Getting up and running with Fleetbase via Docker is the quickest and most straightforward way. If you’d like to use Fleetbase without docker read the [full install guide in the Fleetbase documentation](https://docs.fleetbase.io/getting-started/install).  
  
Make sure you have both the latest versions of docker and docker-compose installed on your system.

```bash
git clone git@github.com:fleetbase/fleetbase.git  
cd fleetbase && ./scripts/docker-install.sh
```

### Accessing Fleetbase
Once successfully installed and running you can then access the Fleetbase console on port 4200 and the API will be accessible from port 8000.  
  
Fleetbase Console: http://localhost:4200
Fleetbase API: http://localhost:8000

### Additional Configurations

**CORS:** If you’re installing directly on a server you will need to configure the environment variables to the application container:
```
CONSOLE_HOST=http://{yourhost}:4200
```
If you have additional applications or frontends you can use the environment variable `FRONTEND_HOSTS` to add a comma delimited list of additioal frontend hosts.

**Application Key** If you get an issue about a missing application key just run:
```bash
docker compose exec application bash -c "php artisan key:generate --show"
```
Next copy this value to the `APP_KEY` environment variable in the application container and restart.
  
**Routing:** Fleetbase ships with a default OSRM server hosted by `[router.project-osrm.org](https://router.project-osrm.org)` but you’re able to use your own or any other OSRM compatible server. You can modify this in the `console/environments` directory by modifying the .env file of the environment you’re deploying and setting the `OSRM_HOST` to the OSRM server for Fleetbase to use.  
  
**Services:** There are a few environment variables which need to be set for Fleetbase to function with full features. If you’re deploying with docker then it’s easiest to just create a `docker-compose.override.yml` and supply the environment variables in this file.

```yaml
version: “3.8”
services:  
  application:  
    environment:  
      CONSOLE_HOST: http://localhost:4200
      MAIL_MAILER: (ses, smtp, mailgun, postmark, sendgrid)
      OSRM_HOST: https://router.project-osrm.org
      IPINFO_API_KEY:
      GOOGLE_MAPS_API_KEY:  
      GOOGLE_MAPS_LOCALE: us
      TWILIO_SID:  
      TWILIO_TOKEN:
      TWILIO_FROM:
```

You can learn more about full installation, and configuration in the [official documentation](https://docs.fleetbase.io/getting-started/install).

## 🚀 Deploy on AWS in One Click

Deploy your complete Fleetbase logistics platform on AWS with enterprise-grade security, scalability, and reliability. No DevOps expertise required!

[![Deploy to AWS](https://img.shields.io/badge/Deploy%20to%20AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://console.fleetbase.io/aws-marketplace)

### ✨ What You Get

- **Complete AWS Infrastructure**: ECS Fargate, RDS MySQL, ElastiCache Redis, S3, CloudFront, and more  
- **25-Minute Setup**: From zero to production-ready logistics platform  
- **Enterprise Security**: VPC isolation, encrypted storage, secrets management  
- **Auto-Scaling**: Handle traffic spikes with ECS Fargate auto-scaling  
- **High Availability**: Multi-AZ deployment with 99.9% uptime SLA  
- **Cost Optimized**: Pay-as-you-use with optimized resource allocation  

### 🏗️ Infrastructure Included

Your AWS deployment includes a complete, production-ready infrastructure stack:

- **Compute**: ECS Fargate cluster with auto-scaling services  
- **Database**: RDS MySQL 8.0 with automated backups and Multi-AZ support  
- **Cache**: ElastiCache Redis for high-performance caching  
- **Storage**: S3 object storage with CloudFront CDN for global distribution  
- **Networking**: VPC with private subnets, NAT gateways, and security groups  
- **Load Balancing**: Application Load Balancer with SSL certificates  
- **Monitoring**: CloudWatch logs, container insights, and health monitoring  
- **Messaging**: SQS message queues for background job processing  

[**🚀 Deploy Now**](https://console.fleetbase.io/aws-marketplace) | [**📖 Learn More**](https://docs.fleetbase.io/category/deploying/aws)

# 🧩 Extensions 

Extensions are modular components that enhance the functionality of your Fleetbase instance. They allow you to add new features, customize existing behavior, or integrate with external systems.

You can find extensions available from the official [Fleetbase Console](https://console.fleetbase.io), here you will also be able get your registry token to install extensions to a self-hosted Fleetbase instance. 

Additionally you're able to develop and publish your own extensions as well which you can read more about developing extensions via the [extension building guide](https://docs.fleetbase.io/developers/building-an-extension).

## ⌨️ Fleetbase CLI 

The Fleetbase CLI is a powerful tool designed to simplify the management of extensions for your Fleetbase instance. With the CLI, you can effortlessly handle authentication, install and uninstall extensions, and scaffold new extensions if you are developing your own.

Get started with the CLI with npm:

```bash
npm i -g @fleetbase/cli
```

Once installed, you can access a variety of commands to manage your Fleetbase extensions.

# 📱 Apps

Fleetbase offers a few open sourced apps which are built on Fleetbase which can be cloned and customized. Every app is built so that the Fleetbase instance can be switched out whether on-premise install or cloud hosted.

<ul>
  <li><a href="https://github.com/fleetbase/storefront-app">Storefront App</a>: Fleetbase based ecommerce/on-demand app for launching your very own shop or marketplace to Apple or Android playstore.</li>
  <li><a href="https://github.com/fleetbase/navigator-app">Navigator App</a>: Fleetbase based driver app which can be used for drivers to manage and update order, additionally provides real time driver location which can be viewed in the Fleetbase Console.</li>
</ul>

## 🛣️ Roadmap
1.  **Inventory and Warehouse Management** ~ Pallet will be Fleetbase’s first official extension for WMS & Inventory.
2.  **Accounting and Invoicing** ~ Ledger will be Fleetbase’s first official extension accounting and invoicing.
3.  **AI** ~ AI Agent intrgation for system and workflows.
4. **Dynamic Rules System** ~ Trigger events, tasks jobs from a rule builder on resources.

Ubuntu 22.04 LTS 是目前部署 Fleetbase 最稳定、兼容性最强的环境之一——比 CentOS 系列更省心，所有依赖版本都直接支持。下面是为你量身定制的完整部署方案。

🧱 一、系统与基础环境建议
项目	推荐配置	说明
系统	Ubuntu 22.04 LTS (64 bit)	支持到 2027 年，兼容 Docker、PHP 8、Node 18+
CPU / 内存	≥ 4 核 / 8 GB RAM	小规模部署；中大型可 8 核 16 GB
磁盘	≥ 50 GB SSD	Docker 卷+数据库占用较多
网络	稳定公网，开放 80 / 443 端口	便于反代与 SSL 证书
🐋 二、推荐部署模式：Docker Compose（官方方式）

Fleetbase 官方在 GitHub 与 docs.fleetbase.io 都建议用 Docker Compose，安装步骤如下。

1️⃣ 安装 Docker & Compose
sudo apt update && sudo apt upgrade -y
sudo apt install ca-certificates curl gnupg lsb-release -y
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu jammy stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
sudo systemctl enable docker && sudo systemctl start docker
docker --version
docker compose version

2️⃣ 获取 Fleetbase 源代码
git clone https://github.com/fleetbase/fleetbase.git
cd fleetbase

3️⃣ 复制环境模板并配置变量
cp .env.example .env
nano .env


关键变量：

APP_KEY=base64:随机生成
APP_URL=https://api.example.com
CONSOLE_URL=https://console.example.com
DB_HOST=db
DB_PORT=3306
DB_DATABASE=fleetbase
DB_USERNAME=fleetbase
DB_PASSWORD=strongpassword
GOOGLE_MAPS_API_KEY=你的API密钥

4️⃣ 启动容器
docker compose up -d


启动后默认包含：

api (Laravel API)

console (Ember 前端)

socket (WebSocket)

db (MySQL)

redis

5️⃣ 初始化数据库
docker compose exec api php artisan migrate --seed

6️⃣ 配置 Nginx 反向代理 + SSL

如果你使用宝塔或自己管理 Nginx：

server {
    server_name api.example.com;
    location / {
        proxy_pass http://127.0.0.1:9000;  # 对应容器或端口
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }
    listen 80;
}


再用 Certbot 或 宝塔 一键 Let’s Encrypt 证书，开启 HTTPS。

🧩 三、可选优化
模块	功能	命令 / 提示
Redis	缓存与队列	默认容器内已启用
备份卷	数据持久化	/var/lib/docker/volumes/fleetbase_*
Map API	路线 / 定位 / 距离	建议绑定 Google Maps 或 OpenStreetMap API
监控	Uptime Kuma / Netdata	独立容器即可
防火墙	ufw allow 80,443,22/tcp	其余端口关闭
🧰 四、若不想用 Docker（原生部署简略）

仍然可行，但需：

PHP 8.1 + Composer 2.x

Node 18 + Ember CLI + pnpm

MySQL 8.0 + Redis 6+

Nginx / Apache 配置 FPM 反代

手动运行 php artisan migrate --seed、npm build

不如 Docker 轻松。

✅ 五、最终建议

Ubuntu 22.04 + Docker Compose 是最省事组合。

宝塔也可装 Docker 管理插件，用它启动 compose 更方便。

数据、上传目录、.env 都挂载宿主机卷，便于未来迁移。
## 🪲 Bugs and 💡 Feature Requests

Have a bug or a feature request? Please check the <a href="https://github.com/fleetbase/fleetbase/issues">issue tracker</a> and search for existing and closed issues. If your problem or idea is not addressed yet, please <a href="https://github.com/fleetbase/fleetbase/issues/new">open a new issue</a>.

## 👨‍💻 Contributing

Please read through our <a href="https://github.com/fleetbase/fleetbase/blob/main/CONTRIBUTING.md">contributing guidelines</a>. Included are directions for opening issues, coding standards, and notes on development.

## 👥 Community

Get updates on Fleetbase's development and chat with the project maintainers and community members by joining our <a href="https://discord.gg/V7RVWRQ2Wm">Discord</a>.

<ul>
  <li>Follow <a href="https://x.com/fleetbase_io">@fleetbase_io on X</a>.</li>
  <li>Read and subscribe to <a href="https://www.fleetbase.io/blog-2">The Official Fleetbase Blog</a>.</li>
  <li>Ask and explore <a href="https://github.com/orgs/fleetbase/discussions">our GitHub Discussions</a>.</li>
</ul>
<p dir="auto">See the <a href="https://github.com/fleetbase/fleetbase/releases">Releases</a> section of our GitHub project for changelogs for each release version of Fleetbase.</p>
<p>Release announcement posts on <a href="https://www.fleetbase.io/blog-2" rel="nofollow">the official Fleetbase blog</a> contain summaries of the most noteworthy changes made in each release.</p>

## Creators

<p dir="auto"><strong>Ronald A. Richardson</strong>- Co-founder &amp; CTO</p>
<img src="https://user-images.githubusercontent.com/58805033/230263021-212f2553-1269-473d-be94-313cb3eecfa5.png" alt="Ron Image" width="75" height="75" style="max-width: 100%;">          
<p><a href="https://github.com/orgs/fleetbase/people/roncodes">Github</a> | <a href="https://www.linkedin.com/in/ronald-a-richardson/">LinkedIn</a></p>
                   
<p dir="auto"><strong>Shiv Thakker</strong> - Co-founder &amp; CEO</p>
<img src="https://user-images.githubusercontent.com/58805033/230262598-1ce6d0cc-fb65-41f9-8384-5cf5cbf369c7.png" alt="Shiv Image" width="75" height="75" style="max-width: 100%;">  
<p><a href="https://github.com/orgs/fleetbase/people/shivthakker">Github</a> | <a href="https://www.linkedin.com/in/shivthakker/">LinkedIn</a></p>


# License & Copyright

Fleetbase is made available under the terms of the <a href="https://www.gnu.org/licenses/agpl-3.0.html" target="_blank">GNU Affero General Public License 3.0 (AGPL 3.0)</a>. For other licenses <a href="mailto:hello@fleetbase.io" target="_blank">contact us</a>.



