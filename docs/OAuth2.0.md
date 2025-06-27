# OAuth 2.0 Overview

OAuth 2.0 can be thought of as a **digital handshake** between the app, service, and user, with everyone agreeing on what is shared.

It's an **authorization framework** that enables applications to access a user’s data on another service (like Facebook or GitHub) **without sharing the user’s password**.

Now that we’ve covered what it is, let’s dive into how it works.

---

## 🔸 OAuth 2.0 Process Overview

The process generally follows **6 steps** with **4 components** typically involved:

1. **Client** (app wanting access)
2. **Resource Owner** (user)
3. **Authorization Server**
4. **Resource Server**

To understand the process, let’s take a look at how a game would connect to a player’s **Facebook** account.

---

## 📱 OAuth 2.0 Workflow Example: Game Connecting to Facebook

### **Step 1: Request Access**
- Within the game (**client**), the player (**user**) clicks on a “connect with Facebook” button to link their profile and find friends.

### **Step 2: Redirect to Service**
- The game redirects the player to Facebook’s (**service’s**) login page.

### **Step 3: Permission Request**
- After logging in, the data that the game is requesting access to will be shown to the player, who can either allow or deny the access.

### **Step 4: Authorization Code**
- If the player gives their approval, Facebook redirects the player back to the game with an **authorization code** (from the **authorization server**). The code is a temporary credential that proves the player’s consent.

### **Step 5: Exchange Code for Token**
- The game now sends the **authorization code** along with its own identification to Facebook’s server in the background. Facebook identifies the authorization code and the game’s identity and returns an **access token**.

### **Step 6: Use the Token**
- The game can now use the **access token** to request the agreed-upon data from Facebook (**resource server**), like the player's friends list.

---

## 🔑 Key Points

In this process, the player’s **Facebook credentials** were never shared, but the game was able to access the agreed-upon player data from Facebook. This is what **OAuth 2.0** facilitates; allowing third-party applications to access data from services in a secure manner without sharing credentials.

---

## 🎯 OAuth 2.0 Grant Types

OAuth 2.0 provides multiple **grant types** to cater to different use cases. These grant types dictate how the application gets an access token.

For most web applications, the **Authorization Code Grant** is the recommended and most secure method to obtain access tokens.

## **Summary of OAuth 2.0 Grant Types**

| Grant Type                       | Use Case                             | Security                               |
|-----------------------------------|--------------------------------------|----------------------------------------|
| **Authorization Code Grant**      | Web applications (server-side)       | **Most secure**, uses authorization code for token exchange |
| **Implicit Grant**                | Single-page applications (client-side) | Less secure, access token is exposed in the URL |
| **Resource Owner Password Credentials Grant** | Trusted applications               | **Less secure**, user credentials shared directly |
| **Client Credentials Grant**      | Machine-to-machine communication     | Secure, client uses client ID and secret |
| **Refresh Token Grant**           | Token renewal                        | Secure, allows long-lived sessions without re-authentication |
| **Device Authorization Grant**    | Devices with limited input capabilities | Secure for devices like smart TVs, gaming consoles |
