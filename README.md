<div align="center">

# 🎮 BattleFree — Public Assets CDN

### 🖼️ Static Image & Asset Hosting Repository

<img src="https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge" />
<img src="https://img.shields.io/badge/Type-Static%20Asset%20Host-blue?style=for-the-badge" />
<img src="https://img.shields.io/badge/Powered%20By-GitHub%20Pages-black?style=for-the-badge&logo=github" />
<img src="https://img.shields.io/badge/Saves-Supabase%20Egress-orange?style=for-the-badge&logo=supabase" />

```
   ____        _   _   _      _____              
  | __ )  __ _| |_| |_| | ___|  ___| __ ___  ___ 
  |  _ \ / _` | __| __| |/ _ \ |_ | '__/ _ \/ _ \
  | |_) | (_| | |_| |_| |  __/  _|| | |  __/  __/
  |____/ \__,_|\__|\__|_|\___|_|  |_|  \___|\___|

        📦  P U B L I C   A S S E T S   C D N
```

</div>

---

## 📌 Overview

This repository is dedicated to hosting all **public images and static assets** used by the **BattleFree** app.

Its main purpose is to serve every image used inside the app (icons, banners, avatars, backgrounds, UI assets, etc.) through a **direct public URL**, instead of storing them in **Supabase Storage**.

> 💡 **In short:** It works like a lightweight, free, and fast **image CDN** — built exclusively for BattleFree.

---

## 🎯 Purpose / Why This Exists

| ❌ Before (Supabase Storage) | ✅ Now (GitHub Repo) |
|---|---|
| Every image load/download consumed **egress bandwidth** | Free static delivery via GitHub / GitHub Pages |
| Supabase's **free egress limit** ran out quickly | No egress cost — completely offloaded |
| Both storage cost and bandwidth cost applied | Only repository storage, no running cost |
| Extra API calls / auth overhead for assets | Direct raw public URL — no auth, no overhead |

**In simple terms:** Supabase Storage consumes money/limits from its egress quota every time an image is served. By hosting static assets on GitHub instead, the app fetches images directly via a **raw GitHub URL / GitHub Pages URL** — resulting in **zero egress cost and zero storage load** on the Supabase side.

---

## 🗂️ Folder Structure

```
battlefree-assets/
│
├── icons/            → All app icons (UI, buttons, nav, etc.)
├── banners/          → Promotional & event banners
├── avatars/          → Default/placeholder avatar images
├── backgrounds/      → Game/app background images
├── logos/            → Brand logos (light/dark variants)
├── misc/             → Any other public static asset
│
└── README.md
```

> 📁 Naming convention: always use **lowercase-kebab-case**  
> Example: `battle-win-banner.png`, `user-avatar-default.svg`

---

## 🔗 How to Use

To load any image from this repo in the app, simply use its **raw GitHub URL**:

```
https://raw.githubusercontent.com/<username>/<repo-name>/main/<folder>/<file-name>
```

**Example:**

```js
const bannerUrl = "https://raw.githubusercontent.com/yourusername/battlefree-assets/main/banners/event-banner.png";

<img src={bannerUrl} alt="Event Banner" />
```

> ⚡ **Recommended:** Enable GitHub Pages in the repo settings — this gives you a clean, custom-domain-style URL along with better CDN-level caching.

```
https://<username>.github.io/battlefree-assets/<folder>/<file-name>
```

---

## ➕ How to Add a New Asset

1. Select the correct folder (`icons/`, `banners/`, etc.) — create a new one if it doesn't exist.
2. Upload the image after **optimizing** it (compressed PNG/WEBP/SVG — keep the file size small).
3. Write a clear commit message — e.g. `add: new diwali event banner`
4. Once merged and pushed, the GitHub Pages/raw URL updates automatically.
5. Use the new URL in the app code — no backend changes needed.

---

## ⚙️ Best Practices

- ✅ Always **compress/optimize** images before pushing (TinyPNG, Squoosh, etc.)
- ✅ Use SVG wherever possible — lightweight and scalable
- ✅ Keep asset names **descriptive**
- ✅ Don't put large video or heavy files in this repo — **images & light static assets only**
- ✅ Never store sensitive/user-specific data here — this repo is **fully public**

---

## 🚫 What This Repo Is NOT For

- ❌ User-generated or private content (that stays in Supabase Storage)
- ❌ Dynamic or frequently-changing data
- ❌ Large video files or heavy media

---

## 🧩 Tech Behind It

<div align="center">

<img src="https://img.shields.io/badge/Hosting-GitHub%20Pages-181717?style=flat-square&logo=github" />
<img src="https://img.shields.io/badge/Delivery-Raw%20Content%20CDN-2088FF?style=flat-square&logo=githubactions" />
<img src="https://img.shields.io/badge/Cost-Free-success?style=flat-square" />

</div>

---

## 🤝 Contributing

To add new assets or update existing ones, simply raise a PR. Make sure to include a clear description and place files in the correct folder.

---

<div align="center">

### 🕹️ Built for **BattleFree**
_Fast • Free • Egress-Friendly Asset Delivery_

</div>
