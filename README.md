# 🏗️ NovaEco Runtime (Base Images)

![Component ID](https://img.shields.io/badge/ID-RUNTIME-orange)
![Layer](https://img.shields.io/badge/Layer-Infrastructure-blue)
![Type](https://img.shields.io/badge/Type-Base_Image-green)

> **The Immutable Foundation.**
> The root of the NovaEco software supply chain, defining the hardened base Docker images upon which every microservice in the ecosystem is assembled.

## 📖 Overview

The **NovaEco Runtime** repository operates as a Build Artifact Producer. It does not contain circular economy business logic; rather, it publishes the fundamental building blocks (OS layers, language runtimes like Python and Node.js, and system dependencies) to the Container Registry.

In a decentralized digital public infrastructure, "Configuration Drift" between municipal deployments or developer machines is a major source of operational risk. This component implements **Immutable Infrastructure** principles—ensuring that the environment where a circular economy algorithm is tested is the *exact same* binary foundation used in production, eliminating "It works on my machine" issues.

* **Role:** Supply Chain Security, Dependency Management, & Container Standardization.
* **Input:** `Dockerfile` definitions & hardened dependency constraints.
* **Output:** Golden Docker Images (e.g., `novaeco-runtime-python`, `novaeco-runtime-node`).

---

## ⚠️ Architectural Migration Notice (V2)

**This repository is part of the NovaEco v2 Polyrepo Architecture.**
Active development and migration from the legacy v1 prototype into this dedicated infrastructure component is scheduled for **Q2/Q3 2026**. 

---

## 🌟 Key Capabilities (Target Architecture)

### 1. The "Golden Image" Strategy
Instead of every domain service (like `novaeco-balance` or `novaeco-policy`) installing OS dependencies from scratch, the deployment pipelines inject component packages into our pre-built golden images. This ensures consistency across the entire system-of-systems.

### 2. Supply Chain Security (DevSecOps)
Every build triggers automated vulnerability scanning (e.g., Trivy/Grype). High-severity CVEs in underlying libraries break the build pipeline, preventing insecure packages from ever reaching public or enterprise deployments. This shifts security "Left" to the very base layer of the infrastructure.

### 3. Late-Binding Assembly Support
Under the NovaEco Late-Binding Container Strategy, individual developers do not write complex `Dockerfile`s. Instead, automated pipelines dynamically generate standard containers that inject compiled logic packages into these hardened runtimes. This drastically speeds up CI/CD build times and guarantees deterministic deployments.

### 4. Build Performance & Caching
Pre-compiles heavy dependencies (e.g., numerical processing libraries required for Life Cycle Assessments) into the base image. Because deployment pipelines only need to install lightweight logic packages rather than compiling heavy C-extensions from scratch, final container assembly drops from minutes to seconds.

---

## 🤝 Contributing

We welcome contributors to help build the open-source infrastructure for the circular economy. 

Please see the central [**NovaEco Organization README**](https://github.com/novaeco-tech) for our overall contribution guidelines, Code of Conduct, and ecosystem roadmap.

## 📄 License

This project is licensed under the **Apache License 2.0**. See the [LICENSE](LICENSE) file for details.
