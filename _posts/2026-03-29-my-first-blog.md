you give seperate seperate copy 

i want to copy 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fingerprint on Ubuntu - Dhilip</title>



<style>
body {
    font-family: 'Segoe UI', sans-serif;
    line-height: 1.7;
    margin: 0;
    background: #0f172a;
    color: #e2e8f0;
}

.container {
    max-width: 900px;
    margin: auto;
    padding: 40px 20px;
}

h1, h2, h3 {
    color: #38bdf8;
}

h1 {
    font-size: 2.5rem;
}

p {
    color: #cbd5f5;
}

.card {
    background: #1e293b;
    padding: 20px;
    border-radius: 12px;
    margin: 20px 0;
}

code {
    background: #020617;
    padding: 4px 8px;
    border-radius: 6px;
    color: #38bdf8;
}

pre {
    background: #020617;
    padding: 15px;
    border-radius: 10px;
    overflow-x: auto;
}

img {
    width: 100%;
    border-radius: 10px;
    margin-top: 10px;
}

a {
    color: #38bdf8;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
}

.footer {
    text-align: center;
    margin-top: 40px;
    opacity: 0.7;
}
</style>
</head>


<body>

<div class="container">

<h1>👋 Hey guys, I'm Dhilip</h1>

<p>
After 3 years of my Linux journey, I finally achieved something I thought was impossible.
</p>

<div class="card">
<p>
I bought an HP laptop with a fingerprint reader. The same day I got it, I installed Ubuntu 😄  
I never even tried the fingerprint sensor in Windows.
</p>

<p>
But sadly... Linux didn’t support it.
</p>

<p>
For <b>2+ years</b>, I used my laptop without fingerprint login.  
As a <b>FOSS activist</b>, I kept trying — but nothing worked.
</p>
</div>

<h2>🔥 Breakthrough Moment</h2>

<p>
Two weeks ago, I found this blog:
</p>

<p>
<a href="https://johanneskinzig.com/fingerprint-authentication-with-ubuntu-2404-on-my-hp-envy-notebook.html" target="_blank">
Fingerprint Authentication Guide
</a>
</p>

<p>
Even without hope, I read everything.
</p>

<p>
Then I discovered:
</p>

<pre>
04f3:0c00 ELAN Fingerprint (Unsupported)
</pre>

<p>
But then... I saw a pull request adding support for many devices — including mine 👀
</p>

<p>
Ubuntu hadn’t merged it yet — so I built the driver myself 💪
</p>

---

<h2>💻 Fingerprint Authentication on Ubuntu 24.04</h2>

![Ubuntu](/assets/images/ubuntu.jpg)

<div class="card">
<p>
Many HP laptops use ELAN fingerprint sensors, which are not supported by default in Ubuntu 24.04.
</p>

<p>
So we need to build a patched version of <code>libfprint</code>.
</p>
</div>

---

<h2>📚 Resources</h2>

<ul>
<li><a href="https://wiki.archlinux.org/title/Fprint">Arch Wiki - Fprint</a></li>
<li><a href="https://gitlab.freedesktop.org/depau/libfprint">libfprint Fork</a></li>
<li><a href="https://gitlab.freedesktop.org/libfprint/libfprint/-/merge_requests/330">Merge Request</a></li>
</ul>

---

<h2>⚙️ Installation Steps</h2>

<h3>1. Install Dependencies</h3>

<pre>
sudo apt-get install meson glib-2.0 libgusb-dev libgirepository1.0-dev libcairo-dev libpixman-1-dev cmake libnss3-dev libgudev-1.0-dev gtk-doc-tools gdb valgrind git openssl libssl-dev
</pre>

---

<h3>2. Clone Repository</h3>

<pre>
git clone https://gitlab.freedesktop.org/depau/libfprint.git
cd libfprint
</pre>

---

<h3>3. Switch Branch</h3>

<pre>
git switch elanmoc2
git fetch && git pull
</pre>

---

<h3>4. Build & Install</h3>

<pre>
meson setup builddir && cd builddir
meson compile
meson test
sudo meson install
</pre>

---

<h3>5. Fix Library Path</h3>

<pre>
echo '/usr/local/lib/' | sudo tee /etc/ld.so.conf.d/local.conf
sudo ldconfig
</pre>

---

<h3>6. Restart Service</h3>

<pre>
sudo systemctl restart fprintd.service
</pre>

---

<h3>7. Enroll Fingerprint</h3>

<pre>
fprintd-enroll $USER
</pre>

![Login](/assets/images/login.png)

---

<h3>8. Enable for sudo</h3>

<pre>
sudo pam-auth-update
</pre>

![Sudo User](/assets/images/sudo_user.png)
![Sudo](/assets/images/sudo.png)

---

<h2>🎉 Final Result</h2>

<div class="card">
<p>
Now you can use your fingerprint for:
</p>

<ul>
<li>Login</li>
<li>Sudo authentication</li>
<li>System unlock</li>
</ul>
</div>

---

<h2>💭 Final Thoughts</h2>

<p>
I hope this helps someone out there.
</p>

<p>
After 3 years… it finally worked.
</p>

<p><b>Linux is the best ❤️</b></p>

<div class="footer">
<p>© Dhilip | FOSS Enthusiast</p>
</div>

</div>

</body>
</html> 