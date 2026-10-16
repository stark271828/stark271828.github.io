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

## Professional Appointments

<div class="career-list">
  <article class="career-entry">
    <h3 class="career-title">Postdoctoral Researcher</h3>
    <div class="career-date"><time datetime="2024-12">Dec 2024</time> – Present</div>
    <div class="career-details">
      <div class="career-institution">National Laboratory of the Rockies (NLR)</div>
      <div>Power Systems Engineering Center</div>
      <div class="career-location">Golden, Colorado, USA</div>
    </div>
  </article>
  <article class="career-entry">
    <h3 class="career-title">Research Intern</h3>
    <div class="career-date"><time datetime="2023-03">Mar 2023</time> – <time datetime="2024-12">Dec 2024</time></div>
    <div class="career-details">
      <div class="career-institution">National Laboratory of the Rockies (NLR)</div>
      <div>Power Systems Engineering Center</div>
      <div class="career-location">Golden, Colorado, USA</div>
    </div>
  </article>
  <article class="career-entry">
    <h3 class="career-title">Research Assistant</h3>
    <div class="career-date"><time datetime="2018-08">Aug 2018</time> – <time datetime="2023-05">May 2023</time></div>
    <div class="career-details">
      <div class="career-institution">The University of Georgia (UGA)</div>
      <div>Intelligent Power Electronics and Electric Machine Laboratory</div>
      <div class="career-location">Athens, Georgia, USA</div>
    </div>
  </article>
</div>

---

## Education

<div class="career-list">
  <article class="career-entry">
    <h3 class="career-title">Ph.D. in Electrical and Computer Engineering</h3>
    <time class="career-date" datetime="2023">2023</time>
    <div class="career-details">
      <div class="career-institution">The University of Georgia</div>
      <div class="career-location">Athens, Georgia, USA</div>
    </div>
  </article>
  <article class="career-entry">
    <h3 class="career-title">B.Sc. in Electrical Engineering</h3>
    <time class="career-date" datetime="2018">2018</time>
    <div class="career-details">
      <div class="career-institution">Huazhong University of Science and Technology</div>
      <div class="career-location">Wuhan, Hubei, China</div>
    </div>
  </article>
</div>

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
