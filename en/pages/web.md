# Web

## Inject jQuery into any site
- <a class="bookmarklet" href="javascript:(function(e,s){e.src=s;e.onload=function(){jQuery.noConflict();console.log('jQuery injected')};document.head.appendChild(e);})(document.createElement('script'),'//code.jquery.com/jquery-latest.min.js')"><b>Drag this</b></a>
- Or Copy/Paste the following into urlbar:
- `javascript:(function(e,s){e.src=s;e.onload=function(){jQuery.noConflict();console.log('jQuery injected')};document.head.appendChild(e);})(document.createElement('script'),'//code.jquery.com/jquery-latest.min.js')`


**NOTE:** If `$` isen't working, either redefine it or use `jQuery`

## Youtube don't auto pause
- <a class="bookmarklet" href="javascript:(function () { 'use strict'; setInterval(function () { var elem = document .querySelector( '.style-scope.ytd-popup-container>yt-confirm-dialog-renderer .buttons.style-scope.yt-confirm-dialog-renderer>yt-button-renderer#confirm-button' ); if (elem) { elem.click(); } }, 500); alert('YC Activated'); })();
"><b>Drag this</b></a>
- Or Copy/Paste the following into urlbar:
- `javascript:(function () { 'use strict'; setInterval(function () { var elem = document .querySelector( '.style-scope.ytd-popup-container>yt-confirm-dialog-renderer .buttons.style-scope.yt-confirm-dialog-renderer>yt-button-renderer#confirm-button' ); if (elem) { elem.click(); } }, 500); alert('YC Activated'); })();
`
