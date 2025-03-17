# Minecraft-server-installation-guide
Steps to install Minecraft server

Minecraft Paper Server Setup (Linux)

This guide helps you set up a Paper Minecraft server on Linux step by step.


---

# 📌 Step 1: Install Java (Required)

Paper requires Java 17+. To install it, run:
```bash
sudo apt update
sudo apt install openjdk-17-jdk -y
```

## Verify the installation:

``bash
java -version
```
## You should see output similar to:
```bash
openjdk version "17.0.1" ...
```

---

# 📌 Step 2: Create a Server Directory

Navigate to your preferred location and create a server folder:
```bash
mkdir ~/minecraft-paper
cd ~/minecraft-paper
```

---

# 📌 Step 3: Download the Paper Server

## 1. Visit PaperMC Downloads.


## 2. Select your Minecraft version and copy the latest download link.


## 3. Run the following command (replace <URL> with the copied link):
```bash
wget https://papermc.io/api/v2/projects/paper/versions/your-paper-version/builds/latest/downloads/paper-your-paper-version-latest.jar -O paper.jar
```

## 4. Verify the file is downloaded:
```bash
ls -l
```

---

# 📌 Step 4: Run the Server for the First Time

Start the server to generate required files:
```bash
java -Xms2G -Xmx4G -jar paper.jar --nogui
```
-Xms2G → Minimum RAM (2GB)

-Xmx4G → Maximum RAM (4GB)


## ⚠️ The server will fail with an EULA message.


# 📌 Step 5: Accept the EULA

Edit the eula.txt file:
```bash
nano eula.txt
```
Change this line:

eula=false

To:
```bash
eula=true
```
Save and exit: CTRL + X → Y → Enter.


# 📌 Step 6: Start the Server

Run the server again:
```bash
java -Xms2G -Xmx4G -jar paper.jar --nogui
```
## ✅ The server will now start generating necessary files.


# 📌 Step 7: Configure the Server (Optional)

To modify server settings:
```bash
nano server.properties
```
Change settings as needed.


# 📌 Step 8: Create a Startup Script (Optional)

To make starting the server easier, create a script:
```bash
nano start.sh
```

Add the following:
```bash
#!/bin/bash
java -Xms2G -Xmx4G -jar paper.jar --nogui
```
Save and exit, then make it executable:
```bash
chmod +x start.sh
```
Now, you can start the server with:
```bash
./start.sh
```

# 📌 Step 9: Allow Firewall (If Needed)

If you’re hosting for others, allow port 25565:
```bash
sudo ufw allow 25565/tcp
```

# 🎉 Done! Your Paper server is now running.

Enjoy playing Minecraft with PaperMC! 🚀

