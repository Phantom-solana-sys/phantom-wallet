# Tutorial: How to Manually Load a Browser Extension (Unpacked)

This guide explains how to manually load a browser extension from a local folder (referred to as an *unpacked extension*) for development or testing purposes.

---

## 📋 Prerequisites
Before loading the extension, make sure your extension folder contains a **`manifest.json`** file directly in its root directory. This file is the primary configuration file required by the browser.

---

## 🌐 1. Google Chrome (and Chromium-based browsers like Brave, Opera)

Follow these steps for Google Chrome:

1. **Open the Extensions Page:**
   * Open Chrome, type `chrome://extensions` in the address bar, and press **Enter**.
   * Alternatively, click the **Menu (three dots)** icon in the top right -> **Extensions** -> **Manage Extensions**.

2. **Enable Developer Mode:**
   * In the top right corner of the Extensions page, toggle the **Developer mode** switch to active (blue).

3. **Load the Extension:**
   * Once Developer Mode is enabled, new buttons will appear in the top left.
   * Click the **Load unpacked** button.

4. **Select the Extension Folder:**
   * Browse to and select the folder that contains your extension files (where `manifest.json` is located).
   * Click **Select Folder**.

5. **Done!** Your extension is now installed and active. You can see it in the extensions list or pin it to the browser toolbar.

---

## 🌀 2. Microsoft Edge

Since Microsoft Edge is based on Chromium, the process is very similar to Chrome:

1. **Open the Extensions Page:**
   * Type `edge://extensions` in the address bar and press **Enter**.

2. **Enable Developer Mode:**
   * In the bottom left menu pane, toggle the **Developer mode** switch to active.

3. **Load the Extension:**
   * Click the **Load unpacked** button at the top of the page.

4. **Select the Folder:**
   * Select your extension folder (which contains `manifest.json`) and click **Select Folder**.

---

## 🦊 3. Mozilla Firefox

In Firefox, manual loading is **temporary** (it will be removed when Firefox is closed). If you want to load extensions permanently, you need *Firefox Developer Edition* or *Nightly* with specific configuration changes.

To load an extension temporarily:

1. **Open the Debugging Page:**
   * Type `about:debugging` in the address bar and press **Enter**.

2. **Go to "This Firefox":**
   * Click the **This Firefox** option in the left navigation sidebar.

3. **Load Temporary Add-on:**
   * Click the **Load Temporary Add-on...** button.

4. **Select a File:**
   * Navigate to your extension's folder and select **any file** inside it (selecting `manifest.json` is recommended).
   * Click **Open**.

5. **Done!** The extension will remain active until you close Firefox.

---

## 🔄 How to Reload the Extension After Modifying Code

If you make changes to the extension's source code (such as editing JavaScript, HTML, or CSS files), you do not need to remove and re-add the folder. Simply do the following:

* **Google Chrome / Microsoft Edge:**
  Find your extension's card on the `chrome://extensions` / `edge://extensions` page, and click the **Reload** (🔄) icon in the bottom right corner of the card.
* **Mozilla Firefox:**
  Go to `about:debugging#/runtime/this-firefox`, locate your extension, and click the **Reload** button.

---

## ⚠️ Troubleshooting

* **Error: "Manifest file is missing or unreadable"**
  * *Cause:* You selected the wrong parent folder, or `manifest.json` is not in the root of the folder you selected.
  * *Solution:* Make sure you select the specific folder that directly contains the `manifest.json` file.
* **Error: "Manifest version 2 is deprecated"**
  * *Cause:* Chrome now enforces the Manifest V3 standard.
  * *Solution:* Change `"manifest_version": 2` to `"manifest_version": 3` in your `manifest.json` and update any deprecated syntax if necessary.
