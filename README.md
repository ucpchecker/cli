 # UCP Validator CLI

### A community command-line tool for validating UCP manifests directly from your terminal or CI/CD
pipeline.

We build open infrastructure to help developers verify, debug, and monitor Agent Commerce readiness.

---

### ⚡ **Features**

| Feature | Description |
| :--- | :--- |
| **Live Verification** | Force a real-time check against the UCP Validator API. |
| **CI/CD Ready** | Proper exit codes (`0` for verified, `1` for failure) to gate deployments. |
| **Scriptable** | `--json` output for easy parsing with `jq` and other tools. |

---

### 📦 **Installation**

#### **Linux / CI (GitHub Actions)**

```bash
wget https://github.com/ucpchecker/cli/releases/download/v1.0.0/ucp-linux-amd64
chmod +x ucp-linux-amd64
./ucp-linux-amd64 check yourdomain.com

#### Mac (Apple Silicon)

wget https://github.com/ucpchecker/cli/releases/download/v1.0.0/ucp-mac-arm64
chmod +x ucp-mac-arm64
./ucp-mac-arm64 check yourdomain.com

#### Windows

Download ucp-windows.exe from the Releases page and run via PowerShell.

———

### 🛠️ Usage

Live Check (Forces fresh verification)

ucp check mystore.com

Cached Status (Fast lookup, no external requests)

ucp status mystore.com

JSON Output (For scripting)

ucp check mystore.com --json

CI/CD Pipeline (Block bad deployments)

ucp check mystore.com || exit 1
