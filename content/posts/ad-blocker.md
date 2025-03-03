+++
date = '2025-03-3T18:24:05+05:00'
title = "How I Created a Simple Ad Blocker Extension for Google Chrome "
+++


# Introduction

In this blog post, I'll walk you through the process of creating a simple ad blocker extension for Google Chrome. I'll also guide you on how to load this extension into your browser and test its effectiveness using the [Ookla Speedtest](https://www.speedtest.net/) website. Let's get started!

---

## Step 1: Understanding the Basics

An ad blocker extension works by blocking requests to known ad-serving domains. In this example, we'll block requests to `doubleclick.net` and `googleadservices.com`, which are commonly used for serving ads.

To create this extension, we'll need two files:
1. **`manifest.json`**: This file defines the extension's metadata and permissions.
2. **`rules.json`**: This file contains the rules for blocking specific domains.

---

## Step 2: Creating the Files

### 1. `manifest.json`
This file tells Chrome about your extension, including its name, version, and permissions. Here's the code:

```json
{
    "name": "Simple Ad Blocker",
    "version": "1.0.0",
    "manifest_version": 3,
    "permissions": [
        "declarativeNetRequest"
    ],
    "host_permissions": [
        "https://*/*"
    ],
    "declarative_net_request": {
        "rule_resources": [
            {
                "id": "ruleset_1",
                "enabled": true,
                "path": "rules.json"
            }
        ]
    }
}

```

### 2. `rules.json`
This file tells Chrome about your extension, including its name, version, and permissions. Here's the code:

```json
{
    "name": "Simple Ad Blocker",
    "version": "1.0.0",
    "manifest_version": 3,
    "permissions": [
        "declarativeNetRequest"
    ],
    "host_permissions": [
        "https://*/*"
    ],
    "declarative_net_request": {
        "rule_resources": [
            {
                "id": "ruleset_1",
                "enabled": true,
                "path": "rules.json"
            }
        ]
    }
}

```

## Step 3: Organizing the Files

1. Create a new folder on your computer (e.g., `SimpleAdBlocker`).
2. Place both `manifest.json` and `rules.json` inside this folder. **Make sure both files are in the same folder**, as the `manifest.json` file references the `rules.json` file.

---

## Step 4: Loading the Extension into Chrome

1. Open Google Chrome and go to `chrome://extensions/`.
2. Enable **Developer Mode** by toggling the switch in the top-right corner.
3. Click on **Load unpacked**.
4. Select the folder where your `manifest.json` and `rules.json` files are located (e.g., `SimpleAdBlocker`).
5. Your extension will now appear in the list of installed extensions.

---

## Step 5: Testing the Extension

To test if your ad blocker is working, follow these steps:

1. Visit a website that displays ads, such as a news website.
2. Open Chrome's Developer Tools (`Ctrl + Shift + I` or `Cmd + Option + I` on Mac).
3. Go to the **Network** tab and look for requests to `doubleclick.net` or `googleadservices.com`. These requests should be blocked.

## Conclusion

Congratulations! You've successfully created a simple ad blocker extension for Google Chrome. This extension blocks requests to specific ad-serving domains, improving your browsing experience. You can further customize it by adding more rules or exploring other features of the `declarativeNetRequest` API.

If you don't want to go through the entire process of creating the extension yourself, you can download my **ready-to-use extension** here:  
[Download Simple Ad Blocker Extension](https://drive.google.com/drive/folders/0By53oibND7d4flJqSTI2ZUJWcVJ1T01QYUR2aHZCdDU3aXQ4aWdjSEx3aHUwVTBhaTQ1SE0?resourcekey=0-odU4UHzJvTA0eqthlXHLtQ&usp=drive_link)

Simply download the file, extract it, and follow the steps in **Step 4** to load it into Chrome.

---

**Disclaimer**:  
1. This extension is for educational purposes only. Please respect the terms of service of websites and use ad blockers responsibly.  
2. This extension **may not work on YouTube** or other platforms that use advanced ad-serving techniques.  
3. Use at your own risk.  

Happy browsing! 🚀

