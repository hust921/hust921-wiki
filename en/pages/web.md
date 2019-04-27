# Web

## Inject jQuery into any site
- Copy/Paste the following into urlbar:
- `javascript:(function(e,s){e.src=s;e.onload=function(){jQuery.noConflict();console.log('jQuery injected')};document.head.appendChild(e);})(document.createElement('script'),'//code.jquery.com/jquery-latest.min.js')`

Or create bookmark and press when site is loaded.
**NOTE:** If `$` isen't working, either redefine it or use `jQuery`
