---
title: "Klovnstation 14"
description: "It's the place to be!"
layout: single
---
Welcome to the website of Klovnstation 14. 

We are a Space Station 14 server with minimal rules and a focus on high quality game design. Scholarly players, powergamers and roleplayers will all find their niche here.

We do not care about your past bans as long as you aren't a creep or criminal, everyone else is welcome here.

## IMPORTANT: We are still temporarily on Wizden auth. This will be changed soon.

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

- [The launcher we recommend](https://store.steampowered.com/app/3731580/Space_Station_Beyond/)
- [Our game IP (game.klovnstation.org)](ss14://game.klovnstation.org)
- [Our minimal rules](/rules)
- XMPP tutorial for dummies (under construction)
- [About us](/aboutus)
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
</div>
<div class="right">
<img src="/images/kslogo.png" alt="KS14 logo" class="bigimage">
</div>
<br style="clear: both;">
</div>

<!--Horrible demonic solution to the most egregious bits of flicker on website load caused by the JS-->
<div id="flicker-prevention" style="display: none;">

### Our design documents

Because we have less rules, our game has to be designed very well in order for it to be fun for everyone. Our design documents are available either on the discord or [over here](/docs).

</div>