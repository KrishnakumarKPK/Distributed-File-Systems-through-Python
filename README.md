# Distributed File Systems through Python 📁🌐

This project is a low-level implementation of a **Distributed File System (DFS)** using pure Python. It simulates how distributed file storage systems manage file splitting, redundancy, and retrieval across multiple server nodes — without relying on third-party libraries or frameworks.

---

## 🔧 Key Features

- **File Upload (PUT):** Files are split into chunks and distributed across four DFS nodes using hashing for placement and redundancy.
- **File Download (GET):** Retrieves file chunks from available servers and reconstructs the original file. Tolerates up to one node failure.
- **Authentication:** Supports basic user authentication using MD5 hashed credentials from a config file.
- **Fault Tolerance:** Ensures that files can still be retrieved even if one DFS node is offline.
- **Command-line Interface:** Interact with the system via simple terminal commands.

---

## 🛠 How to Use

### 1. Start DFS Nodes

Start four DFS servers on separate terminals (or background processes):

```bash
python dfs1.py 10001
python dfs2.py 10002
python dfs3.py 10003
python dfs4.py 10004
```

### 2. Run the Client

Use the client to interact with the DFS system:

```bash
python dfc.py dfc.conf
```

You will be prompted to enter a command like:

- `PUT filename.txt`
- `GET filename.txt`
- `LIST`

---

## 🔐 Default Users

Predefined users in the `dfc.conf` file:

- **Alice** – `Crimson33`
- **Bob** – `Velvet77`
- **Eve** – `Magellan101`

Passwords are MD5-hashed in the configuration file.

---

## 📄 Supported Commands

| Command        | Description |
|----------------|-------------|
| `PUT <file>`   | Splits and uploads file chunks to DFS nodes with redundancy |
| `GET <file>`   | Downloads and reconstructs the original file from chunks |
| `LIST`         | Lists all files stored and their completeness status |

---

## 🧪 Fault Tolerance

This system supports recovery with **any 3 of the 4 nodes** active. If only two or fewer nodes are running, some files may not be reconstructable due to missing chunks.

---

## 🔮 Possible Improvements

- Add file encryption before transmission
- Introduce file replication for stronger durability
- Switch to more secure password hashing (bcrypt/SHA-256)
- Add a web interface or REST API for file interaction
- Handle binary files and large uploads

---

## 👨‍💻 Author

**Krishna Kumar K**  
🔗 [LinkedIn](https://www.linkedin.com/in/krishna-kumar-kondooru-731044256/)

---

⭐ *Star this repo if you're exploring distributed systems with Python!*
