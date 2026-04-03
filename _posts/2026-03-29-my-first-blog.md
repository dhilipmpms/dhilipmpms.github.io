---
layout: post
title: "Fingerprint Authentication on Ubuntu 24.04 — My 3-Year Linux Journey"
date: 2026-03-29
author: Dhilip
description: "After 3 years of trying, I finally got my HP laptop's ELAN fingerprint sensor working on Ubuntu. Here's how I did it."
---

<div class="blog-hero">
  <span class="blog-tag">Linux</span>
  <span class="blog-tag">Ubuntu</span>
  <span class="blog-tag">FOSS</span>
  <h1 class="blog-title">👋 Hey guys, I'm Dhilip</h1>
  <p class="blog-subtitle">After 3 years of my Linux journey, I finally achieved something I thought was impossible.</p>
</div>

<div class="card story-card">
  <div class="card-accent"></div>
  <p>
    I bought an HP laptop with a fingerprint reader. The same day I got it, I installed Ubuntu 😄<br>
    I never even tried the fingerprint sensor in Windows.
  </p>
  <p>But sadly… Linux didn't support it.</p>
  <p>
    For <b>2+ years</b>, I used my laptop without fingerprint login.<br>
    As a <b>FOSS activist</b>, I kept trying — but nothing worked.
  </p>
</div>

## 🔥 Breakthrough Moment

Two weeks ago, I found this blog:

<a href="https://johanneskinzig.com/fingerprint-authentication-with-ubuntu-2404-on-my-hp-envy-notebook.html" target="_blank" class="resource-link">
  <span class="link-icon">🔗</span>
  <span>Fingerprint Authentication Guide — Johannes Kinzig</span>
</a>

Even without hope, I read everything.

Then I discovered:


04f3:0c00 ELAN Fingerprint (Unsupported)


But then… I saw a pull request adding support for many devices — including mine 👀

Ubuntu hadn't merged it yet — so I built the driver myself 💪

---

## 💻 Fingerprint Authentication on Ubuntu 24.04

<img src="/assets/images/ubuntu.jpg" alt="Ubuntu" class="blog-img" loading="lazy">

<div class="card">
  <p>Many HP laptops use ELAN fingerprint sensors, which are not supported by default in Ubuntu 24.04.</p>
  <p>So we need to build a patched version of <code>libfprint</code>.</p>
</div>

---

## 📚 Resources

<div class="resources-grid">
  <a href="https://wiki.archlinux.org/title/Fprint" target="_blank" class="resource-link">
    <span class="link-icon">📖</span>
    <span>Arch Wiki — Fprint</span>
  </a>
  <a href="https://gitlab.freedesktop.org/depau/libfprint" target="_blank" class="resource-link">
    <span class="link-icon">🔧</span>
    <span>libfprint Fork (GitLab)</span>
  </a>
  <a href="https://gitlab.freedesktop.org/libfprint/libfprint/-/merge_requests/330" target="_blank" class="resource-link">
    <span class="link-icon">📝</span>
    <span>Merge Request #330</span>
  </a>
</div>

---

## ⚙️ Installation Steps

<div class="step-card">
  <div class="step-number">1</div>
  <div class="step-content">
    <h3>Install Dependencies</h3>

bash
sudo apt-get install meson glib-2.0 libgusb-dev \
  libgirepository1.0-dev libcairo-dev libpixman-1-dev \
  cmake libnss3-dev libgudev-1.0-dev gtk-doc-tools \
  gdb valgrind git openssl libssl-dev


  </div>
</div>

<div class="step-card">
  <div class="step-number">2</div>
  <div class="step-content">
    <h3>Clone Repository</h3>

bash
git clone https://gitlab.freedesktop.org/depau/libfprint.git
cd libfprint


  </div>
</div>

<div class="step-card">
  <div class="step-number">3</div>
  <div class="step-content">
    <h3>Switch Branch</h3>

bash
git switch elanmoc2
git fetch && git pull


  </div>
</div>

<div class="step-card">
  <div class="step-number">4</div>
  <div class="step-content">
    <h3>Build & Install</h3>

bash
meson setup builddir && cd builddir
meson compile
meson test
sudo meson install


  </div>
</div>

<div class="step-card">
  <div class="step-number">5</div>
  <div class="step-content">
    <h3>Fix Library Path</h3>

bash
echo '/usr/local/lib/' | sudo tee /etc/ld.so.conf.d/local.conf
sudo ldconfig


  </div>
</div>

<div class="step-card">
  <div class="step-number">6</div>
  <div class="step-content">
    <h3>Restart Service</h3>

bash
sudo systemctl restart fprintd.service


  </div>
</div>

<div class="step-card">
  <div class="step-number">7</div>
  <div class="step-content">
    <h3>Enroll Fingerprint</h3>

bash
fprintd-enroll $USER


<img src="/assets/images/login.png" alt="Fingerprint Login" class="blog-img" loading="lazy">

  </div>
</div>

<div class="step-card">
  <div class="step-number">8</div>
  <div class="step-content">
    <h3>Enable for sudo</h3>

bash
sudo pam-auth-update


<div class="img-row">
  <img src="/assets/images/sudo_user.png" alt="Sudo User Config" class="blog-img" loading="lazy">
  <img src="/assets/images/sudo.png" alt="Sudo with Fingerprint" class="blog-img" loading="lazy">
</div>

  </div>
</div>

---

## 🎉 Final Result

<div class="card result-card">
  <p>Now you can use your fingerprint for:</p>
  <ul class="result-list">
    <li><span class="check">✅</span> Login</li>
    <li><span class="check">✅</span> Sudo authentication</li>
    <li><span class="check">✅</span> System unlock</li>
  </ul>
</div>

---

## 💭 Final Thoughts

I hope this helps someone out there.

After 3 years… it finally worked.

**Linux is the best ❤️**

<div class="blog-footer">
  <p>© Dhilip | FOSS Enthusiast</p>
</div>