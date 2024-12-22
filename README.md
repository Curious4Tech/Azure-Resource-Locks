# Azure-Resource-Locks
This repository provides a step-by-step guide to applying Azure resource locks at the subscription, resource group, and individual resource levels. Perfect for beginners and professionals looking to enhance governance and security in Azure environments.

# 🔒 How to Apply Locks at Subscription, Resource Group, and Resource Levels in Azure  

## 📝 **Prerequisites**  

Before you start, ensure the following are in place:  

1. **Azure Subscription**  
   - 🟢 You must have at least one **`active Azure subscription`**.  
   - 🔑 Ensure you have sufficient permissions (**`Owner or User Access Administrator`**) to manage locks.  

2. **Resource Group**  
   - 📦 A resource group should already exist in your subscription.  
   - ➕ If you don't have one, create it by navigating to **`Resource Groups`** in the Azure portal and selecting **`+ Create`**.

3. **Resources**  
   - 💡 Deploy at least one resource (e.g., **`Virtual Machines, Storage Accounts, or Virtual network`**) in your resource group.

4. **Permissions**  
   - 👤 Verify that your account has **`Owner`** or **`User Access Administrator`** roles at the scope where you want to apply the lock (subscription, resource group, or individual resource).  

---

## 🛠️ **Step-by-Step Guide**  

### 1️⃣ **Navigate to the Azure Portal**  
- 🌐 Log in to the [Azure Portal](https://portal.azure.com/).  
- 🔍 Use the search bar to locate resources or navigate through the menus.  

---

### 2️⃣ **Apply a Lock at the Subscription Level**  
1. 🗂️ Search for **Subscriptions** in the portal and select your subscription.  
2. 🔒 Click **Locks** from the left-hand menu.  
3. ➕ Click **+ Add** to create a new lock.  
   - 🏷️ **Name**: Provide a meaningful name (e.g., `SubscriptionDeleteLock`).  
   - 🔑 **Lock Type**: Select **ReadOnly** or **CanNotDelete**.  
   - 📝 **Notes**: Add a description of why you're applying the lock.  
4. ✅ Click **OK** to save the lock.  

---

### 3️⃣ **Apply a Lock at the Resource Group Level**  
1. 📦 Search for **Resource Groups** and select your desired resource group.  
2. 🔒 Click **Locks** from the left-hand menu.  
3. ➕ Click **`+ Add`** to create a lock.  
   - 🏷️ **`Name`**: Provide a meaningful name (e.g., `RGProtectionLock`).  
   - 🔑 **Lock Type**: Select **`ReadOnly`** or **`Delete`**.  
   - 📝 **`Notes`**: Add relevant details.  
4. ✅ Click **`OK`** to save the lock.  

---

### 4️⃣ **Apply a Lock at the Individual Resource Level**  
1. 🔍 Navigate to the specific resource (e.g., **`Virtual Machine, Storage Account, Virtual network`**).  
2. 🔒 Under **`Settings`**, click **`Locks`**.  
3. ➕ Click **`+ Add`** to create a lock.  
   - 🏷️ **`Name`**: Provide a meaningful name (e.g., **`VMReadOnlyLock`**).  
   - 🔑 **`Lock Type`**: Select **`Read-Only`** or **`Delete`**.  
   - 📝 **`Notes`**: Add relevant details.  
4. ✅ Click **`OK`** to save the lock.  

---

### 5️⃣ **Verify the Applied Lock**  
- 📋 Return to the **`Locks`** blade for the respective level (**`subscription, resource group, or resource`**).  
- ✅ Confirm the lock is listed with the correct details.  

---

### 6️⃣ **Test the Lock Behavior**  
- 🛑 **For Read-Only locks**:  
  - Modifications should fail, but resources remain accessible in read-only mode.  
- 🛡️ **For Delete locks**:  
  - Deletions should fail, but modifications are allowed.  

---

### 🗑️ **Removing or Modifying Locks**  
1. Navigate to the **Locks** blade of the respective resource level.  
2. 🖱️ Select the lock you want to remove or modify.  
3. ❌ Click **`Delete`** to remove the lock or edit its properties.  

---

## ℹ️ **Additional Notes**  

- 🌍 Locks applied at the **`subscription level`** inherit automatically to all child resources, including resource groups and individual resources.  
- 🛠️ Locks at a **`lower level`** (e.g., resource group) add additional restrictions without overriding higher-level locks.  
- 🔑 **`Permissions`**: Only accounts with **Owner** or **`User Access Administrator`** roles can manage locks.  

---

### 🚀 **Benefits of Applying Locks**  
- ✅ Prevents accidental deletion or modification of critical resources.  
- ✅ Enhances governance and control over Azure environments.  

---

🔗 [Learn more about Azure Locks](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources)  

---

## 🌟 **Conclusion**

By implementing resource locks, you can safeguard your Azure environment against unintentional modifications and ensure better governance of your infrastructure. This guide simplifies the process with detailed instructions, ensuring that your subscription, resource groups, and individual resources remain secure.

💡 If you found this helpful, consider giving this repository a ⭐ and sharing it with others in your network!

