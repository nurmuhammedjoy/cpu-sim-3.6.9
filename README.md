# 🖥️ How to Install and Run CPU Sim 3.6.9 in Termux (Native)

## ✅ Requirements

  ```bash
  pkg install openjdk-17
  ```
---

## 📦 Step 1: download the files form my git

```bash
gh repo clone nurmuhammedjoy/cpu-sim-3.6.9
```

---

## 🧠 Step 2: Create a Global shortcut `cpusim` Command

Run these commands in Termux:

```bash
mkdir -p ~/.local/bin
nano ~/.local/bin/cpusim
```

Paste this into the file:

```sh
#!/data/data/com.termux/files/usr/bin/sh
java -cp ~/cpu-sim-3.6.9/CPUSim3.6.jar:\
~/cpu-sim-3.6.9/jhall.jar:\
~/cpu-sim-3.6.9/CPUSimHelp3.6.jar cpusim.Main
```

Save the file: `Ctrl + O`, `Enter`, then exit with `Ctrl + X`

---

## ✅ Step 3: Make it Work Anywhere

```bash
chmod +x ~/.local/bin/cpusim
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

---

## 🚀 Step 4: Run CPU Sim Anywhere

```bash
cpusim
```

🎉 CPU Sim 3.6.9 will open!

# 🛠 CPU Sim 4.0.11 JavaFX Dependency Issue

## What’s the problem?

When trying to launch CPU Sim 4.0.11 with OpenJDK 11+ or 17, users encounter this error:

```java
Exception in thread "main" java.lang.NoClassDefFoundError: javafx/application/Application
    at java.base/java.lang.ClassLoader.defineClass1(Native Method)
    at java.base/java.lang.ClassLoader.defineClass(...)  
    at cpusim.Main.main(Main.java:73)
Caused by: java.lang.ClassNotFoundException: javafx.application.Application
