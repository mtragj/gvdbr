---
layout: page-fullwidth
title: "2026 Activities"
subheadline:
teaser: "Weekend activity schedule for the 2026 Rally - including our Saturday night door prize drawing for a GASGAS e-bike! Check back for updates!"
header:
  image_fullwidth: singletrack_plains_header.png
permalink: "/activities/"
---
<!--more-->

<div style="margin: 18px 0; padding: 12px 14px; background: #f3f4f6; border-radius: 6px;">
  <p style="margin: 0 0 6px; font-weight: 700;">Event Location</p>
  <p style="margin: 0;"><a href="https://maps.app.goo.gl/DyTFPyFCcu5sCqNt6" target="_blank" rel="noopener noreferrer">Open event map in Google Maps</a></p>
</div>

<style>
/* Page container spacing */
.activity-section {
  max-width: 1100px;
  margin: 0 auto 40px;
  padding: 0 20px;
}

/* Day title */
.activity-section h2 {
  margin: 28px 0 12px;
  font-size: 22px;
  text-align: center;
}

/* Table styling */
.schedule-table {
  width: 100%;
  border-collapse: collapse;
  margin: 0 auto 24px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.06);
  background: #fff;
  border-radius: 6px;
  overflow: hidden;
}

.schedule-table thead {
  background: #f6f6f6;
  text-align: left;
}

.schedule-table th,
.schedule-table td {
  padding: 12px 14px;
  border-bottom: 1px solid #eee;
  font-size: 15px;
}

.schedule-table tr:last-child td {
  border-bottom: none;
}

/* Time column narrower */
.schedule-table th.time,
.schedule-table td.time {
  width: 160px;
  white-space: nowrap;
  font-weight: 600;
  color: #333;
}

/* Responsive: stack rows on small screens */
@media (max-width: 640px) {
  .schedule-table, .schedule-table thead, .schedule-table tbody, .schedule-table th, .schedule-table td, .schedule-table tr {
    display: block;
  }
  .schedule-table thead {
    display: none;
  }
  .schedule-table tr {
    margin-bottom: 12px;
    border-bottom: 1px solid #eee;
    padding-bottom: 8px;
  }
  .schedule-table td {
    padding: 8px 10px;
  }
  .schedule-table td.time {
    font-weight: 700;
    display: block;
    margin-bottom: 6px;
  }
}
</style>

<div class="activity-section">
  <h2>Friday</h2>
  <table class="schedule-table" aria-describedby="friday-schedule">
    <thead>
      <tr>
        <th class="time">Time</th>
        <th>Event</th>
      </tr>
    </thead>
    <tbody id="friday-schedule">
      <tr>
        <td class="time">12PM - 3PM</td>
        <td>Event/Vendor Setup</td>
      </tr>      
      <tr>
        <td class="time">3PM - 8PM</td>
        <td><strong>Registration</strong></td>
      </tr>
      <tr>
        <td class="time">3PM - 6PM</td>
        <td>Vendor Expo</td>
      </tr>      
      <tr>
        <td class="time">3PM - 7PM</td>
        <td>Food Truck - TBD</td>
      </tr>
      <tr>
        <td class="time">4PM - 6PM</td>
        <td><a href="{{ site.url }}{{ site.baseurl }}/rides/gj_desert/easy/skills-training-trail-skills-enhancer/">Trail Skills Enhancer</a> - beginner/novice skills training at the 27-1/4 Road MX Track</td>
      </tr>
      <tr>
        <td class="time">4PM - 8PM</td>
        <td>Yard Games</td>
      </tr>
      <tr>
        <td class="time">6PM - 8PM</td>
        <td>Campfire/Smores(provided)</td>
      </tr>     
      <tr>
        <td class="time">6PM - 8PM</td>
        <td>Music or a Movie</td>
      </tr>
    </tbody>
  </table>

  <h2>Saturday</h2>
  <table class="schedule-table" aria-describedby="saturday-schedule">
    <thead>
      <tr>
        <th class="time">Time</th>
        <th>Event</th>
      </tr>
    </thead>
    <tbody id="saturday-schedule">
      <tr>
        <td class="time">7AM - 11AM</td>
        <td><strong>Registration</strong></td>
      </tr>
      <tr>
        <td class="time">4PM - 8PM</td>
        <td>Bravos Food Truck</td>
      </tr>
      <tr>
        <td class="time">4PM - 8PM</td>
        <td>Vendor Expo</td>
      </tr>            
      <tr>
        <td class="time">5PM</td>
        <td>Slow Ride Contest</td>
      </tr>
      <tr style="background: #fdf1f1;">
        <td class="time">6PM</td>
        <td><strong><a href="#door-prizes">Door Prize Drawing</a></strong> - win a GASGAS e-bike! Must be present to win</td>
      </tr>
      <tr>
        <td class="time">6PM - 8PM</td>
        <td>Music or a Movie</td>
      </tr>
    </tbody>
  </table>

  <h2>Sunday</h2>
  <table class="schedule-table" aria-describedby="sunday-schedule">
    <thead>
      <tr>
        <th class="time">Time</th>
        <th>Event</th>
      </tr>
    </thead>
    <tbody id="sunday-schedule">
      <tr>
        <td class="time">7AM-10AM</td>
        <td><strong>Registration</strong></td>
      </tr>
      <tr>
        <td class="time">12PM - 5PM</td>
        <td>Teardown/Depart</td>
      </tr>
    </tbody>
  </table>

  {% assign register_url = site.url | append: site.baseurl | append: "/register/" %}
  {% include door_prizes cta_url=register_url %}
</div>