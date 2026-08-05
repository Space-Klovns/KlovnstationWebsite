---
title: "Klovnstation 14"
description: "It's the place to be!"
layout: single
---
Welcome to the website of Klovnstation 14. 

We are a Space Station 14 server with minimal rules and a focus on high quality game design. Scholarly players, powergamers and roleplayers will all find their niche here.

We do not care about your past bans as long as you aren't a creep or criminal, everyone else is welcome here.


<script>
// demonic shit
document.addEventListener('DOMContentLoaded', function() {
  function updateLayout() {
    const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) || window.innerWidth <= 768;
    
    if (isMobile) {
      document.getElementById('mobile-layout').style.display = 'block';
      document.getElementById('desktop-layout').style.display = 'none';
      document.getElementById('flicker-prevention').style.display = 'block';
    } else {
      document.getElementById('mobile-layout').style.display = 'none';
      document.getElementById('desktop-layout').style.display = 'block';
      document.getElementById('flicker-prevention').style.display = 'block';
    }
  }
  
  // Run on load
  updateLayout();
  
  // Re-run on resize (desktop ↔ tablet)
  window.addEventListener('resize', updateLayout);
});
</script>

<!-- MOBILE LAYOUT -->
<div id="mobile-layout" style="display: none;">
{{% hotlinkicon "https://discord.gg/adkEEQQyRj" "/icons/discord.svg" "Discord" %}}
{{% hotlinkicon "https://github.com/Space-Klovns/Klovnstation14" "/icons/github.svg" "Github" %}}
{{% hotlinkicon "/xmpp" "/icons/xmpp.svg" "XMPP" %}}
{{% hotlinkicon "https://klovnstation14.miraheze.org/wiki/Main_Page" "/icons/wiki.svg" "Wiki" %}}
{{% hotlinkicon "https://www.youtube.com/@Klovnstation14" "/icons/youtube.svg" "YouTube" %}}

- [The launcher we recommend](https://github.com/LaCumbiaDelCoronavirus/SanabiLauncher)
- [Our game IP (game.klovnstation.org)](ss14://game.klovnstation.org)
- [Our minimal rules](/rules)
- XMPP tutorial for dummies (under construction)
- [About us](/aboutus)
- [Lore](/lore)
</div>

<!-- DESKTOP LAYOUT -->
<div id="desktop-layout" style="display: none;">
<div class="left">
{{% hotlinkicon "https://discord.gg/adkEEQQyRj" "/icons/discord.svg" "Discord" %}}
{{% hotlinkicon "https://github.com/Space-Klovns/Klovnstation14" "/icons/github.svg" "Github" %}}
{{% hotlinkicon "/xmpp" "/icons/xmpp.svg" "XMPP" %}}
{{% hotlinkicon "https://klovnstation14.miraheze.org/wiki/Main_Page" "/icons/wiki.svg" "Wiki" %}}
{{% hotlinkicon "https://www.youtube.com/@Klovnstation14" "/icons/youtube.svg" "YouTube" %}}

- [The launcher we recommend](https://store.steampowered.com/app/3731580/Space_Station_Beyond/)
- [Our game IP (game.klovnstation.org)](ss14://game.klovnstation.org)
- [Our minimal rules](/rules)
- XMPP tutorial for dummies (under construction)
- [About us](/aboutus)
- [Lore](/lore)
</div>
<div class="right">
<img src="/images/kslogo.png" alt="KS14 logo" class="bigimage">
</div>
<br style="clear: both;">
</div>

<!--Horrible demonic solution to the most egregious bits of flicker on website load caused by the JS-->
<div id="flicker-prevention" style="display: none;">

### Upcoming pophosts

<div id="discord-events">Loading events…</div>

<script>
  const EVENTS_URL = 'https://game.klovnstation.org/events';
  const GUILD_ID = '1431244580451516428';

  function formatDate(value) {
    if (!value || value === 'None') return '—';

    const date = new Date(value);
    if (Number.isNaN(date.getTime())) return value;

    return date.toLocaleString(undefined, {
      weekday: 'short',
      year: 'numeric',
      month: 'short',
      day: 'numeric',
      hour: '2-digit',
      minute: '2-digit',
    });
  }

  async function loadEvents() {
    const container = document.getElementById('discord-events');

    try {
      const url = `${EVENTS_URL}?guild_id=${encodeURIComponent(GUILD_ID)}`;
      const res = await fetch(url);

      if (!res.ok) {
        container.textContent = 'Failed to load events.';
        return;
      }

      const data = await res.json();
      const events = data.events || [];

      if (!events.length) {
        container.textContent = 'No upcoming events.';
        return;
      }

      const table = document.createElement('table');
      table.style.width = '100%';
      table.style.borderCollapse = 'collapse';

      const thead = document.createElement('thead');
      thead.innerHTML = `
        <tr>
          <th style="text-align:left; padding:8px; border-bottom:1px solid #ccc;">Name</th>
          <th style="text-align:left; padding:8px; border-bottom:1px solid #ccc;">Start</th>
          <th style="text-align:left; padding:8px; border-bottom:1px solid #ccc;">End</th>
          <th style="text-align:left; padding:8px; border-bottom:1px solid #ccc;">Location</th>
        </tr>
      `;

      const tbody = document.createElement('tbody');

      for (const event of events) {
        const tr = document.createElement('tr');

        const [name, startTime, endTime, location] = event;

        tr.innerHTML = `
          <td style="padding:8px; border-bottom:1px solid #eee;">${name ?? '—'}</td>
          <td style="padding:8px; border-bottom:1px solid #eee;">${formatDate(startTime)}</td>
          <td style="padding:8px; border-bottom:1px solid #eee;">${formatDate(endTime)}</td>
          <td style="padding:8px; border-bottom:1px solid #eee;">${location && location !== 'None' ? location : '—'}</td>
        `;

        tbody.appendChild(tr);
      }

      table.appendChild(thead);
      table.appendChild(tbody);

      container.innerHTML = '';
      container.appendChild(table);
    } catch (err) {
      console.log(err);
      container.textContent = 'Error loading events.';
    }
  }

  loadEvents();
</script>


### Our design documents

Because we have less rules, our game has to be designed very well in order for it to be fun for everyone. Our design documents are available either on the discord or [over here](/docs).

</div>