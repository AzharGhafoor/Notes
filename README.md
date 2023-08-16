# PIP Not Getting Installed in Ubuntu?

### Command I Used: `ubuntu@ubuntu:/$ sudo apt install python3-pip`
### Error

`
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package python3-pip is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'python3-pip' has no installation candidate
`

### Solution
It looks like the 'python3-pip' package is not available in our current package repositories. This could be due to a misconfiguration or an issue with the package sources.

To address this issue, one can try the following steps:

**Step 1: Update Package Lists**

To ensure that you have the latest information about available packages, update your package lists:

```
sudo apt update
```

**Step 2: Check Package Repository**

Inspect the contents of the package repository configuration files to ensure that valid sources are defined:
```
cat /etc/apt/sources.list
ls /etc/apt/sources.list.d/
```

**Step 3: Refresh Repository Information**

Refresh the repository information to make sure you have the most recent data: 
```
sudo apt update
```

**Step 4: Enable Universe Repository**

The 'python3-pip' package is commonly found in the "universe" repository. Ensure that it's enabled:

```
sudo add-apt-repository universe
sudo apt update
```

**Step 5: Install 'python3-pip'**

Once you've enabled the "universe" repository, try installing 'python3-pip' again: 

```
sudo apt install python3-pip
```

If the installation is successful, you should see the version of 'pip' installed when you run: 

```
pip3 --version
```

