---
layout: post
title:  "Docker Installation in Windows and Troubleshooting"
date:   2022-05-11 0:19:48 +0900
category: DevOps
---

# WSL2 installation
---


WSL2 is required to run Docker, so install it.
If possible, we recommend installing in step 1.
If you cannot install in step 1, perform step 2.

### Step 1
1. Execute the following command in PowerShell to check the installable distribution.

{% highlight ruby %}
  wsl --list --online
{% endhighlight %}

*If the command cannot be executed due to an error, perform step 2.

2. Select one from the installable distributions and install with the following command. (The following command installs Ubuntu-20.04)

{% highlight ruby %}
  wsl --install -d Ubuntu-20.04
{% endhighlight %}

3. After executing the following command, restart the PC.

{% highlight ruby %}
  wsl --update
{% endhighlight %}

4. After restarting, start the installed application (Linux distribution).

5. Execute the following command with PowerShell and confirm that the version of the installed application is "2".

{% highlight ruby %}
  wsl -l -v
{% endhighlight %}

### Step 2

1. Search for "Ubuntu" in the Microsoft Store and install the Linux distribution.

2. Launch the installed application (Linux distribution).

3. Execute the following command with PowerShell and confirm that the version of the installed application is "1".

{% highlight ruby %}
  wsl -l -v
{% endhighlight %}

4. Execute the following command to change the version of the installed application. (Replace the command Ubuntu-20.04 according to the installed application.)

{% highlight ruby %}
  wsl --set-version Ubuntu-20.04 2
{% endhighlight %}

*If an error occurs in 4, execute steps 3 and 4 linked below.

[https://docs.microsoft.com/ja-jp/windows/wsl/install-manual](https://docs.microsoft.com/ja-jp/windows/wsl/install-manual#step-3---enable-virtual-machine-feature)

5. Restart your PC.

6. After restarting, execute the following command in PowerShell and confirm that the installed application version is "2".

{% highlight ruby %}
  wsl -l -v
{% endhighlight %}


# Docker Desktop installation

---

Use Docker Desktop to use Docker on Windows.

1. Download from the official website and execute.

[Official site](https://docs.docker.com/desktop/windows/install/)

2. After running the installer, the PC will be restarted automatically.

  *If it is not restarted automatically, restart it manually.

3. Confirm that the error occurs in Docker after restarting.

4. Follow step 5 in the link below to add your own account that uses Docker to the user group "docker-users".

[Click to this Link](https://l.facebook.com/l.php?u=https%3A%2F%2Fmatsuand.github.io%2Fdocs.docker.jp.onthefly%2Fdesktop%2Fwindows%2Finstall%2F%3Ffbclid%3DIwAR01kuuQfaIj2a_qKjSp49rOfnDUVkvJKIc-J9SPYQCXJ_QROGMDbtiJ8jU%23install-docker-desktop-on-windows&h=AT2Ds8V5wl8jWTaiPmRcGiYqj1wFmDAWibUyMT2681V8FM2sJ_fi8X4dsedHb4DG-e97pKGqyjO5AwlkuoCMj9i97Pzkijj9HSqYoikwyo7BjigFBsyYtV3r8zfmutFwNka8fzEfA9M)

  *Since Microsoft AD is used, it may not be possible to execute from the GUI. Since Infrastructure knows the command, ask him to execute it.

5. After restarting the PC, check that Docker starts normally.

6. With Docker running, open PowerShell, etc., execute the following command, and if "Hello from Docker!" Is displayed, installation is complete.

{% highlight ruby %}
  docker run hello-world
{% endhighlight %}

# Other notes

### VMware does not start after installing Docker

Occurs because older versions of VMware and WSL2 cannot coexist.

The solution is to update VMware.

See below for details.

Development Tips List / If VMware does not start after installing Docker

Happy Coding :)
