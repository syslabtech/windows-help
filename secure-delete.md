To **permanently delete a file in Windows** so that **no recovery tool** (like Recuva, EaseUS, etc.) can recover it — similar to how antivirus software or data wiping tools shred files — you need to **overwrite the file's data multiple times** before deletion.

### 🔒 Secure File Deletion with SDelete (Microsoft Sysinternals)

Use **`SDelete`**, a secure deletion tool from Microsoft that supports **DoD 5220.22-M (3-pass)** or **higher** levels of shredding.

---

### ✅ Step-by-Step Secure Deletion Command (5-Pass Shredding)

1. **Download SDelete:**

   * [https://learn.microsoft.com/en-us/sysinternals/downloads/sdelete](https://learn.microsoft.com/en-us/sysinternals/downloads/sdelete)
   * Extract it (you'll get `sdelete.exe`).

2. **Open Command Prompt as Administrator.**

3. **Run this command (5 passes):**

   ```cmd
   sdelete -p 5 -s -q "C:\Path\To\Your\File.txt"
   ```

   **Explanation:**

   * `-p 5` = overwrite file 5 times (shredding level 5).
   * `-s` = include subdirectories (optional).
   * `-q` = quiet mode.
   * Replace `"C:\Path\To\Your\File.txt"` with your actual file path.

---

### 🚫 Note

* After shredding, **the file is not recoverable**, even with forensic tools.
* For full disk erasure or free space wiping, you can run:

  ```cmd
  sdelete -p 5 -z C:
  ```

---

### ⚠️ Warning

Use this carefully. Once deleted this way, **the file is gone forever.** No recovery software will get it back — even military-grade tools will fail.

---

Great! Here's exactly how you can **run `sdelete`** after downloading the ZIP:

---

### ✅ Steps to Use `sdelete` (on Windows)

#### 1. **Extract the ZIP**

* Right-click the downloaded `SDelete.zip` file.
* Click **“Extract All…”** or use **7-Zip / WinRAR**.
* You’ll see a file called `sdelete.exe` (and possibly `sdelete64.exe`).

#### 2. **Open Command Prompt as Administrator**

* Press `Win + S`, type `cmd`.
* Right-click **Command Prompt**, select **“Run as administrator.”**

#### 3. **Navigate to the Folder**

In Command Prompt, navigate to the folder where you extracted `sdelete`.

For example:

```cmd
cd C:\Users\YourName\Downloads\SDelete
```

(Adjust the path to where you extracted it.)

#### 4. **Run SDelete Command**

Example to securely delete a file with 5-pass overwrite:

```cmd
sdelete64.exe -p 5 "C:\Path\To\Your\File.txt"
```

Or if you’re on a 32-bit system, use:

```cmd
sdelete.exe -p 5 "C:\Path\To\Your\File.txt"
```

---

### 🧪 Test It (Optional)

Try it on a test `.txt` file first to make sure it works as expected.

---

### 📝 Tips

* You can also **move `sdelete64.exe` to `C:\Windows\System32`** so you can run it from any location.

  ```cmd
  move sdelete64.exe C:\Windows\System32\
  ```

Then you can just type:

```cmd
sdelete64 -p 5 "C:\Path\To\File"
```

---

