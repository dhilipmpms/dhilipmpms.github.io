---
layout: post
title: "Reviving My Pixel XL with LineageOS — A Lesson Learned"
date: 2026-04-03
author: Dhilip
description: "How I gave a second life to an old Pixel XL by installing LineageOS, and why official documentation is your best friend."
---

<div class="blog-hero">
  <span class="blog-tag">Android</span>
  <span class="blog-tag">LineageOS</span>
  <span class="blog-tag">Custom ROM</span>
  <span class="blog-tag">Pixel XL</span>
  <h1 class="blog-title">📱 Giving New Life to an Old Pixel XL</h1>
  <p class="blog-subtitle">From a bricked bootloop to a smooth LineageOS experience.</p>
</div>

<div class="card story-card">
  <div class="card-accent"></div>
  <p>
    I recently decided to install <b>LineageOS</b> on my Pixel XL. It was a great way to give a "second life" to my friend's old mobile device.
  </p>
  <p>
    The performance is incredible, but the journey wasn't as smooth as I expected.
  </p>
</div>

---

## 🔑 The Golden Rule: Unlock the Bootloader

The first and most important step in the custom ROM journey is unlocking the bootloader. Without doing this, you cannot install any custom firmware.

<div class="card">
  <p>Unlocking the bootloader allows you to flash custom partitions, which is essential for any modding project.</p>
</div>

---

## ⚙️ Preparation Steps

<div class="step-card">
  <div class="step-number">1</div>
  <div class="step-content">
    <h3>Enable Developer Options</h3>
    <p>Go to Settings > About Phone and tap "Build Number" seven times.</p>
  </div>
</div>

<div class="step-card">
  <div class="step-number">2</div>
  <div class="step-content">
    <h3>Enable OEM Unlocking</h3>
    <p>Inside Developer Options, toggle the "OEM Unlocking" switch to ON.</p>
  </div>
</div>

<div class="step-card">
  <div class="step-number">3</div>
  <div class="step-content">
    <h3>Enable USB Debugging</h3>
    <p>This allows your computer to communicate with the device via ADB.</p>
  </div>
</div>

<div class="step-card">
  <div class="step-number">4</div>
  <div class="step-content">
    <h3>Unlock Bootloader</h3>
    <p>Using ADB/Fastboot commands to finalize the unlock process.</p>
  </div>
</div>

---

## ⚠️ The Bricking Incident (Lesson Learned)

After unlocking the bootloader, I got a bit overconfident. Instead of following the **official LineageOS guide**, I used an AI bot to guide the installation. 

**Big mistake.**

<div class="card story-card" style="border-left-color: #ff4757;">
  <div class="card-accent" style="background: #ff4757;"></div>
  <p>
    I ended up bricking my device. It was stuck in a terrifying bootloop.
  </p>
  <img src="/assets/images/bootloop.jpg" alt="Bootloop" class="blog-img" loading="lazy">
</div>

<div class="card story-card" style="border-left-color: #ff4757; background: rgba(255, 71, 87, 0.05);">
  <div class="card-accent" style="background: #ff4757;"></div>
  <p>
    <b>⚠️ Lesson Learned:</b> Always stick to official articles, wikis, and documentation. AI is great for explaining concepts, but for critical technical steps, the official source is the only source you should trust.
  </p>
</div>

---

## ✨ Fixing and Installing

After fixing the bricked state, I went back to the basics and followed the official LineageOS Wiki.

<div class="card">
  <p>Following the correct steps made everything fall into place. The installation was smooth once I followed the verified guide.</p>
  <img src="/assets/images/boot.jpg" alt="LineageOS Installation" class="blog-img" loading="lazy">
</div>

---

## 🎉 Final Result

The Pixel XL is now running smooth and fast on LineageOS!

<img src="/assets/images/lineageos.jpg" alt="Pixel XL Running LineageOS" class="blog-img" loading="lazy">

<div class="card result-card">
  <p>The benefits are clear:</p>
  <ul class="result-list">
    <li><span class="check">✅</span> Better Performance</li>
    <li><span class="check">✅</span> Enhanced Privacy</li>
    <li><span class="check">✅</span> Latest Security Patches</li>
    <li><span class="check">✅</span> No Bloatware</li>
  </ul>
</div>

---

## 💭 Final Thoughts

Installing a custom ROM is a rewarding experience, but it requires patience and precision. Don't take shortcuts, and always respect the official documentation.

**Happy Modding! 🚀**

<div class="blog-footer">
  <p>© Dhilip | Android & FOSS Enthusiast</p>
</div>
