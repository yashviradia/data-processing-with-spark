# data-processing-with-spark

A step-by-step guide to install and configure **Apache Spark** on a Linux system for local development, including PySpark with JupyterLab.

---

## 🧰 Prerequisites

### 1. Install Java

Update package index and install OpenJDK 21:

`sudo apt update`  
`sudo apt install openjdk-21-jdk -y`

Verify the installation:

`java -version`

### 2. Install Python Tools

Install `pip` and `venv` for Python 3.13:

`sudo apt install python3-pip python3.13-venv -y`

---

## ⚙️ Download & Install Apache Spark

1. Download the latest Spark version from the [official Spark downloads page](https://spark.apache.org/downloads.html).
2. Extract the tarball and move Spark to `/opt`:

`tar -xzf spark-<version>-bin-hadoop3.tgz`  
`sudo mv spark-<version>-bin-hadoop3 /opt/spark`

Replace `<version>` with the actual downloaded version.

---

## ✅ Sanity Check

Run the Spark shell to verify your installation:

`/opt/spark/bin/spark-shell`

This launches a Scala-based Spark shell.

---

## 🛠 Configure Environment Variables

Add Spark to your system `PATH` by updating your shell startup file (`~/.bashrc` for Bash, `~/.zshrc` for Zsh):

```
cat <<'EOF' >> ~/.bashrc
export SPARK_HOME=/opt/spark
export PATH="$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin"
EOF

source ~/.bashr
```

