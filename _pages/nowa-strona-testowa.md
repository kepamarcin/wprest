---
ID: 410
post_title: Nowa strona testowa
author: mkepa
post_excerpt: ""
layout: page
permalink: >
  https://mkepa.thisistap.com/nowa-strona-testowa/
published: true
post_date: 2018-12-14 20:36:30
---
<!-- wp:gallery {"ids":[380,275,206,15],"columns":4} -->
<ul class="wp-block-gallery columns-4 is-cropped"><li class="blocks-gallery-item"><figure><img src="https://mkepa.thisistap.com/wp-content/uploads/2018/07/wave-poster-min-1024x576.jpg" alt="" data-id="380" data-link="https://mkepa.thisistap.com/wqpis-z-gu/wave-poster-min/" class="wp-image-380"/></figure></li><li class="blocks-gallery-item"><figure><img src="https://mkepa.thisistap.com/wp-content/uploads/2017/10/zdj..jpeg" alt="" data-id="275" data-link="https://mkepa.thisistap.com/zdj/" class="wp-image-275"/></figure></li><li class="blocks-gallery-item"><figure><img src="https://mkepa.thisistap.com/wp-content/uploads/2017/10/fo-1.jpg" alt="" data-id="206" data-link="https://mkepa.thisistap.com/fo-2/" class="wp-image-206"/></figure></li><li class="blocks-gallery-item"><figure><img src="https://mkepa.thisistap.com/wp-content/uploads/2017/02/20140819_150528_Android-814x1024.jpg" alt="" data-id="15" data-link="https://mkepa.thisistap.com/pierwszy-wpis-o-niczym/20140819_150528_android/" class="wp-image-15"/></figure></li></ul>
<!-- /wp:gallery -->

<!-- wp:code -->
<pre class="wp-block-code"><code>var e = {};
function t(e) {
  return new Promise(function(t, n) {
    var r = new XMLHttpRequest;
    r.open("GET", e, !0),
    r.withCredentials = !0,
    r.onload = function() {
      200 === r.status ? t() : n()
    }
    ,
    r.send()
  }
  )
}
var n = function(e) {
  if ("undefined" == typeof document)
    return !1;
  try {
    var t = document.createElement("link");
    if (t.relList &amp;&amp; "function" == typeof t.relList.supports)
      return t.relList.supports(e)
  } catch (e) {
    return !1
  }
}("prefetch") ? function(e) {
  return new Promise(function(t, n) {
    var r = document.createElement("link");
    r.rel = "prefetch",
    r.href = e,
    r.onload = t,
    r.onerror = n,
    (document.head || document.querySelector("script").parentNode).appendChild(r)
  }
  )
}
: t;
function r(r, i) {
  if (!e[r]) {
    if ("connection"in navigator) {
      if ((navigator.connection.effectiveType || "").includes("2g"))
        return;
      if (navigator.connection.saveData)
        return
    }
    return (i ? function(e) {
      return null == self.fetch ? t(e) : fetch(e, {
        credentials: "include"
      })
    }
    : n)(r).then(function() {
      e[r] = !0
    })
  }
}
var i = i || function(e) {
  var t = Date.now();
  return setTimeout(function() {
    e({
      didTimeout: !1,
      timeRemaining: function() {
        return Math.max(0, 50 - (Date.now() - t))
      }
    })
  }, 1)
}
  , o = new Set
  , u = new IntersectionObserver(function(e) {
  e.forEach(function(e) {
    if (e.isIntersecting) {
      var t = e.target.href;
      o.has(t) &amp;&amp; c(t)
    }
  })
}
);
function c(e) {
  o.delete(e),
  r(e, u.priority)
}
module.exports = function(e) {
  e = Object.assign({
    timeout: 2e3,
    priority: !1,
    timeoutFn: i,
    el: document
  }, e),
  u.priority = e.priority,
  e.timeoutFn(function() {
    e.urls ? e.urls.forEach(c) : Array.from(e.el.querySelectorAll("a"), function(e) {
      u.observe(e),
      o.add(e.href)
    })
  }, {
    timeout: e.timeout
  })
}
;
</code></pre>
<!-- /wp:code -->

<!-- wp:html -->
<pre class="wp-block-preformatted"><code>var e = {};<br>
function t(e) {<br>
  return new Promise(function(t, n) {<br>
    var r = new XMLHttpRequest;<br>
    r.open("GET", e, !0),<br>
    r.withCredentials = !0,<br>
    r.onload = function() {<br>
      200 === r.status ? t() : n()<br>
    }<br>
    ,<br>
    r.send()<br>
  }<br>
  )<br>
}<br>
var n = function(e) {<br>
  if ("undefined" == typeof document)<br>
    return !1;<br>
  try {<br>
    var t = document.createElement("link");<br>
    if (t.relList &amp;&amp; "function" == typeof t.relList.supports)<br>
      return t.relList.supports(e)<br>
  } catch (e) {<br>
    return !1<br>
  }<br>
}("prefetch") ? function(e) {<br>
  return new Promise(function(t, n) {<br>
    var r = document.createElement("link");<br>
    r.rel = "prefetch",<br>
    r.href = e,<br>
    r.onload = t,<br>
    r.onerror = n,<br>
    (document.head || document.querySelector("script").parentNode).appendChild(r)<br>
  }<br>
  )<br>
}<br>
: t;<br>
function r(r, i) {<br>
  if (!e[r]) {<br>
    if ("connection"in navigator) {<br>
      if ((navigator.connection.effectiveType || "").includes("2g"))<br>
        return;<br>
      if (navigator.connection.saveData)<br>
        return<br>
    }<br>
    return (i ? function(e) {<br>
      return null == self.fetch ? t(e) : fetch(e, {<br>
        credentials: "include"<br>
      })<br>
    }<br>
    : n)(r).then(function() {<br>
      e[r] = !0<br>
    })<br>
  }<br>
}<br>
var i = i || function(e) {<br>
  var t = Date.now();<br>
  return setTimeout(function() {<br>
    e({<br>
      didTimeout: !1,<br>
      timeRemaining: function() {<br>
        return Math.max(0, 50 - (Date.now() - t))<br>
      }<br>
    })<br>
  }, 1)<br>
}<br>
  , o = new Set<br>
  , u = new IntersectionObserver(function(e) {<br>
  e.forEach(function(e) {<br>
    if (e.isIntersecting) {<br>
      var t = e.target.href;<br>
      o.has(t) &amp;&amp; c(t)<br>
    }<br>
  })<br>
}<br>
);<br>
function c(e) {<br>
  o.delete(e),<br>
  r(e, u.priority)<br>
}<br>
module.exports = function(e) {<br>
  e = Object.assign({<br>
    timeout: 2e3,<br>
    priority: !1,<br>
    timeoutFn: i,<br>
    el: document<br>
  }, e),<br>
  u.priority = e.priority,<br>
  e.timeoutFn(function() {<br>
    e.urls ? e.urls.forEach(c) : Array.from(e.el.querySelectorAll("a"), function(e) {<br>
      u.observe(e),<br>
      o.add(e.href)<br>
    })<br>
  }, {<br>
    timeout: e.timeout<br>
  })<br>
}<br>
;</code></pre>
<!-- /wp:html -->