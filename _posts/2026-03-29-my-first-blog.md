# 👋 Hey guys, I'm Dhilip

After 3 years of my Linux journey, I finally achieved something I thought was impossible.

I bought an HP laptop with a fingerprint reader. The same day I got it, I installed Ubuntu 😄  
I never even tried the fingerprint sensor in Windows.

But sadly... Linux didn’t support it.

For **2+ years**, I used my laptop without fingerprint login.  
As a **FOSS activist**, I kept trying — but nothing worked.

## 🔥 Breakthrough Moment

Two weeks ago, I found this blog:

[Fingerprint Authentication Guide](https://johanneskinzig.com/fingerprint-authentication-with-ubuntu-2404-on-my-hp-envy-notebook.html)

Even without hope, I read everything.

Then I discovered:

04f3:0c00 ELAN Fingerprint (Unsupported)


But then... I saw a pull request adding support for many devices — including mine 👀

Ubuntu hadn’t merged it yet — so I built the driver myself 💪

---

## 💻 Fingerprint Authentication on Ubuntu 24.04

![Ubuntu](/assets/images/ubuntu.jpg)

Many HP laptops use ELAN fingerprint sensors, which are not supported by default in Ubuntu 24.04.

So we need to build a patched version of `libfprint`.

---

## 📚 Resources

- [Arch Wiki - Fprint](https://wiki.archlinux.org/title/Fprint)
- [libfprint Fork](https://gitlab.freedesktop.org/depau/libfprint)
- [Merge Request](https://gitlab.freedesktop.org/libfprint/libfprint/-/merge_requests/330)

---

## ⚙️ Installation Steps

### 1. Install Dependencies

sudo apt-get install meson glib-2.0 libgusb-dev libgirepository1.0-dev libcairo-dev libpixman-1-dev cmake libnss3-dev libgudev-1.0-dev gtk-doc-tools gdb valgrind git openssl libssl-dev


### 2. Clone Repository

git clone https://gitlab.freedesktop.org/depau/libfprint.git

cd libfprint

### 3. Switch Branch


### 4. Build & Install

meson setup builddir && cd builddir

meson compile

meson test

sudo meson install

### 5. Fix Library Path

echo '/usr/local/lib/' | sudo tee /etc/ld.so.conf.d/local.conf

sudo ldconfig

### 6. Restart Service

sudo systemctl restart fprintd.service

### 7. Enroll Fingerprint

fprintd-enroll $USER


![Login](/assets/images/login.png)

### 8. Enable for sudo


![Sudo User](/assets/images/sudo_user.png)
![Sudo](/assets/images/sudo.png)

---

## 🎉 Final Result

Now you can use your fingerprint for:

- Login
- Sudo authentication
- System unlock

---

## 💭 Final Thoughts

I hope this helps someone out there.

After 3 years… it finally worked.

**Linux is the best ❤️**

---

© Dhilip | FOSS Enthusiast
