# A-classic-error-in-calculating-the-crown-volume
The Flawed Math Too Many Papers Still Use for Crown Volume Calculations
It’s honestly shocking how many academic papers rely on fundamentally incorrect math when estimating tree crown volume. Some of these methods manage to produce numbers that look reasonable—but scratch the surface, and the mathematical holes are glaring. And yes, they absolutely need to be called out.
In LiDAR-based crown volume estimation, the so-called frustum method has become the go to approach. The idea is simple: slice the crown vertically into layers (equally or unevenly spaced point clouds), compute the area of each layer’s upper and lower boundary, estimate the volume of that slice, sum them up, and boom—total canopy volume.
Sounds fine in theory. The problem? How most researchers calculate the layer volume.
The vast majority plug the two boundary areas into the classic frustum volume formula:
V = h/3 × (A₁ + A₂ + √(A₁ × A₂))
Let’s be blunt: this is mathematically reckless. That formula only holds if the solid is a true frustum—a definition clearly laid out on Wikipedia. But in the real world, crown are messy. The upper boundary might be roughly circular; the lower boundary could be closer to a triangle. There’s no mathematical justification for jamming such irregular shapes into a formula that assumes strict geometric preconditions.
Some scholars have caught on. They keep the layer by layer concept but switch to a far more defensible approximation: average the two boundary areas and multiply by the layer height.
V = h × (A₁ + A₂) / 2
This isn’t perfect, but it’s engineering math—a deliberate, transparent approximation with a solid logical foundation. It works because it doesn’t pretend the canopy obeys rules it clearly doesn’t.
Here’s the frustrating part: an embarrassing number of published papers—far too many to list here, though I’ve included a few below—have slipped through peer review using that bogus frustum formula. Worse, papers relying on this method with zero theoretical grounding are still being published as recently as 2019. That’s not just lazy; it’s academically indefensible. Methods without mathematical legitimacy don’t suddenly become valid because they’ve been used before. It’s time we stop treating them as if they do.

