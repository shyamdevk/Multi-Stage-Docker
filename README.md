# 🐳 **Multi-Stage Docker Build**

## ⭐ **Simple Definition**

**Multi-stage Docker build** means using **multiple FROM statements** in one Dockerfile so you can:

* Build your app in one stage
* Copy only the required files into a clean, smaller final image

➡️ **Result:** super small, secure Docker images.

---

## 🎯 **Why Do We Use Multi-Stage Builds?**

* Reduce image size
* Remove unnecessary build tools
* Improve security
* Faster deployments
* Cleaner final image (only required binaries/files)

---

## 🔍 **Simple Explanation**

Normally, building apps (like Go, Node.js, Python) requires:

* Build tools
* Compilers
* Libraries

But we **don’t want these inside the final production image**.

Multi-stage builds let you:

1. **Build** app in a big image
2. **Copy only final output** to a small image

---

# 📌 **Key Points (Easy to Remember)**

* ✔️ Uses **multiple FROM** instructions
* ✔️ Build app in one stage
* ✔️ Copy only needed output to final stage
* ✔️ Removes build tools → smaller image
* ✔️ Used for Node.js, Go, Java, Python, etc.

---

# 🔧 **Real-World Use Cases**

* Building React/Angular apps
* Building Go binary then shipping tiny image
* Packaging Java JAR file using Maven → then run on JRE
* Python apps that need heavy build dependencies

---
Here is your **clean, decorated, beginner-friendly `README.md`** with explanations where needed.
You can copy–paste this directly into your repo.

---

# 🐳 Multi-Stage Docker Build — Practical Exercise

This practical demonstrates the difference between a **single-stage Docker build** and a **multi-stage Docker build**.  
You will observe how multi-stage builds help create **smaller, optimized, production-ready images**.

---

## 🔧 Steps to Run This Practical

### 📥 1. Clone the Repository
```bash
git clone https://github.com/shyamdevk/Multi-Stage-Docker.git
````

---

## 🧱 2. Build the Single-Stage Docker Image

Navigate to the folder containing the **single-stage Dockerfile**:

```bash
cd docker-single-stage/build
docker build -t single-stage-app .
```

### 💡 Explanation

A single-stage image contains **everything** used for building + running the application.
This leads to a **large final image** because it includes:

* Go compiler
* Build tools
* Cache
* Intermediate files

---

## 🔍 3. Check Image Size

```bash
docker images
```

👉 **Note the size of `single-stage-app`.**
(It will be larger than the multi-stage image)

---

## 🧱 4. Build the Multi-Stage Docker Image

Go back to the root:

```bash
cd ..
docker build -t multi-stage-app .
```

### 💡 Explanation

The multi-stage Dockerfile builds the Go app in one stage,
then copies **only the final binary** into a clean, lightweight base image.
This removes:

* Build tools
* Compilers
* Extra dependencies

➡️ Result: **Much smaller, secure, production-ready image.**

---

## 🔍 5. Check Image Size Again

```bash
docker images
```

Compare the sizes:

* **`single-stage-app`** → Large
* **`multi-stage-app`** → Small

✔️ This proves how multi-stage builds optimize image size.

---

## 📂 Repo Structure

```
├── docker-single-stage/build/
│   ├── Dockerfile          # Single-stage Dockerfile
│   └── calculator.go       # Go source code
│
├── Dockerfile              # Multi-stage Dockerfile
├── calculator.go           # Go source code
└── README.md
```

---

## 📚 Reference

[https://github.com/shyamdevk/Multi-Stage-Docker.git](https://github.com/shyamdevk/Multi-Stage-Docker.git)

---


