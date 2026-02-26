# CHATTING-APPLICATION

Here is a complete and professional **README.md** file for your Chatting Application project.

You can copy this directly into a `README.md` file.

---

# 💬 Java Chatting Application (Client–Server)

A simple **GUI-based Chatting Application** built using **Java Swing** and **Socket Programming**.
This project demonstrates real-time communication between a **Client** and a **Server** using TCP connections.

---

## 📌 Project Overview

This application allows two users to communicate over a network using:

* Java Sockets
* Java Swing (GUI)
* DataInputStream & DataOutputStream
* File handling for chat history

The project consists of:

* `Client.java`
* `Server.java`

Both sides have a graphical chat interface similar to messaging apps.

---

## 🛠 Technologies Used

* **Java**
* **Swing (GUI)**
* **Socket Programming (TCP)**
* **AWT**
* **File I/O**
* **Multithreading (Implicit via loops)**

---

## 📂 Project Structure

```
chatting_Application/
│
├── Client.java
├── Server.java
├── assets/
│   ├── backward_icon.png
│   ├── orangeGhost.png
│   └── blueGhost.png
└── chat_history.txt (auto-generated)
```

---

## 🚀 Features

### ✅ Graphical User Interface

* Custom header panel
* Profile icons
* Active status label
* Chat message bubbles
* Timestamps (HH:mm format)
* Send button
* Exit button

### ✅ Real-time Messaging

* Uses TCP Socket connection
* Server runs on port `6001`
* Messages sent using `writeUTF()`
* Messages received using `readUTF()`

### ✅ Message Alignment

* Client messages aligned to the right
* Received messages aligned to the left
* Vertical layout using `BoxLayout`

### ✅ Chat History Storage

* Messages stored in:

```
chat_history.txt
```

* Format:

```
[HH:mm] Sender: Message
```

* Uses append mode (`FileWriter("chat_history.txt", true)`)

---

## 🔌 How It Works

### 1️⃣ Server Side

* Creates a `ServerSocket` on port **6001**
* Waits for client connection using:

```java
Socket s = skt.accept();
```

* Reads messages continuously using:

```java
dataInput.readUTF();
```

### 2️⃣ Client Side

* Connects to:

```
127.0.0.1 (localhost)
Port: 6001
```

* Sends messages using:

```java
dataOutput.writeUTF(output);
```

---

## ▶️ How To Run The Project

### Step 1: Compile

Open terminal inside project directory:

```
javac chatting_Application/*.java
```

### Step 2: Run Server First

```
java chatting_Application.Server
```

### Step 3: Run Client

Open another terminal window:

```
java chatting_Application.Client
```

⚠️ Always start the **Server first**, then the **Client**.

---

## 🌐 Network Configuration

Currently configured for:

```
IP Address: 127.0.0.1
Port: 6001
```

To run on different systems:

* Replace `127.0.0.1` in `Client.java` with the server machine's IP address.

Example:

```java
Socket s = new Socket("192.168.1.5", 6001);
```

---

## 📸 UI Description

### Header Panel

* Back button (Exit)
* Profile icon
* User name
* Status label ("Active Now")

### Chat Area

* Message bubbles (Green background)
* Timestamp below each message
* Vertical stacking

### Input Area

* Text field
* Send button

---

## 📁 Important Methods Explained

### `formateLabel(String output)`

* Creates message bubble
* Adds timestamp
* Uses HTML for word wrapping
* Returns a JPanel

### `saveMessage(String sender, String message)`

* Saves chat messages
* Appends to `chat_history.txt`
* Adds timestamp

### `actionPerformed(ActionEvent ae)`

* Triggered when Send button is clicked
* Sends message
* Displays message on UI
* Clears text field

---

## ⚠️ Limitations

* Supports only **one client at a time**
* No multithreading for multiple clients
* No encryption
* No user authentication
* No database storage
* No scroll pane (chat may overflow)
* No exception-based UI handling

---

## 🔮 Possible Improvements

* Add multi-client support using Threads
* Add JScrollPane for chat window
* Add emoji support
* Add file sharing
* Add message encryption
* Add user login system
* Add database (MySQL) storage
* Improve UI design
* Add typing indicator
* Add online/offline detection

---

## 🧠 Concepts Demonstrated

* TCP Communication
* Client–Server Architecture
* Swing GUI Design
* Layout Managers (BorderLayout, BoxLayout)
* Event Handling (ActionListener, MouseAdapter)
* File Handling in Java
* Real-time Data Streaming

---

## 📝 Example Chat History File Output

```
[14:32] Client: Hello
[14:33] Server: Hi!
[14:34] Client: How are you?

```
