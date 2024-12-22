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

![image](https://github.com/user-attachments/assets/83c2a4a7-03da-4d60-9bb7-277791076c55)

---

## 🛠️ **Step-by-Step Guide**  

### 1️⃣ **Navigate to the Azure Portal**  
- 🌐 Log in to the [Azure Portal](https://portal.azure.com/).  
- 🔍 Use the search bar to locate resources or navigate through the menus.  

---

### 2️⃣ **Apply a Lock at the Subscription Level**  
1. 🗂️ Search for **`Subscriptions`** in the portal and select your subscription.  
2. 🔒Expand **`Settings`** and then click **`Resource locks`** from the left-hand menu.

 ![image](https://github.com/user-attachments/assets/d46aa0f6-3453-4304-be45-c9e3fd11593c)
 
3. ➕ Click **`+ Add`** to create a new lock.  
   - 🏷️ **`Name`**: Provide a meaningful name (e.g., **`SubscriptionDeleteLock`**).  
   - 🔑 **`Lock Type`**: Select **`Read-Only`** or **`Delete`**.  
   - 📝 **`Notes`**: Add a description of why you're applying the lock.  
4. ✅ Click **`OK`** to save the lock.  

![image](https://github.com/user-attachments/assets/4ff97ea5-0ffe-4c03-adc3-92a666bf857e)

- 📋 Return to the **`Resource locks`** blade for the  **`subscription`** level.
- ✅ Confirm the lock is listed with the correct details.  
![image](https://github.com/user-attachments/assets/f80866b7-8593-4e06-b55a-5f2d08f46db3)

- Now, test the inheritance to confirm it works properly by deleting a resource group or resource within the subscription you have applied the delete lock.

![image](https://github.com/user-attachments/assets/49bd9a2e-473d-4f72-972e-be6fdfac78b1)

---

### 3️⃣ **Apply a Lock at the Resource Group Level**  

If you only have one suscription, delete the previous lock before testing the resource group level lock. For the sake fo this demo, I deletde the previous Lock at the subscription level.
1. 📦 Search for **Resource Groups** and select your desired resource group.  
2. 🔒 Expand **`Settings`** and then click **Locks** from the left-hand menu.

![image](https://github.com/user-attachments/assets/31220b99-cd22-40f6-8cc8-def076fa87f6)

3. ➕ Click **`+ Add`** to create a lock.  
   - 🏷️ **`Name`**: Provide a meaningful name (e.g., `RGProtectionLock`).  
   - 🔑 **Lock Type**: Select **`Read-Only`** or **`Delete`**.  
   - 📝 **`Notes`**: Add relevant details.  
4. ✅ Click **`OK`** to save the lock.  

![image](https://github.com/user-attachments/assets/629f2cfa-b80a-4f0a-84c3-797e5be0f25e)

 - 📋 Return to the **`Locks`** blade for the  **`Resource Group`** level.
 - ✅ Confirm the lock is listed with the correct details.  
![image](https://github.com/user-attachments/assets/54a1af03-c023-4378-beca-8d336aba7d3b)

 - Now, test the inheritance to confirm it works properly by modifying an individual resource within the resource group you have applied the Read-Only lock.

![image](https://github.com/user-attachments/assets/4465d5d9-a8cd-444c-8f29-5ce95ce91867)

---

### 4️⃣ **Apply a Lock at the Individual Resource Level**  

If you only have one resource group, delete the previous lock before testing the individual resource level lock. For the sake fo this demo, I deletde the previous Lock at the resource group level.
1. 🔍 Navigate to the specific resource (e.g., **`Virtual Machine, Storage Account, Virtual network`**).  
2. 🔒 Under **`Settings`**, click **`Locks`**.

![image](https://github.com/user-attachments/assets/5ec2c235-4eb4-4cde-982c-5ab1e521c49e)

3. ➕ Click **`+ Add`** to create a lock.  
   - 🏷️ **`Name`**: Provide a meaningful name (e.g., **`VnetDeleteLock`**).  
   - 🔑 **`Lock Type`**: Select **`Read-Only`** or **`Delete`**.  
   - 📝 **`Notes`**: Add relevant details.  
4. ✅ Click **`OK`** to save the lock.  

![image](https://github.com/user-attachments/assets/ccb92b59-9f05-44ef-8e79-4b31620207a3)

 - 📋 Return to the **`Locks`** blade for the  **`Resource`** level.
 - ✅ Confirm the lock is listed with the correct details.  
![image](https://github.com/user-attachments/assets/6355cf68-64ea-4d10-9d90-4f5b604a4e4b)

 - Now, test to confirm it works properly by deleting the individual resource on which you have applied the Delete lock.

![image](https://github.com/user-attachments/assets/000087f5-1987-479a-a9a7-54fd26fc44e4)

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

