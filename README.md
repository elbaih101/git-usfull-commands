# git-usfull-commands

To use the `git -c http.sslVerify=false` command by default in IntelliJ IDEA for operations like pulling, fetching, or rebasing, you can configure Git settings for your project or globally.

Here’s how to do it:

### 1. **Set the Git Configuration in IntelliJ IDEA:**

You can configure Git to disable SSL verification by editing the Git configuration file or by setting it via IntelliJ IDEA.

#### Option 1: Configure globally in Git
Run the following command in your terminal to disable SSL verification globally:

```bash
git config --global http.sslVerify false
```

This will apply to all repositories on your machine.

#### Option 2: Configure locally for a specific repository
If you want to disable SSL verification only for a specific repository, navigate to the repository directory and run:

```bash
git config http.sslVerify false
```

#### Option 3: Use IntelliJ IDEA's Git Configuration Settings
- Go to **File > Settings (or Preferences on macOS)**.
- Under **Version Control**, click on **Git**.
- Check if your Git executable path is set correctly and make sure the repository URL is correct.
- If you still face issues, you can set the configuration from the terminal using the commands mentioned earlier.

### 2. **Using the `-c` Flag with Git Commands in IntelliJ IDEA:**

If you specifically need to use `git -c http.sslVerify=false` for commands such as `pull`, `fetch`, or `rebase` in IntelliJ IDEA, you would have to manually run these commands in the terminal because IntelliJ does not have an option to add the `-c` flag for Git commands in its GUI.

Here’s how you can do it:
1. Open the **Terminal** inside IntelliJ IDEA (bottom panel).
2. Run the command like:

   ```bash
   git -c http.sslVerify=false fetch
   git -c http.sslVerify=false pull
   git -c http.sslVerify=false rebase
   ```

Alternatively, if you want to integrate it into your workflows (like rebasing or pulling), you can use the global or local Git configuration options mentioned above for a more permanent solution.

### 3. **Why SSL verification might fail:**
If you're running into SSL certificate errors, it’s typically because:
- The server's SSL certificate is not trusted by your system.
- The certificate chain is broken, or the repository server uses a self-signed certificate.

Disabling SSL verification with `http.sslVerify=false` can bypass this issue, but it’s not recommended for production or security-sensitive environments as it can expose you to man-in-the-middle attacks.

Let me know if you need more help!
