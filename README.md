
# ⚠️ A Classic Error in Calculating the Crown Volume

[![Status](https://img.shields.io/badge/status-critical%20review-red)]()
[![Topic](https://img.shields.io/badge/topic-LiDAR%20%7C%20forestry%20%7C%20biometrics-blue)]()
[![Year](https://img.shields.io/badge/year-2025%2B-critical)]()

&gt; **TL;DR**: A widely-used frustum formula in tree crown volume estimation is mathematically invalid for irregular crown shapes. This repository documents the flaw and proposes the correct alternative.

---

## 🎯 The Problem

In LiDAR-based crown volume estimation, the **frustum method** has become the de facto standard:

1. Slice the crown vertically into layers (equally or unevenly spaced)
2. Compute the area of each layer's upper ($A_1$) and lower ($A_2$) boundary
3. Estimate the volume of each slice
4. Sum for total canopy volume

**Sounds reasonable in theory. The issue? How most researchers calculate layer volume.**

---

## ❌ The Flawed Approach

The vast majority plug the two boundary areas into the classic frustum formula:

$$V = \frac{h}{3} \times (A_1 + A_2 + \sqrt{A_1 \times A_2})$$

&gt; **⚠️ Warning**: This is mathematically reckless.

That formula **only holds if the solid is a true frustum**—a definition clearly laid out on [Wikipedia](https://en.wikipedia.org/wiki/Frustum). But real-world crowns are messy:
- Upper boundary: roughly circular
- Lower boundary: closer to a triangle

**There is no mathematical justification** for forcing irregular shapes into a formula that assumes strict geometric preconditions.

---

## ✅ The Correct Alternative

Some scholars have caught on. They retain the layer-by-layer concept but switch to a defensible approximation:

$$V = h \times \frac{(A_1 + A_2)}{2}$$

| Aspect | Frustum Formula | Average Area Method |
|--------|----------------|---------------------|
| **Assumption** | Strict geometric similarity | None (transparent approximation) |
| **Mathematical rigor** | ❌ Invalid for irregular shapes | ✅ Engineering approximation |
| **Transparency** | Pretends precision | Acknowledges uncertainty |

&gt; This isn't perfect, but it's **engineering math**—a deliberate, transparent approximation with solid logical foundation. It works because it doesn't pretend the canopy obeys rules it clearly doesn't.

---

## 📚 Evidence from Literature

An embarrassing number of published papers have slipped through peer review using the bogus frustum formula. 

&gt; **Key finding**: Papers relying on this method with zero theoretical grounding are still being published as recently as **2019**.

**This isn't just lazy; it's academically indefensible.** Methods without mathematical legitimacy don't suddenly become valid because they've been used before.

---

