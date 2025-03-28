## 📄 `README.md`

# 🛡️ Wazuh SIEM - Single Node Docker Deployment

A single-node SIEM solution powered by [Wazuh](https://wazuh.com/), deployed via Docker. This setup is perfect for local testing, learning, small environments, or kicking off a larger security monitoring project.

> 🔧 Built and tested on **WSL Ubuntu + Docker Compose**.

---

## 📦 Stack Overview

This Docker-based deployment includes:

- **Wazuh Manager** - Core component for log collection, analysis, and alerting
- **Wazuh Indexer (OpenSearch)** - Stores and indexes security events
- **Wazuh Dashboard** - Web UI for visualization and management
- **Filebeat** - For internal data forwarding
- **Docker Compose** - Orchestrates all containers

---

## 🚀 Getting Started

### 1. Clone this repository

```bash
git clone https://github.com/nirmal7-np/SIEMSolution.git
cd SIEMSolution/single-node
```

### 2. Generate Indexer Certificates

Before starting, generate the required certs:

```bash
docker compose -f generate-indexer-certs.yml run --rm generator
```

This will create certificates inside `config/certs/`.

### 3. Start the Wazuh Stack

```bash
docker compose up -d
```

> 🕒 First-time startup may take a few minutes.

---

## 🌐 Access the Dashboard

Once up and running, access the dashboard at:

🔗 [https://localhost:5601](https://localhost:5601)

- **Username**: `admin`
- **Password**: `SecretPassword` (default — can be changed in `config/wazuh_dashboard/config/wazuh.yml`)

> ⚠️ If using WSL, use your **Windows IP or localhost:5601** depending on port binding.

---

## 🛠️ File Structure

```
single-node/
├── config/
│   ├── wazuh_indexer/
│   ├── wazuh_manager/
│   ├── wazuh_dashboard/
│   └── certs/
├── docker-compose.yml
├── generate-indexer-certs.yml
└── README.md
```

---

## 📋 Requirements

- Docker
- Docker Compose
- WSL (if on Windows)
- Internet connection for pulling images

---

## 📎 References

- 📚 [Wazuh Docker Deployment Docs](https://documentation.wazuh.com/current/deployment-options/docker/wazuh-container.html)
- 🌐 [Official Wazuh Site](https://wazuh.com/)

---

## 🔒 Security Notes

- Default credentials should be changed in production.
- SSL certificates are self-signed by default.
- Only exposed locally (change `docker-compose.yml` if deploying externally).

---

## 🙌 Credits

Thanks to the [Wazuh Team](https://github.com/wazuh) for providing the containerized solution.

---

## 📢 Author

👤 **Nirmal**  
📬 GitHub: [@nirmal7-np](https://github.com/nirmal7-np)

---

## 📌 License

This project is released under the [MIT License](../LICENSE).
```

---

Let me know if you want to add:
- Screenshots of the dashboard
- Custom tweaks you made
- How to add agents

Or I can turn this into a stylish Markdown doc with icons and badges too 💅
