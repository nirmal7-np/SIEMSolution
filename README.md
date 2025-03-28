# Wazuh SIEM Docker Deployment

Deploy a powerful SIEM stack using Wazuh, Docker, and Docker Compose — built to run locally on Ubuntu for testing, development, or small-scale production.

---

## ⚙️ Setup Locally in Ubuntu (with Docker Compose)

### Step 1: Clone the Repository

```bash
git clone https://github.com/nirmal7-np/SIEMSolution.git
cd SIEMSolution/single-node
```

---

### Step 2: Generate Certificates for the Indexer

```bash
docker compose -f generate-indexer-certs.yml run --rm generator
```

This will create necessary SSL certificates under `config/certs/`.

---

### Step 3: Start the Wazuh Stack

```bash
docker compose up -d
```

> This brings up Wazuh Manager, Dashboard, Indexer (OpenSearch), and Filebeat containers.

---

## 🖥️ Wazuh Dashboard

Once running, access the Wazuh Dashboard here:

- 🔗 [https://localhost:5601](https://localhost)
- 🧑‍💻 **Username**: `admin`
- 🔐 **Password**: `SecretPassword` *(or check your dashboard config)*

If you're on WSL, open it in a browser on your Windows host using `localhost:5601`.

---

### 📸 Screenshot

![Wazuh Dashboard](./assets/wazuh-dashboard.png)

This is a live view of the Wazuh SIEM Dashboard — showing endpoint security, threat intelligence, and compliance monitoring all in one place.

---

## 📁 Project Structure

```
single-node/
├── config/
│   ├── wazuh_dashboard/
│   ├── wazuh_indexer/
│   ├── wazuh_manager/
│   └── certs/
├── docker-compose.yml
├── generate-indexer-certs.yml
└── README.md
```

---

## 📌 Highlights

✅ Single-node Wazuh stack  
✅ Local deployment in under 10 minutes  
✅ Secure by default with SSL certs  
✅ Dashboard for logs, alerts, and agents  
✅ Modular config for future scaling

---

## 🧰 Requirements

- Ubuntu (native or WSL)
- Docker
- Docker Compose
- Internet connection (to pull images)

---

## 🔒 Security Notes

- Change the default login credentials before using in production.
- Certs are self-signed — use trusted certs for live environments.
- Network ports are exposed locally — review `docker-compose.yml` before exposing externally.

---

## 📚 References

- [Wazuh Docker Documentation](https://documentation.wazuh.com/current/deployment-options/docker/wazuh-container.html)
- [Wazuh Manager](https://documentation.wazuh.com/current/user-manual/index.html)

---

## 👨‍💻 Maintainer

Made with 💻 by **Nirmal**  
🔗 GitHub: [@nirmal7-np](https://github.com/nirmal7-np)

---
