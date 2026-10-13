---
layout: about
title: Home
profile:
  enabled: true
  image: "/assets/img/profile_by.jpg"
  alt: "Portrait of Bowen Yang"
  caption: ""
  align: right
  width: 160px
sections: []
---
<p class="eyebrow">Power electronics · Control · Power systems</p>

<p class="editor-note">I am a Postdoctoral Researcher at the National Laboratory of the Rockies (formerly NREL). I received my Ph.D. in Electrical and Computer Engineering from the University of Georgia in 2023. My research focuses on the modeling and control of power electronics and converter-dominated power systems, with particular interests in grid-forming inverters, medium-voltage modular power converters, solid-state transformers, solid-state circuit breakers, and cyber-physical security. My work tries to bridge fundamental theoretical analysis with practical implementation and validation, aiming to develop more reliable, resilient, and scalable power electronics technologies for next-generation energy systems.</p>

<p class="bio-quote">
  “Scientists discover the world that exists; engineers create the world that never was.” -- Theodore von Kármán
</p>

---

## Research Interests
- Current-Limiting Control of Grid-Forming Inverters
- Stability and Resilience of Heterogeneous Converter Networks
- Power System Black Start and Restoration with Inverter-Based Resources
- Decentralized Control of Modular Power Converters
- Solid-State Protection and Grid-Support Technologies
- Multi-Domain Modeling of Cyber-Physical Power Electronics Systems
- Physics-Guided Data-Driven Condition Monitoring

[Research Topics]({{ '/research/' | relative_url }}) \| [Research Projects]({{ '/projects/' | relative_url }})

--- 

## Latest News

{% include news.html limit=6 %}

[All News]({{ '/news/' | relative_url }})

---

## Selected Recent Publications

{% bibliography --query @*[selected=true] %}

[All publications]({{ '/publications/' | relative_url }})