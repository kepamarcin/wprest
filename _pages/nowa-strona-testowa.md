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