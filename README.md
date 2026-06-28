**deployment contribution credit**: sriteja-it
<br>
**Author**: patan-shehanaz
<br>

🛡️CryptoGuard (Dark Mode PQC Dashboard)

A next-generation cryptographic safety auditor and interactive dashboard designed to evaluate public-key infrastructure (PKI) vulnerability index thresholds against emerging quantum computing threat vectors. 
The application scans TLS/certificate endpoints, computes explainable risk scoring, manages active API key lifecycles, and retains persistent audit logs over secure pipelines.

🚀 **[Live Production Deployment](https://crypto-guard1.vercel.app/)**

---
✨ Features
* **Quantum-Urgency Risk Engine:** Scans active TLS endpoints and computes an explainable, multi-variable vulnerability score mapping classical strength against quantum threat timelines.
* **Secured API Key Management:** Admin APIs employ strict security protocols—never returning plaintext keys. Active keys are securely referenced solely via `keyId` and `keyFingerprint`.
* **Automated Data Migrations:** Implements an automated backend schema migration on startup, enforcing a default quota limit of `5` scans per API key to ensure system stability.
* **Granular Audit Logs:** Complete per-scan and bulk-deletion management pipelines for historical records, accessible via an interactive administrative UI.
* **Highly Tunable Configurations:** The risk scoring matrix is fully customizable via decoupled environment variables governing algorithm weights and penalty thresholds.
---
🛠️ Systems Design & Architecture
The codebase is organized into an isolated, performant monorepo structure separating the data processing backend from the responsive administrative viewports:
### 📂 Repository Directory Tree
```text
├── backend/                  # Node.js/Express API Engine
│   ├── server.js             # Core API endpoints & administrative routes
│   ├── mongoStore.js         # MongoDB integration layer (schemas & data helpers)
│   ├── riskEngine.js         # Algorithmic risk scoring logic & metadata parsing
│   ├── test-risk.js          # Isolated unit tests validating risk metrics
│   └── test-integration.js   # Automated integration suites checking quota pipelines
├── src/                      # React + Vite Client Application
│   ├── components/           # Functional dashboard elements & primitives
│   ├── pages/                # Admin views, historical lists, and analytics panes
│   ├── App.jsx               # Main application layout routing
│   └── main.jsx              # Client-side initialization script
├── styles/                   # Global CSS, Tailwind configurations, & typography
├── index.html                # Vite entry template layout
├── vite.config.js            # Frontend build pipeline configurations
└── package.json              # Monorepo cross-dependencies & ecosystem metadata
```
## 📊 The Risk Scoring Engine (riskEngine.js)
The core analytical engine parses active handshakes and algorithm parameters, outputting a highly detailed **vulnerabilityScore (0-100)**, an explicit **riskLevel**, and an algorithmic **breakdown** computed across four vectors:

| Assessment Vector | Parameter Evaluated | Mitigation Mapping |
| :--- | :--- | :--- |
| **Classical Strength** | Bit-length analysis (e.g., RSA-2048 vs. ECC-256) | Baseline cryptography strength verification |
| **Quantum Urgency** | Mathematical vulnerability to Shor's/Grover's algorithms | Preemptive Post-Quantum Cryptography (PQC) routing |
| **TLS Protocol Penalties** | Deprecated protocol versions (TLS 1.0/1.1 vs. TLS 1.3) | Configuration vulnerability scoring adjustments |
| **Expiry Penalties** | Certificate lifecycle longevity and remaining validity | Operational compliance oversight |

## ⚙️ Local Installation & Configuration
### Prerequisites
 * **Node.js** (v18.x or higher recommended)
 * **MongoDB Instance** (Local daemon or MongoDB Atlas URI)
### 1. Setup and Environment Injection
Clone this repository locally, navigate to the backend/ directory, and create a custom .env file:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
# Tunable Risk Thresholds
CLASSICAL_WEIGHT=0.40
QUANTUM_WEIGHT=0.60
DEFAULT_QUOTA_LIMIT=5
```
### 2. Dependency Resolution & Startup
Execute the following commands to install dependencies and initialize the localized execution loops:
```bash
# Initialize and start the Backend Engine
cd backend
npm install
npm start
# Initialize and start the Frontend Interface (In a separate terminal tab)
cd ..
npm install
npm run dev
```
## 🧪 Testing Pipelines
The system maintains comprehensive testing coverage across core algorithmic behaviors and administrative constraints. Run these verification frameworks directly inside the backend/ directory:
```bash
# Execute isolated unit tests for the risk engine math
node test-risk.js
# Execute full database integration and quota verification sweeps
node test-integration.js
```
## 📄 Distribution & Attribution
Designed, engineered, and maintained by **patan-shehanaz**. Developed as an active reference model for cryptographic baseline discovery and PQC migration analysis.
```
```
