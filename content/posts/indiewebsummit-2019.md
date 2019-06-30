---
type: post
title: "IndieWeb Summit 2019 - Day 1 Review"
description: "To grow more familiar with the IndieWebCamp community and its principles, I'm sharing its code of conduct, here."
summary: "Be respectful of other people, respectfully ask people to stop if you are bothered, and if you can't resolve an issue, contact staff. If you are being a problem, it will be apparent and you'll be asked to leave."
categories: ["IndieWeb Summit"]
tags: ["code-of-conduct", "wiki", "principles"]
date: "2019-06-26T01:13:33-23:00"
draft: false
slug: /indieweb-summit/2019/day-one/

images: https://web-work.tools/indieweb/images/IndieWeb-Summit-2019-Day-1.png
---


<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
<video id="video"></video>
<script>
  if(Hls.isSupported()) {
    var video = document.getElementById('video');
    var hls = new Hls();
    hls.loadSource('http://cdncities.com/deranalive/deranalive/playlist.m3u8');
    hls.attachMedia(video);
    hls.on(Hls.Events.MANIFEST_PARSED,function() {
      video.play();
  });
 }
 // hls.js is not supported on platforms that do not have Media Source Extensions (MSE) enabled.
 // When the browser has built-in HLS support (check using `canPlayType`), we can provide an HLS manifest (i.e. .m3u8 URL) directly to the video element throught the `src` property.
 // This is using the built-in support of the plain video element, without using hls.js.
  else if (video.canPlayType('application/vnd.apple.mpegurl')) {
    video.src = 'https://web-work.tools/indieweb/indieweb-livestream.m3u8';
    video.addEventListener('canplay',function() {
      video.play();
    });
  }
