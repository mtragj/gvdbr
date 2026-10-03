---
layout: page-fullwidth
title: "Sponsors"
subheadline:
teaser: "Thank you to the businesses that make the 2026 Grand Valley Dirt Bike Rally possible."
header:
  image_fullwidth: singletrack_plains_header.png
permalink: "/sponsors/"
---
<!--more-->

<style>
/* Tier heading */
.sponsor-tier-title {
  text-align: center;
  margin: 40px 0 20px;
  padding-bottom: 8px;
  border-bottom: 3px solid #ddd;
}
.sponsor-tier-title.platinum { border-color: #b8c2cc; }
.sponsor-tier-title.gold     { border-color: #d4a017; }
.sponsor-tier-title.silver   { border-color: #a8a8a8; }
.sponsor-tier-title.bronze   { border-color: #b0733a; }

/* Sponsor grid container */
.sponsor-row {
  display: flex;
  justify-content: center;
  gap: 30px;              /* Equal spacing between items */
  margin-bottom: 40px;    /* Space between rows */
  flex-wrap: wrap;        /* Responsive wrapping */
}

/* Each sponsor block; the tier modifier sets the logo size */
.sponsor {
  flex: 1 1 200px;
  max-width: 200px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.sponsor.gold   { flex-basis: 300px; max-width: 300px; }
.sponsor.silver { flex-basis: 260px; max-width: 260px; }
.sponsor.bronze { flex-basis: 200px; max-width: 200px; }

/* Consistent logo container */
.sponsor img {
  width: 100%;
  height: 100px;          /* Same height for all logos within a tier */
  object-fit: contain;    /* Keep aspect ratio inside box */
  background: #fff;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 6px;
  margin-bottom: 12px;
}
.sponsor.gold img   { height: 180px; border: 2px solid #d4a017; }
.sponsor.silver img { height: 140px; border: 2px solid #a8a8a8; }
.sponsor.bronze img { height: 100px; border: 2px solid #b0733a; }

/* Sponsor text */
.sponsor p {
  margin: 0;
  font-size: 14px;
  line-height: 1.3;
}
.sponsor.gold p   { font-size: 18px; font-weight: bold; }
.sponsor.silver p { font-size: 16px; font-weight: bold; }
</style>

{% comment %}
Platinum sponsor: none yet for 2026. Remove the comment tags and fill in when one signs on.
(Use a Liquid comment, not an HTML one: compress.html mishandles multi-line HTML comments.)
<h2 class="sponsor-tier-title platinum">Platinum Sponsor</h2>
<div class="sponsor-row">
  <div class="sponsor platinum">
    <a href="URL"><img src="{{ site.urlimg }}sponsor_logos/LOGO.png" alt="NAME logo"></a>
    <p><a href="URL">NAME</a></p>
  </div>
</div>
{% endcomment %}

<h2 class="sponsor-tier-title gold">Gold Sponsors</h2>
<div class="sponsor-row">
  <div class="sponsor gold">
    <a href="https://www.gjktm.com/"><img src="{{ site.urlimg }}sponsor_logos/teddymorse.png" alt="Teddy Morse's Grand Junction Powersports logo"></a>
    <p><a href="https://www.gjktm.com/">Teddy Morse KTM</a></p>
  </div>
  <div class="sponsor gold">
    <a href="https://www.motominded.com/"><img src="{{ site.urlimg }}sponsor_logos/motominded.png" alt="MotoMinded logo"></a>
    <p><a href="https://www.motominded.com/">MotoMinded</a></p>
  </div>
  <div class="sponsor gold">
    <a href="https://moleculemoto.com/"><img src="{{ site.urlimg }}sponsor_logos/molecule_motosports.png" alt="Molecule Motosports logo"></a>
    <p><a href="https://moleculemoto.com/">Molecule Motosports</a></p>
  </div>
</div>

<h2 class="sponsor-tier-title silver">Silver Sponsors</h2>
<div class="sponsor-row">
  <div class="sponsor silver">
    <a href="https://www.bajadesigns.com/"><img src="{{ site.urlimg }}sponsor_logos/baja_designs.png" alt="Baja Designs logo"></a>
    <p><a href="https://www.bajadesigns.com/">Baja Designs</a></p>
  </div>
  <div class="sponsor silver">
    <a href="https://www.motorcycleaccessoriesgj.com/"><img src="{{ site.urlimg }}sponsor_logos/motorcycle_accessories.png" alt="Motorcycle Accessories logo"></a>
    <p><a href="https://www.motorcycleaccessoriesgj.com/">Motorcycle Accessories</a></p>
  </div>
</div>

<h2 class="sponsor-tier-title bronze">Bronze Sponsors</h2>
<div class="sponsor-row">
  <div class="sponsor bronze">
    <a href="https://slavensracing.com/"><img src="{{ site.urlimg }}sponsor_logos/slavens_racing.png" alt="Slavens Racing logo"></a>
    <p><a href="https://slavensracing.com/">Slavens Racing</a></p>
  </div>
  <div class="sponsor bronze">
    <a href="https://www.klim.com/"><img src="{{ site.urlimg }}sponsor_logos/klim.png" alt="KLIM logo"></a>
    <p><a href="https://www.klim.com/">KLIM</a></p>
  </div>
  <div class="sponsor bronze">
    <a href="https://www.doubletakemirror.com/"><img src="{{ site.urlimg }}sponsor_logos/doubletake_mirror.png" alt="DoubleTake Mirrors logo"></a>
    <p><a href="https://www.doubletakemirror.com/">DoubleTake Mirrors</a></p>
  </div>
</div>
