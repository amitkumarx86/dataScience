# dataScience
This repo has content about machine learning

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<title>kmeans_and_meanShift</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>

<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    color: #000 !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.2.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.2.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.2.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.2.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.2.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.2.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=1);
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2);
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=3);
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1);
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1);
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
@media (max-width: 991px) {
  #ipython_notebook {
    margin-left: 10px;
  }
}
[dir="rtl"] #ipython_notebook {
  float: right !important;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#login_widget {
  float: right;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  text-align: center;
  vertical-align: middle;
  display: inline;
  opacity: 0;
  z-index: 2;
  width: 12ex;
  margin-right: -12ex;
}
.alternate_upload .btn-upload {
  height: 22px;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
[dir="rtl"] #tabs li {
  float: right;
}
ul#tabs {
  margin-bottom: 4px;
}
[dir="rtl"] ul#tabs {
  margin-right: 0px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons {
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-right {
  padding-top: 1px;
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-left {
  float: right !important;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: baseline;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
#tree-selector {
  padding-right: 0px;
}
[dir="rtl"] #tree-selector a {
  float: right;
}
#button-select-all {
  min-width: 50px;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
[dir="rtl"] #new-menu {
  text-align: right;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
[dir="rtl"] #running .col-sm-8 {
  float: right !important;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI colors. */
.ansibold {
  font-weight: bold;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  border-left-width: 1px;
  padding-left: 5px;
  background: linear-gradient(to right, transparent -40px, transparent 1px, transparent 1px, transparent 100%);
}
div.cell.jupyter-soft-selected {
  border-left-color: #90CAF9;
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected {
  border-color: #ababab;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 5px, transparent 5px, transparent 100%);
}
@media print {
  div.cell.selected {
    border-color: transparent;
  }
}
div.cell.selected.jupyter-soft-selected {
  border-left-width: 0;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 7px, #E3F2FD 7px, #E3F2FD 100%);
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #66BB6A -40px, #66BB6A 5px, transparent 5px, transparent 100%);
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  padding: 0.4em;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. We need the 0 value because of how we size */
  /* .CodeMirror-lines */
  padding: 0;
  border: 0;
  border-radius: 0;
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul {
  list-style: disc;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ul ul {
  list-style: square;
  margin: 0em 2em;
}
.rendered_html ul ul ul {
  list-style: circle;
  margin: 0em 2em;
}
.rendered_html ol {
  list-style: decimal;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
  margin: 0em 2em;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  background-color: #fff;
  color: #000;
  font-size: 100%;
  padding: 0px;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: 1px solid black;
  border-collapse: collapse;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  border: 1px solid black;
  border-collapse: collapse;
  margin: 1em 2em;
}
.rendered_html td,
.rendered_html th {
  text-align: left;
  vertical-align: middle;
  padding: 4px;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget {
  float: right !important;
  float: right;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  margin-top: 6px;
}
span.save_widget span.filename {
  height: 1em;
  line-height: 1em;
  padding: 3px;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  display: none;
}
.command-shortcut:before {
  content: "(command)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}

@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1>Question 1</h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[41]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">from</span> <span class="nn">sklearn.cluster</span> <span class="k">import</span> <span class="n">MeanShift</span><span class="p">,</span> <span class="n">estimate_bandwidth</span><span class="p">,</span><span class="n">KMeans</span>
<span class="kn">import</span> <span class="nn">os</span>
<span class="kn">from</span> <span class="nn">skimage</span> <span class="k">import</span> <span class="n">io</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>

<span class="k">def</span> <span class="nf">imagePreprocessing</span><span class="p">(</span><span class="n">img</span><span class="p">):</span>
    
    
    <span class="n">image</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">img</span><span class="p">)</span>
    <span class="c1"># reshape</span>
    <span class="n">flat_image</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">image</span><span class="p">,</span> <span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span><span class="mi">3</span><span class="p">])</span>
    <span class="k">return</span> <span class="n">flat_image</span>

<span class="k">def</span> <span class="nf">meanShift</span><span class="p">(</span><span class="n">flat_image</span><span class="p">):</span>
    <span class="c1"># Estimate Bandwidth</span>
    <span class="n">bandwidth</span> <span class="o">=</span> <span class="n">estimate_bandwidth</span><span class="p">(</span><span class="n">flat_image</span><span class="p">,</span> <span class="n">quantile</span> <span class="o">=</span> <span class="mf">0.2</span><span class="p">,</span> <span class="n">n_samples</span><span class="o">=</span><span class="mi">500</span><span class="p">)</span>
    <span class="n">ms</span> <span class="o">=</span> <span class="n">MeanShift</span><span class="p">(</span><span class="n">bandwidth</span><span class="p">,</span> <span class="n">bin_seeding</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
    <span class="n">ms</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">flat_image</span><span class="p">)</span>
    <span class="n">labels</span> <span class="o">=</span> <span class="n">ms</span><span class="o">.</span><span class="n">labels_</span>
    <span class="k">return</span> <span class="n">ms</span><span class="o">.</span><span class="n">labels_</span><span class="p">,</span> <span class="n">ms</span><span class="o">.</span><span class="n">cluster_centers_</span>


    
<span class="k">def</span> <span class="nf">kmeans</span><span class="p">(</span><span class="n">flat_image</span><span class="p">,</span> <span class="n">n_clusters</span><span class="o">=</span><span class="mi">3</span><span class="p">):</span>
    <span class="n">km</span> <span class="o">=</span> <span class="n">KMeans</span><span class="p">(</span><span class="n">n_clusters</span><span class="p">)</span>
    <span class="n">km</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">flat_image</span><span class="p">)</span>
<span class="c1">#     print (km.labels_)</span>
    <span class="k">return</span> <span class="n">km</span><span class="o">.</span><span class="n">labels_</span><span class="p">,</span> <span class="n">km</span><span class="o">.</span><span class="n">cluster_centers_</span>

<span class="k">def</span> <span class="nf">postProcessImage</span><span class="p">(</span><span class="n">labels</span><span class="p">,</span> <span class="n">kmcenters</span><span class="p">,</span><span class="n">w</span><span class="p">,</span> <span class="n">h</span><span class="p">):</span>
    <span class="n">shape</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="n">shape</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">w</span><span class="p">)</span>
    <span class="n">shape</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">h</span><span class="p">)</span>
    
    <span class="k">return</span> <span class="n">np</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">labels</span><span class="p">,</span><span class="n">shape</span><span class="p">)</span>

<span class="k">def</span> <span class="nf">plotImage</span><span class="p">(</span><span class="n">imgList</span><span class="p">):</span>
    <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">imgList</span><span class="p">)):</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="nb">len</span><span class="p">(</span><span class="n">imgList</span><span class="p">),</span><span class="n">i</span><span class="o">+</span><span class="mi">1</span><span class="p">),</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">imgList</span><span class="p">[</span><span class="n">i</span><span class="p">])</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">axis</span><span class="p">(</span><span class="s1">&#39;off&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
    
<span class="k">def</span> <span class="nf">callMainFunction</span><span class="p">(</span><span class="n">imgNamedict</span><span class="p">):</span>
    <span class="k">for</span> <span class="n">file</span><span class="p">,</span> <span class="n">g_truth</span> <span class="ow">in</span> <span class="n">imgNamedict</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
        <span class="n">img</span> <span class="o">=</span> <span class="n">io</span><span class="o">.</span><span class="n">imread</span><span class="p">(</span><span class="n">file</span><span class="p">)</span>
        <span class="n">w</span><span class="p">,</span> <span class="n">h</span><span class="p">,</span> <span class="n">r</span> <span class="o">=</span> <span class="n">img</span><span class="o">.</span><span class="n">shape</span>    
        <span class="c1"># print (shape)</span>
        <span class="n">preProcessImage</span> <span class="o">=</span> <span class="n">imagePreprocessing</span><span class="p">(</span><span class="n">img</span><span class="p">)</span>    

        <span class="c1"># kmean </span>
        <span class="n">kmlabels</span><span class="p">,</span> <span class="n">kmcenters</span> <span class="o">=</span> <span class="n">kmeans</span><span class="p">(</span><span class="n">preProcessImage</span><span class="p">,</span><span class="mi">5</span><span class="p">)</span>
        <span class="n">kmShiftedImage</span> <span class="o">=</span> <span class="n">postProcessImage</span><span class="p">(</span><span class="n">kmlabels</span><span class="p">,</span> <span class="n">kmcenters</span><span class="p">,</span><span class="n">w</span><span class="p">,</span> <span class="n">h</span><span class="p">)</span>

        <span class="c1"># mean shift</span>
        <span class="n">mslabels</span><span class="p">,</span> <span class="n">mscenters</span> <span class="o">=</span> <span class="n">meanShift</span><span class="p">(</span><span class="n">preProcessImage</span><span class="p">)</span>
        <span class="n">meansShiftedImage</span> <span class="o">=</span> <span class="n">postProcessImage</span><span class="p">(</span><span class="n">mslabels</span><span class="p">,</span> <span class="n">mscenters</span><span class="p">,</span><span class="n">w</span><span class="p">,</span> <span class="n">h</span><span class="p">)</span>

        <span class="n">imagelist</span> <span class="o">=</span> <span class="p">[]</span>
        <span class="n">imagelist</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">img</span><span class="p">)</span>
        <span class="n">imagelist</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">kmShiftedImage</span><span class="p">)</span>
        <span class="n">imagelist</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">meansShiftedImage</span><span class="p">)</span>
        <span class="n">imagelist</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">io</span><span class="o">.</span><span class="n">imread</span><span class="p">(</span><span class="n">g_truth</span><span class="p">))</span>
        
        <span class="c1"># call plot image function, input is list of images</span>
        <span class="n">plotImage</span><span class="p">(</span><span class="n">imagelist</span><span class="p">)</span>

<span class="k">if</span> <span class="vm">__name__</span><span class="o">==</span><span class="s2">&quot;__main__&quot;</span><span class="p">:</span>
    
    <span class="n">imgNamedict</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">()</span>
    
    <span class="n">imgNamedict</span><span class="p">[</span><span class="s1">&#39;a.jpg&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="s1">&#39;a_truth.jpg&#39;</span>
    <span class="n">imgNamedict</span><span class="p">[</span><span class="s1">&#39;b.jpg&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="s1">&#39;b_truth.jpg&#39;</span>
    <span class="n">imgNamedict</span><span class="p">[</span><span class="s1">&#39;c.jpg&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="s1">&#39;c_truth.jpg&#39;</span>
    <span class="n">imgNamedict</span><span class="p">[</span><span class="s1">&#39;d.jpg&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="s1">&#39;d_truth.jpg&#39;</span>
    <span class="n">imgNamedict</span><span class="p">[</span><span class="s1">&#39;e.jpg&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="s1">&#39;e_truth.jpg&#39;</span>
    
    <span class="n">callMainFunction</span><span class="p">(</span><span class="n">imgNamedict</span><span class="p">)</span>
    
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAXQAAABRCAYAAADCdV1iAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAIABJREFUeJzsvXeUJVd57v3boapO6Dg905OkUY5ICISuQEIgEUW0Lggw
yeEa+9omI7AJRkgiGANGIoMB449gBFjGRiijHJFQRGk0SjOjSZ3DSRV2uH/UqdOnJ0ijYeQRfP2s
1atPV1ftqrOr9rPf/byhhPeeBSxgAQtYwO8/5J6+gAUsYAELWMDuwQKhL2ABC1jAHwgWCH0BC1jA
Av5AsEDoC1jAAhbwB4IFQl/AAhawgD8QLBD6AhawgAX8gWCB0BewgAUs4A8EC4S+gAUsYAF/IFgg
9AUsYAEL+APBAqEvYAELWMAfCPSeOvGv797op6ZbGCex3mBcis88QgiklEgpEUKghABAKYVSCq01
QRAAIKUkiiKEEHjvsdZSlDIQQqCUwjlHmqYIIRBAtVKddw4tPFGo5h1nvcn3FwIpBc55UuNI0gzv
BGlqscaighClBEp6SqEiChVSZQSBRgiJ9+CcA+EQQiKEwhqHFBIdgHHQaBmECBkbnyFOEowxtFoN
MpNiTMqbTj5a7Er/vkcM+Us5mQc5eKePOYg1vJVzd+V0vzc4izM6n70/c5f6VogzF+pl7AR2pX+/
NXWhX3b3UQhiWk4jswRUC+88UkkEIIREKQ0IPJ4oDAnCkDAIyIwh0AFRKUIKibUW69q84AEBWiqs
tRhjkELgkVTLfUgp8/9rjRKeUpCP4Zw5PMI5lKR9DHjviZ2gkaR4DyZzGGNRKkBrgZCOckUThgqF
JdAaIQXW+rxNGbc7SuK9R6oAoTzWQqORIFDMTNeJWw2IBbVsFtkIuPOA6/jYQe/Ybt/uMUJPkhTv
Pc45nHdYa1FCdci2IORSGFKtVvPOZo6orbU458iyjCAIOn8Xv6WU9PZWcQ7K5TJCCIIgwKQZkE8Q
YahQ0iM9SJUTt3MeJYL83gsAQRQJVODRQUC91iIKQ4y0IBXWZgRaE0URlbLA+nwSwEu8E3jnSVyG
x+O9QQqNFBLjBMZ5xkZnCKIKCE0QuM61WSc7E9euYmfI/CSu4kSu/Z3Os4AF7C60knG0aKJMjHUh
kOKzACUlymmQHi00UViiXCkhhcrHqRAoobDK4q3HNS1CS5RTeOdx1uKcRwjoH+zHe4uUEuccWusO
DwVaobVEAdp7lBRY67DOI6TACfAIhBSEAUgDkYqYnY0JlcahcE7jU0upHFCRikh7pHA4F+MziUbh
rMdahfcCZ9tcowQogbOC2ZGYKKwisxIyUhhnSX2CCCRpuGNe2GOEnmUpSZLRSgxI8CKfRcMw7JB2
GIbbdLoxhjRNcc51rOqCxL33HcsaoNFo5V9Sa7TW+YzcZf0b47F4lPQIJzrHg8Q73/4bTObRUX5j
q9UKrWaGlB6kxDnRJl5Pq2URspg4Hc55gkBTCkNarRThIYoU3oO1YCxE5SpxllGpVLGZpF6vo5TC
p74zie0KLuA1T7jPi7iSF3LdLp/j9w1n8QlWsoGN7LWnL2UBO0BTamqxRyeOREg8AVq2CHWIl54g
CJCBxMiEDEEYRFjn8N7RTA3e5+NOCoGWGmvbPCE8QkuEgNl4CiklSikCHeDIENqhlMSS4YRECIfE
IxFY6RESvJJkzPGOtJJIaaw3RH2COG5CIMAIrDWIUoRV0MgckgpSKIz14AVBAKrkaTZjhJKUShEA
SWYw1qKqkmbSpNJbRbUy6q0WFWVx3lDS2Q77b48RujEGY3JpwzoLcm4VW3RYmqY4KUnTFKVU5//d
RFdY44W1X1jiWuvOMcYYrLUEOkCrOXklb8eTmXxCgJz8oyAnfOfA2pzY49SAdCgZgMhXCghBFIVo
rbHW4F2GCsp4AOGQSpB5i0od1TDAWo+JDc46fBDghScsaYSWIPMJra+vj/HxUbz3GGN3uX/Xst8T
7nMVL+YqXkwvs/O2n8Y5AJzNBwA4gnu4hyMAOJZbOIEbdvm69iTO4JPzJJcFPP2QmhrWNgldCk4i
A4F0CukUColwkqxlUMrTTBskMgaRj2WBwPp8pW+cwaYmt9bJZc4gCFBKEoVBzjuZJUtTlNZoFeGE
QCAQUuIEZDisdQgJgQ4oOUFoyQ0yl/NN6i1ehCilkWkACJSQBMoTOAUxeAdee6zwKOWR0uGtJ7OG
alTCWE/aTPMVhBYoB5WoQigc0ksyFVHpDZiYreHwxGLHit8eI/TJWkyWZR1rWiKROte8AJIk2Yp4
6dK15/72Pidc1f5f9z7W2k77AMaafFkVBG3rO9fIvJA4cg0+synGOkKpc13eWQQCKSTO5la69B7w
OOHxUtJIMqy1SKlQJu2cOwzDXMJRuaXQ0fVRkOXfK5AhQhrwYDBEUcjw8FImJycxxvyP3IsaffP+
3pr0buL4zucreOnvLaEDnMFZXMwruIXn7ulLWcB2EDcbZNbhjcaGk4T0IZTG+tzgyRLTGfPFSruw
tuf8YGYbXgAH5H4s4wHrgVwzx4O3hiAIcN5BIftaEN7jMkeSWaxUBO3zFIqAV21j0hpQHucsXubn
bKS2Y2SqbI63CkNTSEUS+/a2IOeiVCAEKDxe5lzohEP2wF5qL0brW6iqyg77b49a6GmaonV+CbkE
khNYkiQdIi5uVLecUnRMYZ0XzlOtcxIu2kySpPP/7mOL47p/5xZx/iDYzNDqakdrTRiEmPYkU0w6
UgiMyTp/CyEIVH5tUkriOEYIQZK4eQ9gLgEpnPNkWYYxpuPwzScGyeDgYOf8TzesZ29W8dievoxd
xiu5hFdyCXDmnr6UBWyFNE3JsgzpVE6OwpO5rL1idvN4oRiv3dtg+7xQcIb3fh6/QD5WtQrmSbvd
xmIh8WqlSBAdTlIqJ/hCbSgUB6HVPBlYKUVmc0NSCEGapu3Jw86bnIIgQLaNTGMsWZZ1eMG4DK01
gwMDLBpctMP+24NO0YQsyzqdl/+284ivIPluQge2memCIJdSik4BOpEtRYd0W+2F5V7cwOIGCSHy
h6m9nzT554pWNOPWvEgaay1ZnHupnXM4l98w256dwzDEWksURZ1rLa4nf0gy0jTtWBVxHGPask/3
999VlBd5WpO7fvzj4d/4C17C5b/XlvoCnp7IsiwnXBvgpUGQ4t3cSr0YF8U4LMZtwRvFfoXfrCDz
gkyNMR3C7zaYCsOqm1sKKbf7uMLgUkoRyQi7FQdYazHJ3GdoG4QqN9ZKpRLGmHkTRxHB55zD2JzI
i/MmSULmDF44Ah/iQt/lp9sWe4zQux2axW+h2pdjmZt1ff67WyvvvlEFuZbb4YuFBVzckOJcRXtF
BxYPQZblFrZSqtORmckdEwBhGJJ15BPXuVZjDFlm5lnsaZoSBZpSqUSWzUXTFJNMq9XqPDTOOeI4
7kww1lqSLOtY6UIISqUSUN2l/i0PQWtylw59QpzBWbt03KW8nJO5jHN5M2s4hI/xGQJ2LCttLf28
kos4lt886fMW5zuYB1jDIQwwxfv4ypNuZwFPPbz3eOew1mDSDO/TeYbN1kadc65j2BXc0M0LMozQ
Ws0b9937SynzcEboSLHWWpIk6RDtPF5oh0BGUURqDVEQQvuYgheMdx2CL85hdUC5XCaO405gRhCW
8N7TbDY727zLjd2ivTRNMd6igtxJmuqEeqMO/dvvvz0uuRQQQoBua2CAaM+CeTBJ4dCYC2vsXqp0
36Ci7e6IlmK/7oegexlWEDXQ2T+Korwz2zJQx7EaBJ1oG2vnblxh8TuTdUIpS6VS57yNRqOzaigs
jSzLaDQanevN2kRetFVMFLuKl51jeM7fOJoT8OivJL/8P7vndhfO0sJ5urM4getxCF7NhQg8/8g/
8CG+QJUmP+JtvJ1/B+ACXs1tHLPN8RfzKq7nBN7LV9A8cd9sPSGs4RAAphnkLM5YEFyehjDGkGYZ
GIcTBnzWjgPPUYz3bku5sL4LIw3m8laEoKN5d4/lebzQljm681OKY7rP64FSqdSRhYQQOJM7VqMo
6hyTmazDT5Dzi0nyY7TWHV4QAuI4IY7jDh8J8iCQebzgDEKBsopUxcSt+OlH6NY7MmvmWc7S5B3s
fB5GKLwiARQKbz0BAWEQEHjQQYAUAqUVSquOzmay/KZJKRFuzmGSmQy8R4n8hmVZ4TAtfuYelmr7
YeitVkmShCRJcNAh2bkY+HSe9u/zTCKq1SpBkM/IhQ5WtJ+fOyO1KYlJaKWtjkbXcbS0wzebrfrv
1MfPfX/+QPathKP+3HHUn6d8aXnA+zdnfL4vIK3tmiRTOFF3FDHyQf6ZHhrbbK/SzK+HGm/mp13t
9fAwBwJwB8/aLpkXyAh2iswv5eVPuM8CnoZwGuMb4COMFUgSAmSHrIUXKPLVd8ELTuZypxaSIMgp
LQjzMWy8QfrcCs9cNk+WmeMFUKItsRg/TyP3OJTOz1/VJZRS9FTKpGmay6SAxWF8zgnGGZyznfEM
bYPROXSgCKMy5UqJNEvQXnek2kJGymxK5gypzYiTOG9TxBjjCG2EqDiazeYOu2+PSi7ds5iUcs6p
0GWlbh21kliH0AFCSYTWGGvzOFQ5Z7kX7RXSRqcdwHk3b9nm/dzNLXS1YvYHOjPvTK1GpVLpXHtB
4t16fCH9rFixYt6MDcz7TsaYPOLGOcIw7Eg/xfUX1xKG4W7v9/dvzqWgv5/Nf39a7P5zfJEPPSlZ
5pe8tvP5fE553H0/zOd3qs1fc9xOn38BTx8UnOCcy8OZkWRd47EY08VqvVjpWmuJdNAZy8V47OaT
4vhicpjjBdHhha35o2iv+F/32LTW0mg2iUqledJp98q68AGWwpCVK1dSqUQY4+fxUuHgzbKMJMs6
lnwQBDkvCIkEQh1iZUr0OLywx8Mois4uOqq7U2HOKu6EKCmFxZNaQ+bmtm/9U5BkAa3zDE3VtqjD
MGzLJ3POlI7u1hX7XpB8X19fx0NeaO7FDSmWS8UyLEmSjtOjuIbCiVPsUywJq9UqaZp29HVjTGcy
2J1RLteeJXnwQsnm30heeOacbv3CMw3XnrlnH4Oi3MBlvGy3tVlMKC1K/JzX8xAH7ba2F/DUoRNB
1iZSLTSBngtTLlDwQndJkMLQKqLGtibxbsOw23jSSueW/1byTfc1FWO21Wp19gvDENrtFMRdoOCF
KIrapCw60TUFVxRtF0ZekUNTJFXGcUwcxyROkhpDRVfIuqTj7WHPSS5FLYWuGXVr52XxeWs9CyGh
6ORiE/M1MJiLgik6ulSKEF0WeXGe7vaLm1d0ekHoUghsJ85V0Gw2qVZzh2UnREopfPt71Wq1znfs
DmEqIm5c23FSeNchd8oUZQy6t+8OvPAMxwvPcKw5f+5B/dkpAW/6xY6zznYVb97JejAZep5T9Hhu
nBfzvjX+F7ewgZXsxcZt/vcgB3IQD83bVjhDF/D7g8LwcW5uBW/9XFhwt8FWEHNBiIGc09a7c1AK
i37rFXCxXQcaLfQ8H12xmu6sFtqTR3GNWZYRRVHnXEAnxLGoL1XsX/BC4UNL07TDDd2hjVJKTPu6
Cw294+jVGpd6jDfE7cia7WGPEXq3Ztzd+d2E3B1f2u0INd4gTDuaxTtwHt2+GUU0zPaWZmmaouV8
IhdCYtvyR4Hu5VghBUmloGs10d/fv035AQDdnsWLm7u9mVsIgROu48XurkFT9E130tWu4J1rtk/U
B//R3LV83OdO6Q83Uz5X2X3Sy4W8moc5gFdxMZA7URMiIpKO/t7LLDX6OITVHT29hwanch4xJW7i
OCYZmtfunTxrXptbJ0Qt4Pcf3rWjxkxGRor1Hun8Dnmhm0McpmOAbb1i75Y3umWUraWZgqALDih+
CgOv4JROIpMQHV4oDLLusMoCSqnOSrwg9O7/d1SCtoJQSDCFhm69R6WaRDSZHZif2d2NPbfWFgal
88yq7iVNXgSn0I9SJIIw0O0aKB5jMrxzSKUwWYZp85aR0bwqjFvr78WNVl26WHf8Z7eFXvxdLK00
mpD8IcFZBGCzrBOeBHMPmTOA83g8SipwFsNcxErxXW3bqigexuJn62XjrqIxCtXhJ97Pe3YrmUPu
NP0Nx/Ibjp23PSWatw/AAxzKWZzBx/kUn+b0x203I9wtqfsnf8Vwy5d3vW8X8NTBCYeghHAGbxoI
14+Xc9a41jrnBeGIwoAgKCQPiyXAeTCZmbO025nhtk3KadtQejxeKKTOgnC999h0jhe6Y9znVtxz
Vnq3EVfwQgb41HescYvtrNKFEGRJO2pmKz6w1mK9JfMpJJKWalFLtg04KLDHCL2YkYq6K90hhIWO
FAQBWqp5sdkwNzPDnDXthOzoz8X27pm2o1tvdeOK38VN7A5ZytoOiiiK8MrOyxzN033nSLnjTOmS
dLzIo3mCMJ+5i1DNIqa1iG/tPn/3g/C7EPrVpyte/S87jga54B2KO7+3c+337e2ZfeypSVIqUJD5
+zmHL7XDIp8qXPpeTc/yhQq4T1cU+rMISygbgchlOa0VUgqUigiDOWOsE8oMeF/IJJ4sc6jt8EK3
5b01LxQh0gU3dMswhTVf+NdKpdK8OPgiZr07yahbNt7awVpMBtZa4jiei3Vvc0rHr4jIv5cUREH4
uL61PUbohSxRoJg1S6VSJ8Af5nSp4nOxTCpQLLkyk4cHNhqNvEqjUvN0deccJsuwQnQs+e6l1NbL
sO4bGMcxXgcdHa2Tcizn9LxOMoPPvfOZs2ivyaxBZ3SWYsC8JVW3rJMnEjEv5XdXsSMyv/YsuUMn
6LHvt9zypfkkX8gyv/6i5PIPafZ9sWPtlU/de1GeajIvUN/81E5QC9g1FBErzufRK0rklRLDKA9i
8K7IDJ2TJTt5IFvFfhcRMAUvFERdkGWxXzcvSCk7gQ/dVnwxdosxaYzJw5m7cloKn9fWkTXdvFVw
SnFdxUQD3QmLWacd7z2lKEIJwEl0JKmWyjvsvz0a3tAdJVIqlTpfvLs8rhJzIYVAx8tcoFtnLpys
xhh8V6ZmdwSN7aq50O003TqRZ96D4hxpV2pwZ5IQc/sWlncxRRWfPXOhS845SqVSHpLUFYpVPBCF
pV6URSiXd3zjniw+LUJe8XVD70p40y+yjpa+5nzBz07JJ7ixe0WHwLux5U7B8z7oeN4HU67/R/mU
EvoC/v+NOesZgiggUhFC5+M0y+a05+3xglT5czznH8tzTAr5sghQKAh9e7zQSfDpIuOtEyALg6+Q
Z9M07RxTTBhAZ3LoVhO8953EouLYgheMMegg6Dg9i2sJtUboAOtBBlBuG37bwx6PQ++eyYwxnYJW
0J7p/BwpB0FAFEWdDuqOE/Vubsbtnn0LTauweAs5pyDYHUkc3Usz7z1aSpRU83W3MCBN03nOT2Mt
tC1329bvpJ+bbApJKWuHThax6IX1UHz/Yjm2u1Be5DnmnW6b7Qf/ke+Q+KdFyL8cqfnru3NL48sr
A7IYcJDMgncLVu0CnloUUqaUGtEea0ka54Td5RQVXm7LC8yNZa3zjG5F2Gm320G6I17ojmwp9t86
Wg7oyKXFpFBwQrHSjuO44wDt5pitAz0KXiiy0LfHC5HSNNI6SrZLmrDjcbjHCD11GeApyTLKK/rC
XkazSRJr5sjMe5TX4CTO50lBUgqqpYhqtdohZu89Li3K7QYolb9xyIg5y7tI4Cle91TcGiEMgQSU
RuCQLn9PlRUCKbuWWEJhlQBvcS5FCAi9J2wXvk8zSWItwrq8/oyU2MygpSIsBWitOg+RMXNhRwWR
d69Muiel3QFn2alCXR/3KaN3i6ck2WgBC9gpWI33LZTsRfiAUsmT1OeCFYr8DnB5DRVjcFiEUuhK
xFI9RImQRGWkMiFoJWS+jBEaFVqsS4CgM87CMMR6hyBEZZqWms3fiiQVyvezuFVi46Jx+hKNkwHW
tsd+2M5IdRFeGyyCLAsJooQoTvFSYqOUMM3IUkUiPEorhPAI6xBC0ROUUIHOa5ybjMQY8L6dAa8J
2xJQmjgsGVnQpJoMUhdPw0zRUhhiM4MgJ7V63ILMUdYlrDFEpahdqniu7gmA1hFCqHxJFhRWrEdH
AcXrnEAipCDOMjKXvyJOkIcnwtwMnFvMCmReM0ZrDXpuKWWM65B62QtCEaKCIC87oBUykEgBfd7Q
22xgkpSRyQxnIZAKicKZ3AMvRCFTSIxxKKXnLdMKS7+YqbfOOPtd8I86pDq8c07Addc8Pazwt/Bj
DuZBAH7MW57Uu1EX8PsLKT06yI2fQAfEcUKWWYIgalvEei7noy2HWOspBQEVWyULEyinWAkChS0v
QfuYwGZID0JUSLO2ti5BINs+V0NTNRBSEmQlSpkiVJtY3x+yqjbERK+h2vI0mMtb0VpTKyVUZUhV
SXzkGbRDpJFBlxwHTB/CiB5nSzSG2DSDs3nCoaD9nmIXErg8v6UI4uhObJrjBUOGI1AhWEmW7Tg/
ZY8RejksIcKcoKOoRJY5emTPPK+yMQZXaNhtHSuKIkrlMuVyOV8WteuPZzbF568SwhiHzRxeeCzk
byVRCu8cvisTzRiDdwKpQBiDsQm63ANaIUy+3XuPVBolIRUQZxYtJC6JsUIRKo2WHukDvPL09A3M
SxTy3uO8pxUnnXRm51y+GuhyvHZLUM1mc57jZlfwm69JVhzjufXr7RIGAztO8x861PO39+cT5qXv
2ePJwwCcy1v39CUsYA+g2luiWq3QI3rQFYWJLT097QqKbq5onieXZtIkAwSBDgnKiqgaobyinGqU
lcS6jhIOYwJi10PmNVJM5bzQDoaQGThSmqU6UdKDz1KMhIBBrGuxSTVY3OwhDTM0eQanUgqpNEsb
S6lVNzMWTVGtrWLGNxGJY3iih42V+3FRwNIsol4tY2070kXm9apSZ0nTtqO00PfV/AxV7z0OA07S
bKVkts6UGdth/+2x0TvYn5cLUzoCIQkrEunaWhe5vBL6dhGvLKNarXbkDwc021qzMLnTw2LROsC7
vD4LgLMehCKMipBAR2aancyyvBhPirMZcX2aFav2JREWoat46aHtiRZCkDqDVR4bBgjpwNapeIlL
wYcVapnDiZAwcARhlCcceFBS4m1eJjdPQpBIJUlacWclUJQK6NbYtnb+PllsTcyTa3ZseU+sFvz0
jzRmxwlou4Q3/SLjvDdo3nCe4Z4fS+776dMj9nshDv3pi8GBAYaGFhGkIT7wlHWAk/OTcLTOnZ9x
HNPT05uPHSUw0pA0SgjhaYgxbJhRTpcRWocQKUaNkPiUyA0ipCaMcgem9ILYtLCpQycwUxphw/JH
uLb3Nxw+PcRe6TFU9UF4vRgdC8oV3UkqmurZgPKCxZOH0NKSB1ddxf3mQaqNjOe44yAYZlHcRykY
REU2f/k8Ai3Auow0SQjaHKOVJkma8+SlomQJXuOUZTwdZ6N8dIf9t8cIvRJGoBXGCozPnXUGgRfk
r3vzuYYunJ8XbpTHm0oQEtUm+LgZ4zCUylWSJMtDFoUiUPPThL0xBJVKx2GhlOKRNb9ldsv9jG/a
wGQt5R3vPZ2wL0TpgCAK27GtnpLX4DXWK0rCc965P8SPPwRSMpFpXvu2v6YytBc+CMlEPnnknO4I
pSIIc8921p6JK5W5wmHdacXOOXp7exkYGJjnXX+q8eAvd3/kys9OCej94gf42R39cBgcd/YN3HTa
r57wuFd9y3DRlk9RVMH8kzd8iR8eMb3bruvS9z49ViG/K47gbk7l552/dzbp6gOcTR+1zt/f5q/Y
zIrdfn27gjDSlEoB0gcY0U4gtBbv59dkyaNFKoRhHh2iAo20AYIKjf5Jbuu7gdvqV3P0wNHsnx3L
wMQq+uwwkTRkwVwtF+89KEEoKsiWpGIrjPSt4Z5Hr+KICyvE9REuOODT1N7+fo5rvBQpBCiJbF+D
iWKGZlaxYdlmrtzr3xn96i2semgVtfQRfrjyp+x16is5YekrGJ44AOmKcOncaNXKEpZLSA9KSKyx
VCqVbXghQJNaKPVVYNgiVj4NJRdZ6qfkZ4loMT05hSckYwYJOFmmsmgfplqQSk9gMwIMqcmQ5RI+
LKNck4Eo5btf+wIubkJiaKL52787k5kswooQa2KkFBhj81e+qQAnPDJUlHXEcCnhmvuuZ8voZiYn
Z7FW8NXPf5zPn/2viKC3yBLCeYM1gpbXVHzMJf/f5zAb7mOsMU1j1pOmki984jS+8N3/pO7yWFlH
HloFkOCQAoQFKTQCS+ZrHf9BOQjzBAhhsTLA6IDMOxL3u2voqr9EpadFbaYXgJ6efCDXtzyxVj6w
n2f6z/IiV8vEZl568vf40fN2vvbLEf95CmP3tJhdPNDZJtqkcxpfpIc6DjkvQ/Twt0su2vJpBA63
uD3JXA17PfA+PnvIAE8nRMQoLJK56KEmlfydsU8AheHjfGbetiebBdtN5pAXJHuiNl7NBfPIHOD/
8p2nzcuzq0HIT833qD17C8nYOCu3LEarQRZl+3HD3pfwbH88x4+9HZ3EBI0l1PrWIbJFaD1Nv+ql
qdfzE/1dGl+a5sD1msd67uTiY7/NZ194IxNJjfHq3ZRLiym1qpTrFcpZD6EeIEXSGwXQV+aanqvp
+3EfDz66hplaSrKuymWVb/BHr38FUTaI8p6k3MTgGTb701hseGDRxYSfeJDyY5OM1KdIp1Oaj0oe
vvUy+s4f4JUjR5IELQamBpkcGMmLBKYVkAbhLVIKnPI4k6K8pCpCiBQ+0ohEE/fF9DaGIRjDTgbs
qOrFHiP0xTogEIIf/Os51GobqVQjoszjhUZEAzR9D6e+9f8Q6+V5/XM8icst1tBHlCPFt776T4w9
+giBEkzUW8zEll//5iaOOPokGs1ZFCngKZcrpHGTSrkKeJyUlHrKVJXiXe95P9/+t+/x2tcfw5aR
CUbHJ6i1UkhayKBdFgCHs47YK5xMWPfYBpJagy21JrUZS9YypNrzmTM+wofOOAeHwPvcvsxDp/Ii
/cI7tNTIUIIs0YoTrHUYJ5Bao7TGCo0htx4qvbteq+TdfJUbOZ7bP/DLecN3XoX1M8/c7rHP53oi
Eq78s+vI2nprAAAgAElEQVTwiwWXpS/j5eGv4Fb40ZMY+P87/Cx8ZD9ODz/KT378pwB8YPQHnDMc
cjYf3O4xKw47jjNLb+SN0Xnztp926Y/4LO/e6XP/T+AjfG6H/3sigtyazAFezBVcyUt2+vxncQYf
4Gy2sAyAPnZc46PAMdy23e2n80k+xSd2+txPFR5ePsUzNq1i+p9+S72e0jM+TlaZJpUP8or6Mq45
8hqe/79fS8/UKlqLtrA0rbK4MczDPb3E6lHu0rdS++ZdDN68lAcXrcfds5jssRZXv+5rrBTHUW82
8GN9/LbvOmorUirKc7B5Ngdu2J8+tx8TQzUOW7cPb/jzF/H1f/sexxz1fDaOj3PvgXcyVWsgEVRk
CZdIvBMktIi1wxjLxMQMzThjYqqPeKbBpEsIleOB/76Q1x7xRrI0ZWxgBiUrlOtDmGAaaUFg0FIi
gxAfKZppjZqNESZAN3uQJcFU7wTClmlGTY70O37B+R4j9JF1V/Dz876PpM7kxEbKy5exZWKc/sUr
sNaxeK8h7rnzep59/BuxViKEpowmy1pIH9NKW/Qu6qVaW0QUhSRTLbJ6jZtvvoljnvciWi3D1PQY
mckwWUa5XEUPDTPQ1w+BoiQrhB4OP/xABpcuJ/GCxSv3Zsne+1Hq6cH5CGMdXims9Rif4rwnjpu8
77T3E2nPI6PjrF69jvrMNIlrsPrhLfgsRuoIj0crjY4iQq8JlES2Y0+ttRgnconIQGIdxoHzHpe/
7xulNN7terXFuz7xToLw1WDgE+Wz+GTrDL5efSfvanwDgP0PWMPKc3rhAxdyH4czweLOseuOP55F
B3pOOuFX/Mddb+A+ezg3mby++L5/uQ9rv7uOF33WYFqCE8/KVxEX/pXiju/OWaZH8lvUa/8LO/F+
WFTmzW/9AZA7Zg/lflZz2Have9E953H3IVu4u3YCX3n0kzzzz3Pr92Pqszv8rhFxh1yv5kR+yzN5
Jr/lGk7axd57fJzI1ZzENY+7zzO4h3s5Yof/v4YTOXGrNlax/klfSx81zuG0nd7/Gk6kO95pfx5h
giGezZ1P+txPBSZuuIyps6fpk2VmR8bh4JXMbnmAgb5h7g80z4yXcqH4Bu+UH+GA+l5MasXUfvey
xt/HWrOGldVj2XvpUuzwAKXlnmWNpYyVZvn1I/dw3LJhjh05lo3T4xy07llkPoZFnonBcfZdsR+6
Yeif6qO+V5Oj9j6OwWUXIVSZ/kXDLN93FcvKi0kzhwkyVKxoBk0y43A+YGJ8mnf/7fuoliQPbjSs
feA2JhsZrua55PKf8S8nfpm/WXs6pm+MgSxC9dXp9QFKK6QseMEgraanNEDLxngvIVPEBvbfdBSZ
TmkOjnGZPB/40Hb7b48R+oUXfhcZGoxR9A+sIk1C6sozM+3ZMrKBveuK9M57Ofq4U0iMAiUxWYs0
meG231zL8mXDfP7r5/Dlr36ZocEhxkcmEaHCecXaRx4gKvfiTUJzdgZjDPWZKVq1GczKfSgN9pMJ
SWpbZN4ThAF9/b00WoZWq0ViWyQmRekQYwUeBUqjBFTDMs8/9oVsGtlIaXgFs03PQ48mlJSguqiP
selJFg0tQQiB8QaTGYxzCE+eWSoEuWtE4n2Gx2O9aYdhaYTwebpzltBqPbHFtSNcJz9FUZn2k63c
WnxX4xt8p+cvOV7fyBvX/gczvJS7mcl9Em307+M5+HPHc/wJ1yIrr+K3zb9jzfmmk1m68or9OPHP
HuKHL9J8rKve/Ku/Y3nehyzfPDSPpLmbZ/J6/guLmidAnPIDwy/+dPtkDnDYud8G4AEOpv+FV3Hi
SYZ1a/fj4kUvBbbvtU0obWMRP1VkDjwhmQO8gf/cLqH/Bf/K93gHV3MSd3MEEyzmj/kJV/ASDmX1
Nvsfwmoe4NDdct0AV2/VLydxDat4bLe1/7vi4cvv5FnqmYxFlqVDPaTNcaJkJatnF1PfuBpbP4ba
d+7gKx/9Pm/ffCqtqmZzM6Ehy/RcO0Gwqs5/fvxczvjuVzggPIpNR7Q4svRcHuq7l31uP4r1ixJ6
pmG2ZUiZIZuMCJaV+GX5Ak5N30AaaMj6GIsSICQMSkhpGEu3sCWapRVqEulZbFZiVIoNpsFLquUq
Lz725Wzesh69qEHa3MzMYxOUQsnK7DnUbcbDqx5g3w0HEFdm6WlWqKsMkUq8EHgvsELiqVPyFTIr
qEXj1PvH6W/ty9TAKIGRrG7ewQmDO17F7bEc7pEtho1bMh7eMMW6kXEe2rCOsakYFfTRU+2nAqwa
7OPyqy5ldGqMZpaRCse6xx7F1ke44qJfEKFIa5ZS0IfXmrGJCbaMjjA7O8HIlg00mjP09JaxLqXe
mMa4lC2TYxgMRgoyJbE4tPSkSZOkVcP7hHXrH2ZyegQZAsqBdgidR6dIJVChJra5nJKkCZm3jM3O
IMIQIwwZBkKRV4lTnkxqEqlpCUVLamKlSQgxMsArQRRqLvjFeQQKAiUoa0V/T8RQ366n/h8k11Ab
6sEvFvN+zmqewZhYwnq7it/ao/jYVquAt9w6wPXXvYgNj+2NiaHVKs8ruQuw9wl+HpkXGDqEbUoH
pMwPlXzGW7fNVt0eDmZN5/OlF7+Gf/32u4gGdq2g1suumk+sz+KOXWrnyeLo7cgbe7OBT7RfvvGc
9v8v4lW8i2/wEq7cbjs7+/ank7mEI7h7F6921/EBzt5tba3d3OC2xiitezdz3WyLe9d77ovH6Hdj
DC1aQp1bGd5wJPufF3B+fAGteIL7/E2suMMwvGWYyy/7FZMlRdzah/rimLpcx3g8zebZTUxNPIpd
P854Okm1H1wK6ewMvdMhB23ai+uGr8e6QQZMmRItqlEP3jkaaY2s3OS/Z77KN8y7ubL0beoDDxCo
SZS0CCWRIkSgaGUGbAlT7yO2mpHmGmzF87aNf8yt+iLuOfxGys2VTFQEqVTEQtDw0FIBsdSMDI4x
rqZJoozNfWs589fvQyrB8tmVVAgJqrBu8N4d9t+ek1xmW9TrdQKlGZmq0VOtEgcCwwTNmQnS1hTD
QwMMTj1If/A8pBX0ygZrR+5m9cMPMDE+jRQij0RRCo9laNEiZmZniVuTmMwxW48pV6voIGSfffaj
2azRqE9Qrw8j+zVlZRBSU+1dhPOO3r6A6elJ/v1fPsVgXz/Pf9Fr2OfAo6j0L81fD1WfYqA/AqEx
ccrAohX0DQ1Sf+gehgdX4GpbEGmGEpbbbr2J5x33AlpNkDoBK1BeoSVYnzHbfJiHHnyMo498Do9t
fJg1D1zP8MCf0WjU2bxpI0cefjhK9O5y/65ZlL/YYdINskhOdbY/tmgVALXFfVyXncDP668EchL+
q1sToijmdP0p7vjRs1nhoVxucc+5kiPekhPxLTcfx4techlFKWiAs5cEnDa2fWdpiRiYqz3xrc98
kDf845Wcl76Rv/vImXxhB2UpBLDh14IkCXnZKy5kaGicr/xdfsJ/cCmfkTvOZlWh593jJc47YDOt
nn7efNtFHMsPUFj0z1+Hff35nML58BS/Jvq1XMDtPKfzd0HMW7ujPYIvchrP4k7+lO+zFxs6L/54
iAP4HH8P5NJSwvwO+2JbbumhRi81TuXnnMrP+RZ/zUhbW98ZuK6r2pv1PMaqx91/MWOMs4T/xS0d
J6vAEZJuc41PBmlTwEbHuEyYXtuiFFSoRz0I75id2MziRb0EfY+ydNMyTnzm6/Cixp2Vmzj4scO4
Zt06puLbSH3IMAYTSHrSXqYWj3K4ei4JM9RrYzRmUmZKU/T2LmK/A/bh0cYDmGbGdN1QX/UgZrLJ
qKrRWtVgXe9DNH2DxetWcP8VN5LqGg+9bIafPWOUql1OkiRUXEh96GEaIURTfSzdq0Rl+SA8dB2i
bx+WmbsYjSd45eRb+ObU59l/1SGosQpOgncRWWSo1CrUy6P8YujrTG2e5BlL9+bm2TUkt4+TvHw9
6w5ez8X3X8xHxbf4VfadHfbfHiP0o487jttuvZXpiSli76gGIbWZaSbHmuy9bAm9vX1sGR1n9Kab
oe8gjnnOCazffC8Toxu4997785IAeJw1bBnZRNpqMTMzg9aaVpJgjaEnjMC26Ost0ZwZZXBggFqj
ycjaBxkT4JoT3HL1RQgpaTZmqFarREGJN77lT4l0icwK6jMTTE9M0kgtfdWQDdNNnHsue++9N9Nx
RikMUUIwOT7B4sWL6VUePzvFMYccxOzGtey//2G0Uo9zAoHGmBShJBddfgk3XHsz9x16C/ffdycz
M5v57re/SH9PPzdcdwM/+8l5TE/O7HL/vul5P+Rnv/6TeWReYL3dm1fMXsJ9g8/gBT+4nvv/8+tc
euoozcED+ck5b2R2KM8R+If241GQ+aUXv4Zjn3sTAD8/7y0sX7GR9ev25bSxH8xrv7DSLR/dhrze
+Ykv5vtwB/9UCdjreM+Br3Kc8A9ty73rgBelV1CbPZULzj+V97zvCxzzbkVtg+CzYcDbr8gYfMk3
uYRXdPYvsklPuOwEvvSDl3Pxe1fzSn0tf1H6NB/66bvZcNQxfOjir3IB8Cj7Ptku3SU8l19zM8+j
sp2XZift+vAf4Bwknit4Mfuxdt4+t3IMMeX2/iV6qFGnl4NYw1s5lzUcxME8yPf5U87jjVzGDLM7
eiX840B2KetPRObv4LvsxUZGGGYpowD8PZ/jCl7Ca7jwd4qYOfhZh6AeKlGbqRFbgSuXmJqYYHI0
Y8XSQaKoxOjYFJNX30RjZcwtf/wor7//CB6b3sQDd/2WqWpIVaZsDibYa02FMbWZ9ZW1TKyokxqF
n3Tsv1cvidBMOMmjVtJje1m5ZT/8/ZOM3/cQjbTBNy/6NuVSSHO0RqW/h6qqctDL/oRSXwkfQLBW
oycEPa2Q4d7FXGVnqO4V4A9YxIxs0lOq4IXCzSSES6rs21yOq4/z3uDdfDc5m3ft9QGiesji0QEe
XbKRxY0yE0s3s+HuR4j+vsRNf3wpG27SRGtTvnDuZ9j3uD5u+e9bSD45wrLa0h323x4j9E2jY5R7
+nh47Xq8cWzYMoK3loH+XoKwxPRsg2rvAGvHp/n3c7/P0c86gvGxDczMTtOot9AiwFqXv91beCIt
WbyoD2sskNdhKek8htWmdUqlCjOTWwjDEq36LKUopKxBhhWaaUap1AN4yqUqUamK1hGB95i0STUq
kbZalHWIRqCUYGx8hGr/Ehq1OtVyhZiY6akp9lkykFdIK5dYMz7KQJRSkQHW5ElFRkoS02TkkQcJ
TIPbb7oKk6WYLOaCX/w7pbBCoMqMbVrP0KKdeEPFDvAfF7yd95fG+VLPtuVoV6nHuG/wGTxi92N/
9SiXbH4Xy48+ncfW78M+cl1nP7nV03HyKy/ofD71jecyOjrM8c+/dpv2b7j+RJ5/whPrzB9pZsys
h/7t8Me1vIDb93kRxy0Z4/jnX8Nll76K2a99nYlDD8YZwS/foTmWQzvvIwUYZ4i7OZKB6VxieWBw
Tnv+57GvweVAAKevfB3P3fhfT3h9uwOv4FJu5nmczKXb/G8t+3IUd3ItL+QkruElXMkkgyxiits4
mmFGeSmXs4wtHMb9XM5LeRZ38gtOYQWbOIszeBM/5Uu8j2dxJ2vZb5fIHOZb6E+E4hWABZkDlIl5
DRcCMMwIo+yYdB4PoxOzrAyHmJxpkfiATaNTeGnpqVYoRWUmp2sMDi5i8+gYF37rF7zp5L8hvKtF
o1Yji2FQzLJJBESlKl6PsvqQtQxtXsIxPz+ejX2rOWTLkUyNTLSzNjVRWCaxKUFoWDpdIRQt9q2s
QvZDqzZDFJQQNUWl3Edv1IMbk5RlhThpUB6QbMhmsYGjHkmskMyOTyIWl2hOThMNLqJaL3FLa4Ll
ywJEUmJIL+fkmRfy3+Vv81fVjzPY30dq1kHvNLcGV7Hiziob3jZJIMtktUfIKrDugpt58LIEpOCv
157CkgOW7LD/9hih33DdzThnyRKHQuIyR6AEuDzMsNVqMDFVI2kmxHHKJRf9khce+0z+7Xt3kMSG
qKdMoBXOGZYNL2f9QyOdl1HkLxayNJp1enr6sGlGq1mj2ttHKQzz8EEBrWYLISFJMkqlCkNDQwRB
hDUeY/LsTSU83qcMDlSwaYPazDjeW6o9PYyOjlGKIrxzxK2YarnKvvusYGJimjRzLBse5GMffh+f
+/zXsUqQZSn15iSr19zFKa96FVlqyKxDhSWEFDgfo1RejOz6G6+hUqly6MHv2KX+9Yt3PEBrvode
UWd/NZdx1ho4kOOeeyX/dO9cNIkzuZNlZh3077NtO8PDo9tuhJ0ic4CHLhIc+Krt6+LXcwL7PtMz
NraEjRv25tDD7uUwfsJ1q0/gSl7CCWsvZPibf8voh8cYns3fJXofh/MCexxC3s7pfHSH5z3mXfnq
4X8KH+Uf+Swf45lb6dv7sZarOamjqQNEJAA8h9u5keM4nps4iWs6Vm9CREbI8dzIoaxmGSMcxupd
soqr84NYt8Hf8zk+z4e32f5UxqyP37mRxuoMsHg0aZKidO62j6IyUkrGJiapxTGyVqb3M5pFr3oG
t37jR8zEECyrc6CFUn2Ci14yzmG/WUHfhl6GUkVFHsDDS++id2Yxfb19tFotstTQ01sm6c+ophVs
f4KaFtT8JJlIccKweGiYUihJ0mlCAjLABdB0llVVhayNoCZHCExGudzL+i0b6S9VaYYWP7WZ8ov7
WHxwFTulaE3O8IolJ/Kt75zNuz79DqwYYmZwJf+08TROvvwQTuh9DyNijGCwRvLmIUgmEUMN6uWU
A0aOYPWau9g8UoNXbr//9phTVKMICFAuL46jpUbgcdZy5x2/ZWx8mmYzoRJGVMKAq351JV6WmZw1
hGEJrUKMNThvefDB+zFxTElrbJIg2kXrw6iM8R4vJF5K0syiwggtBd5bMuNIkoxyFDA8NIRNLa1a
C4wBk5DGTRCC6VqdkdGNjI1u4s7bb8fj8N4yOT5Bq9nCZoaZqWmyOOHaG2/g3tUPIKKA2BnWrHuI
O++6jWZzFmtTbr7lWlrxDHEjITVZ/iKMMCQ1gtRrMquwCKy0xGbHVdV+F/SKbQfy979yLp//xNzg
PWnmKnTbJ7s9Mt8d2JrMz/nifJJtjsGSJWNs2byCZcs3cez5J3HEhhfQs8JzIa/he/YvWXnLSzi7
/VKM5/sTEHvsiX58HNguNNaNE7mGMzhrnm1cZe6eH83tnc9/wzeBXA6p0CAkYxkjwM4RbES8jXO1
QU/ncyG5PI+bOtvKxDyf67fbXs9WyUm7DVPkiVo2Q/qMUAhk+z2b99xzH5u2jNNsGvrlMK2hGb59
4zehEVIf81S1RzZ6+W24mfufM8LyG7YQbuiBkmFD/8Ok1tJXW0pYCvP3Egd5tp9MFD30EbklzKYZ
YtQR1gR9ZhH79h+AjkOSGYNvhcSpZNbXSMPcuFs/2eDBqQarN49gA4VxMTPTk6T1Fg0y6q0x/ErB
JfZ87l2zGuUFt667lenbRvlG6z+4Yfn5fP+ev+Tkq5+JnRxiJrwLnUWUN2r6e6boi6royQH6plZi
RMzKiT6cfBrWcglCQ32mgbcWZyxKKIwNGdp7OYlJ8VJQHViMtZ5WMsPI6GY+/LHTiVNwto6QJaa3
bCS0MYkOyGanSROD6KkQKcWKnj5GvSdpNOk1NabrDbYkAQ9O3cH4zHqm0wbDehEz6zczXR8jCyIO
PfbZPHTDzQx4x8EnvYDEeSZv+TXB4CCf+5fv8s9n/QNBJUSKkFI4wOKBBg+pPCFAaklmmnzy9E/w
uje9gf0P34dmMk0pCmipFl/7ztkMlXt5aPUD1Gp14rjJcH+V5tQIJksYGx2nrEKCZcMcedRzWLl0
FQMrlu/2fh91SxjezgNxytWX4Padn4n5lWUf493kzs5GvUq1Z04HrtVyh+1yuZlvf/N9NJsVtvjl
LBObAYgpsWbJwSxx46Q+oBZHpLoC7WJq7zviE3z5nk8CcPAvvglHHo5fOUdtH+OzfOr2T5AkIaOj
y/nKOR/hy4s/yrPXruZ77v+iwpyAyosFzTM/T/lDhi998j0AbB5awfKJTVw38AIOVA/n29wylokt
rJjcxPs/+FnG3BLYdZ/zk0JIxtv48Tbba/TQS51aF7FqDN/gnQB8sCt6ZCmjO4x2OYOzOm0BNKjg
EfS0dfuzOGO7SVAKs007N3IcCoNtU8Nv+F+cwVlk6I6j9olwMa/gPg7fqX23gQAfp2gEsfekHnAx
ew3vRWoinFH0LZIgPJXJXqYma3z89I/RdALXqJGtyPjwPe9ixS1702MOwDQnSE0PptJDUopZpko0
vKDRmKTsHBNxkwfj9bjbGzTHNlNLWvSUVzC15TFmapvJZIXDjzmah266jgFjOORFJ+GUYvLWm5F9
fZzxvW/yww9/Dv+6Gtp6RN8gffXlbC6tZ0mrl3WqzJD1nPG2T3La1z5JusgwO7KWvVeuYqO5m89/
6QqeP3kM195/OY2WxzRnWTo4yMxkntMyOzVOqgSD/6+9846Xqjr3/nf36eXMnMI59CIgCIKKLWrs
ESOJKcaYYuJ7r4kxV2NNNFGxxGuMGhNNcj+vSbyaYkkxKvYYxQIIiKgg0suB08+cM2XP7nu9fwwg
CCZCvFc/vPP9Z/bas3Y5z5n57TVrPSU5hIlTJpEdPxU/67yn+T68SNGmIQyW1iBHdUIRksvn0SWV
nnIfkUwaWdNJNeQIBFhhyPBcE5IkE40YVMwSqhLjv37+c/70wO+YcczxLJ83l6rpcMY5X2POfb8j
r0e46Oqr6Vq/mUVP/R1Nj/Gr+x/gusu+wzQzgpOOceX9d3PB2f9OY38rpTDk5p/cxlXnf4u4onDW
+d+iUq3yV7tEqOlMaG2lORpFSaaRgEQySlvbENIbazlX0uk0WgjNbTprNyzkpptfwXEcUkmFu+74
IZX+IqObh9GxsZMgCDioOY8obGbCmBEgPKrDW0hEYnQrPkL0U+gq8tb6+fCdDzY6ckcxn+OeikzI
TP0J5rin7tSvP8zhnP1dLr+7iRX2EGaEa3hGOoHzu2dzW6Y2LbP44sf43uyasGYb+rjmAolrt7Yn
H7CUn3+2b3v7qvAoft15Gx1thwBwzXESrdveO/RIxGfHY00cCZe9cw8zE7VF0XRmgE+c8gg8A58p
/YXKN2tBTm/5f+Sg376Fn9f45S+/SWeulo/kk8VHuS5+NeMG1uzWBt+75WcA3PIhRrt/jBdJUtm+
qAls376E27iWa3iaEzmJWu6ba7lmJ0F/d/s2Ltne/g3n4KLv9EDYHcFuvv5HMJ8jdhilX8FNAO9b
zAFO4UlO4Ung1vd9zDbU/VSCVRKyVpt+zeXyBCJFR38nRkInqhpkGjNUiCOFCkOaRyAhk9ciDHSv
4sh/P4z2ssmGuxZw0sEH8NLrC6hWHc78+td4/P7fk1OjfOO6K+hd57Li6bkkjDgP/O5urr/4QkI7
gj0kxY333MPFX/4a0cEstqRz8+23cPX53yAOfPn88zBdlz9VCriqysQhQ8irBk3pBiQhkUhGaW1t
pWNNEsexyTU0EERMjqlO4K0f/o1XIgGmU6ZXLeGcP0C2IwqNmymuX0MYShzYMhy/r8SMUfshhz6h
52A05BiwA+zQo2f1cpZUnue9kpF+eIuivZ1MOGACtu/iCg/Xd1BUyGSz+L5MQ6YJWY+hqwojk+la
mO3WWn8NiTi27bP8zaUcPH4c9/70ds4/YxaJRJZrL7uEwpKFRH2fppiCLbk0aBK+b+MOFFCkEDt0
ccyQDYtfZ4gXEA0t4kaEN+b9HdUvIzyJhY/PoVqpEpd8RAD33ngjWUVGSSQBGUWRiSXiZLNZlK2V
hmzHQ4obVJWQqucRCIgm0hj4pOMZdDVG67DhqIpORzSFJgvmuS7RaIwgBqokUxAukqmgBTK+Gv+X
bLzAO5TDtFd2+97T7omcVpqz076LI7dya+JSrjFnc3H0NlZeMJzRP3yF84ZdzqGbV9Pc0sG53uc4
rTQPgGt2mCwYKOR3OldPdzMrzjh3e3vjqGMYO34zHatrgn7tMe/4XP92/D30PdfEd6bftNM5coXN
5Bt7KQ5mWb9+DADD5U0cH32WPzhnMWnwLRqlHr5k/J7b7Yv4qX0hK4PaQuhj3if3yFb/22zzOb+P
s7YL8Y7be8oxPL99ewYLCXYI59r23jIm7d3N/i/i9/hMPHAchCUKfojqeSiqT1JOICyDXHossm6Q
120aom2AjG3V0ulGR02g4z6TiSMCjLFpbv3VXVz6pVnoWozZl1xE6bXFGLbHmJhBIBxisofrFikX
OhEa4ARIXoW1CxeRIyAq+/iqwhsvP03EN5FDwcInHsM0LSKhSwKJu394AylJkI2mkCSZUJKIxiJk
0hlUVaNcHEQOQ6ppGQ0fpRKQcnTyYSue1og6zKE3JjCMsaSDOJ0RCUmB3sAiGtFRY3Fs26SsKESF
j2MJzNh7x6dIO6al/N9k+ikHC0FANKYThC6qJiFkkIMYTlXBtSR0zUCmlimxUjFxHZ+GhnytxJss
M1ypkrBKTBi3P4MbVhOGEpF8A5WebgzHJUzFCXxBWgkYMX4yesswojGDTevXEIQ+pZUbiAUevhYg
JA3bkNFEgOwFhGGEqBZBiCK6pOOGKnJUIWgexiU/+w3lcoWerl5eWrKIlxfNI/Q9ij19bO7ayJjx
4xgoFvEsh4QaoRr4KEHIqJY28HyKpSIFv0xxoA+zNEimIU/RtIm6Pn2OycimVvz+Il4Y8PJba/aq
4sR5P/ql2BK2ATU/Z4A57mkAPJycxSzjUaQ+wcPJWSzwD+PG+PcBkPoEp+mP8Kg7i+9eeQ0//9kl
xP0tdNsTMQybRLJEf9+u3jc/mPZ5Hrz/K+RyvfT2N1M5ZhpdXW17dM8/uOZKFKk2+v8jn2N9bn9O
fHYyj/z181xw0U389LdXIPXt/vP6zcgv+S/7PCQp5FDlFSYpy5mlP7JTn9P0R7nOuprP6H/hAHUZ
nLbYnt4AABxUSURBVC/2yrazJekD+9KsZD/Gbw2i6qeBHIVd+qxmLCEyqxnHuK2j+fE7BF7tCe+e
b9/bB8j7YbbYc/uq56li2sYZ6JqJqaokJPAjFqqrYPalCOU8ruSQERogqFQq2LZNY0OWsOKhJD3y
V6QZeXUX2alZzLVFRCARyzdQ7O4kaQdISQMrsIlHYrRMnkTYmKclnmVg+RpC32PDujUkNBnhW8iq
imMoKJ6P4odAFF01CCmiKQZVXabBSzL/6y53n/wYhTCgs6uDN+e/xLOLX8Oumvifr7Du+tVMGrs/
vRWbgieIhQa6KGOIfoY0tyB5GaSuQTapVfoGC5RKJbLZLFXTRDEtugiZ0JCnsqXKsoOWUfmzv1vb
fmgj9EBx8F0LPdCRpQBVyNhCIEsGlumhEiV0Qqp2mYgRRQ4kIqpB4LgIScZ2bUzDIqWHGAoIP0CE
EoccdDB/m/MIaT1KYAf4IUR0mS0bNlHcsIVxuQReRw8ioREqVSqEhGZIKhZH+CB7PkKRCf0AIQV4
ikAVEkLysQIXRICQIBatBU9YVpVYPI4qgV0skyi7HLffZJAFqajB3Kef4alXFvKFz5zOsKZGXnju
aXQDjIrGx0ZPJB6Pcdfd95JqaOT4aQdjJlRWbVxHbvgQuv6F0P9fJr61fXtL0MrQgS181biHe52z
mWU8CrzjCXOk9vL2vm9kDqiJHSDdKIhgkZvk0r0cHCfCN751Oz/7yfd2ud6a4R9n1fhZtA3dxJbN
w6Frr28dgM/zJ+6edBVTpr7GpMmv091dW0+44KKbeOjOLyJa4Nz+X3GG/iC/+PrXee7Zk9jc3kab
0sFJxadYfdhIvr7s1/RLTXy7cgc/t2tTVyunj2H8krVszraxZ4+b/xl2FOZ7OJuL+ckufcZRmzoq
kt5rIX8vFnIIM1i0vX0bFzGMdjYzlIu4HYASSf6br3EBd2zvZxEh+q5UDH3kSFFC5/1n5NwFVSDw
cdwKoRoBWSFwBWqQxPUk7GgXlXg7q1N9oCqIsgu6xAZdIlEdTW5TmpwHMRnCyEhUbwmekDj4kEN4
8pGH0KIRXM8hKsukQoXeN9fi6htI5Zvo6dqCSGpIYQXJN3BdQUpRkQMZ2QVUKFaqGAmdQJNQkBDC
wxUugSwjqSpaWKuDbNs2qVSaZCJOv+ERc0OOHz8BDwfSKm/+7TkeenE5Z595Cg2ZBp57YREpvYQ+
KDh67HgUTee/f3sfDdksp0wbT28+y7o3VzNy/Chea1j2nub70HwCzAEHs99n6YK1LHutg45NIYkg
g2mq+HICy7RJaBI/vuV6Zh55NMecdALHzvoExx0xg+NnHU88GiMRy1BwBf0Rg6oWpU9VWL5+HZFE
jF6vjKdAxatiyjKqEkEMVjBtGUuScEwX2YmgeHE8WaPHN1ECQSh07DCCmkqy34yphFIUO5SJKRq6
msT1ZVRCgiDEdh16urvxLJueri76+npwojLPP/YY9PeCX2RUXOaTU8bSv2453d0bOezwGaSiGca1
5Sl2taO5VdIi4FMz9mdIymV0Wub7F51HuasPf817r2bvCW1KB0+lTuJe52w2ZYcBUBFxjD6b71zY
wH/+24Vcdf4VDFE38+tzzuI7X72RzrCF8y/4Mb/oOYHRo2uC0tzSwauLDtvtNWJ74DJ/wJQl/7wT
8Lm/1OZt//OGG/jNXecD8I2X7qYjbENRfK6uXs+EwZXcd/s5vPnGdM47+nakPsEz3km8MPcERFj7
eG8Tc4DxZ53HDbHvo8gfTHm/f8SNO7hGWlujJ+/jzPfsvzsx3xv6adgeQfqPGMn6ncR82z0IJMo7
rBinKO8k5sAuYg4175Q7+I+9vOsaog8GNpdYtrqLt9/opbA+xJAVuk2JBnUYPccViGoqj577ON9t
upTzJlzF2cMv56Lmyzj09JnE9quQDsayfESBrsZNrEn10tMwwCudLvFYhM6BEooexfYF/YFHIptE
2A4Fz8XxA4JBB0WK4Xi1HKndbhXhhjghDAoFozHHhEOmEvoGti+hlGyKuolbFniqheZYKEWPtT0e
ptdJX2eJ3jCNIgmeePoxgnKZWDUgF0kza/JEOldupDhQ4PjDJjNEzzCmrZXe9vWk5ZBsGDJzxoG0
pqLsH89z0xWX0FPoQvyDwdKHN0J3PAaKZSTdQFKjuKHMln6HiK4TsU3GNqXJaRLrXn6Rkbk41pZO
Fs1fxFEHTOOJv7xASY6zMvQJqhKdS9diyC44Ho22j1NxiSkGvZ6NoqtIwqchqSCXPQLJpuIW0WQJ
RZYhkHBDByWSouTZaIpOoIX0VgoMOCa2HBKRJMzAxUMmVGUCIZBUHUXTGTVqNP2lgVqtQ1WjTReM
yUXp37SaQp+G8FzyiTxaPIJfNekb7COueAjPZVhjgnLfRs7+wkk4jsWWjh5aRo/ixScfY9rYVgYS
xgdm75P0Z3gjcwCzq7O5PfEdvli6jxu+fhmvTf8GL3y5iQkXj2CRcygPiE9xyW9/ATLc+YfLYX9o
mxvn0fznmBU8xIbSzlFAp2pz9ni+ulx6f8Evt+X1nXLDbAqGMWnRSgA2bhizfX+vqD1NHn348zsd
PzCQQ+JdsyOXXsoPqvCD6g/f/c4HytuM5yBe5UlO5hM8RRSbpUzli9y/1+fM8P6KfOQo/NMFUYAN
jNrt/jP44x7d1zYaGHhf1/1HhHJI72AfgS4Rkz36Yj1UexpQ1YBV0xcyplLiIO9gVj7/d8Y0Zljd
3cvS+S8w4uBD6fz5c1TkgEd+/jyGr6A7nUTjUVo/MQ5t6Rtkih2E+UYGQm9rcR0PN6gSShYSLp5v
ISRQhEBRJIquhZpMUQkDkMFXJQbsIn1WiSCiIIch7dEUo3zBUCWOGhhIOMiGQtPEZtrf8jAGCgxz
Fdyox/hcEmvDGsxOBd0rkW2JElN01N4+Clss/AjIfoXmbJy+ro2cdeYpeLbDlo7VNMYMXp7zew4f
lqQn8t759j80QVdkGVVT0CIxjjjkCIY0DqHiBcw6/njuve1WrA1vkx7agtLZyfwVb9NfKdMY+BRW
LOasgyfz65eWECajRI0IES2K5dTqg85btpLxzQ2cdc7ZrO4ZQAklHnrgAcqDVRL5ZnrVCEHLcCQE
ahgSWA6tQ4dx6CmnYA9WCUVI2apQtR16S2Umz/wsfRvWYa5fQShgyNAWAuHheQ6hb7FyxVIKfVvw
fYfB3i1MGdvGeZddRtKIYCOjqirJdApCDxFYeLgQ2EiKjCMEoWsSBgElswxyGi0ew3Nsli1YwPDm
95+L4x/x7MFHce3WjIvRuU9yi3wpHhq/W/I1UulBtkw5jr8uPphJxeWUfpLmkWNOZ+7yEwG4tno1
S/zpzPcP55HY6dy45goOMl6ntXIPL790DBUgf9yhPHjfV7j6hB/wnHcsw4evR9V8Xpxbywp3wTlX
8trfxsCGDRx+ecDAaokXF7Tw6Tt6WHavIHPsSH5377/tct/Djw654dobAbglfglPeSdzFUchz36J
ATIUaKCFLuJUd/IWAdhMGx20cgBv0n7IIXQuqnlaTz4roP/LR9OxUAJu+EDsO5/DOJwFO3meTGAl
XQzh4zssVh7I6yxhGtP/SXKwH3IlR1KbBpvMMvL0M5djaN0aobkjK5jAg3wBgGa66KaFQ1hIbKs/
+zhW00YHAPdv7beN099VIGOADD/jwj34y3fPtvuYvRfH6lWNhCJjnJjntJNPo+I74AumTRjOH350
D+PeaqYx5WD09rJg1Tx6Bwdp8j163l7Cv005jp/MfYb9lDx2zCAvEpiiyMB/v8nScyfR1J7mP864
lL6+PhQBDz34AL7QMDKNdAsNt6EVWZPQhY9rVWkaOoHDZ56KW3ZqGVttk6ppU6pYjPn4OApdmwk6
XiewZawhOULZJPBVehoKbKy+gJ2u0tOgYSYlZpx6EF84+Us0RppxFQ2CkEwspJhwWa32I0IbTRQJ
8Fi1eQ2GoRMGIaqsIKRZuKRIhWUWzlvE5CnvneDuQxP0tqF5GkUjUS1OSzKFUbSQFYn77rwT3TP5
5re/yYP33I2zdDEfO/lE5j7+NCMzDTjWIJVVrzK4bCm+bqDKglDSkVxBqOoEqsARHrN//Wu6ugfp
6hggHU/x2cMOZ/3qFUweux9a1EALXWK+w+rXlhDYLmEyhxZrxiwN4gjBpT+4jmNnzmKqkSSZylOq
OkiKRLVaRJFMQq/M4w//hvZ1yxkoFjB0la9/ZSYjm1oxhjdRch3aV61jY38Pvl9myaL52FYV0zHR
EgZhUCuc4Ycelm2haApVT8FQNAxJRhEhshDc/Ylv7pV9Z5UeBsARBuvXvTOqvjLbwz2VmTx/bxdT
vtzCS8Fx/OCaK/ns9X+mJGoj5xfmnsC29OjXxK7b5dx3J8+p+XB/vhYRelj2JKZcdiHXjfsxubEZ
MoUnmDz7nRF0qT8KlTJnnN3FpmoDhd5prJj8RZTo1bTOEIwYOWaXa1iVK9h0y3WctnVhM3dGB0+/
PZr9Tv4VAEsOOJmP3xBQ2gQP565j9ardp+R9YtvGVq/MuQAL34cB3yfrGMXhLADYwVvlTL7I/Xyc
57eH8m/jn4k5wPe5cZd9E1jBRkbwRz7HRkYwkRWcyuNM5G3UrXPW3bTQTBczeYIyCd5gCo8wi/P4
LwCO4sXtqXi/yB92egDex5msYvwu192f5Uzhjb2cu5+9x0eIqSFt6Sg94xMU5/fSXBpLObGK+fcs
ZVwhzqcu/CTP3nsPxYXdHHbqJ3huzlOMyWWx3BKD6xawZcMKPCdOKQKdQqDaCcy4y9BXN2J2w09v
/L/06iY9W/pJxKJMOPxw1q5axtTxE8lFEiieTVyYrHj1FTzbJ4hl0aIGrlnCCkIuv/F6Pn7yJ5k+
aX+iyRzqpjxOpowobaCPLn658f+yqLOH/tefJ7pSRUbjK9JpLJ3SzdzGZXR2PcZr9nIKfgf5/HjM
P6+gdZlHKsjjZPPYwqTqWARC4AU+sqJgyiVCo4FMaBJWBG90vQVTd2+/D03QN21ZQzyVo71rHVpv
laCnghWa3H7rzdzx01t59O/PImVzWOUSG7rbUaUAuVIhooAjyySkCLqawsHC0zUiOtSy5kQ45qBj
ePmV5zj6kEk83vECilfltcWvsP9+I7FKfTi2TmsugzfQR0yYGGGFZ+f8mUy6CfAJ/SrHHT6NOX+5
H6v3CI6dtj/CcZEMlWRM5YrLvsVAfy/CtxCey4QxLbRvXM+ieU+yWNL584KHCQOfmBVgxSR8AX7V
JnBclEgU03LwPB/LtgmkEF/4JLQEnhJgOzaqUEnE4ijS3hcyfiT1qXcaOzhOpC6+hPJVx/LxW5/h
+cW1T8WzD57CpvD9hYMmpTLrGkcwZsUGTv/sffxl7ll0drXxCueSlEpEDh/DZ87yuPPm07YfU42O
4LBz17PaqQn3uMPeglXQfttd3HLm11i4NSL+rmkqBzx5H68sP4XyLbWHy6PurNrr3bVXZr9T6eel
bdrY/36t8sGT3UGst43QT+edPDH2XmYeDJBR2P1ILEmZU3l8e/v73EiFOM9wIvGtwURJKhzJPI5k
3vZ+izl4l3qi2/hXpoI+SMIl4BUEjaMSFJ79O+39T5LVGrjgNz9m7tXX88KcATIMwdU92vs6yaZi
6I5TqyRUlciHGhkjS0RxcGWLaNSlOczg6h5Tx01lydpOjho7msfbN6MHEq/Of5EDJo+nXO5Fsio0
pxNYxT4S2OheiRcefYhUphFNFlhehSOmT+Lh+39PcPJxHHPQ/nQllrByuopIalx+67fxt/SR7ogz
VE/RNHwyb3a+yfLFr7Jpcy+Fx5eR9xvIyxB3DXx/PU3RHAOiymAEZGcQJQgol0xkTcYTIZKqEpEj
lG2BJxRUOYngvUsxfmiCfuDU6dhOlQktQ7DX9iLKFRIy5JUIUtmmdfhQVnV3k1Si2IvfIqZLVBqz
OEWbjBpHjxhUFQXFN4jaPo6sI9QACZNFr87Fd8tsWrkWWZbo7d/CqJYYcimKlIhR7rVZtsFHMyRy
I0bS3tVNTO6gXOxARiYWjxKNOHx11hF09nTy8rJ+Goc1UiwWWfna88QyMeJNUTw/hurqDGARHdFM
NQjQ4yqS7GHbNl68Vs3bCX3UjI5b9XHcMopQcAIPSZeQQoipUQo9A7i2QzKWwPJsAqdWBGNviVfL
VKu1CMQd87qcyX3cxS08v/jE7fvmrzgKVXUJArVWJeUfUBZJUt21iMQn/vxpyMNGYxTSuYIyUN4M
P765Nr3zqdMf5OGHzuDB+7+6/fhotIplxbiJrSP/X7xz7u5PX0f3gr3+k9+TFqmTJdnptBY6aZE6
6RIfXARuuJv/UYR3Ivla6dyr875bzJvpoZmeXRYxt5HA5HT++g/PWUsZ/NEmd1IE9+0oE9qaKTVY
GP2bCBTB2LLEnzzB+HwPK/pN0iJO/9K3UMOAclMTdtHFiUTQjAAjIjBMmU2uzRBlCJulDhqCKTwc
zqPRcVnSu4XB5iJ9YZFUk8Qy41VGnjAWhEpRVjCtIhyVIcAjqfVTGCzRvbyXobkGEkfB8SdN58XO
lxg8cIAB3yfXrpL8GaTyLtVoFLVNxncz9Eb6SA/N0SVcWv0hCD2kGNooioyeyuLaFXwNAjcgcKqo
qkLJd5CjCm7goSgapVKJkmcSV4YghRXCiETVeu/i8R+aH/qF3/uqcEIHyQ0obuyl6+12XAPOOecc
opE4M2eeiuM4xCMJAguuvH42f/3j/Zw4dTyBLqG2DEfJNlEo9ONVimhCRjVUHL+KrEqUiwWaslkG
7QA9YpDUQny3hKKreI5AM3Rsq0wml8V0PWKpFJVSkWw8RSALQkUC38MLfSRDQXgSlmmSzqWpeiZD
hrbguA6mVUXVNBzfIxAC27YRQqApCook41o2pucQjcWwbZtYLIZpmgS+j2FEcVwfXTUIgoAwCAj8
EEXRKJdNVEVn7h/f2Ctfaenad9b8ZAI6Glpplns4reXHTOv+G/L5O2f/+9LDoxjXvp47rfP5w4Gf
Z/7LxwC1RU+Av3kn7DbP9XciP+F2u5ZLZT9lJauCXX+2f1Q4VZvDQn8GM9SFPOcdi3lN/F/2Q98x
5P5xTmEV+1F81wjqf9LX+6PM3vihj/nFdHFk5xQ0r4i0zGfd5pXYmsnZX/13ErEcJ5/wKQI3xEgX
GfSSXD37R7z0u7s5aeooDMXDGz6RN0b7eIdKRPoVwmAd3ct7GfPZUxm4bxXRxSaZ0QkKjgW6TNrQ
iCngmyaOE2AYEXzfpi07FKscIjeEFLwCsVQElzKB7CH5GqIKWT2N6UnYrkQmnicQPtmmGCEulXIJ
NWLgBD5+GGB54PsCVVWQJAXbtvD8IpGIged7RIwI1WoV4YUYRhTP9VBVncAPCQONwE+iiQEKXshb
Y96icmP1o+WHbg6W8SWPdetXowQyQU5HM2ReXfk6X/3SOWzu62P+/FdI5yIccsiJLFi1Eg9Bc0OM
9WYZEVbZtHE5QRgQ0RRM2yKfbsAqlonqOpGkjo1FoiGO7dtUlRBZV6j6LmoyQrYxR4I0lm+DkLAU
l/iQFH3dfWiyjlkuM7y1lVJ/gYSephJ6uLqgtzKIrCt09vXjhS6u6+B6HqlUkjAI8RwPz3UQRgRD
1ZAlGVXIhI6HJmRc00K4PoZq4FRsRAihJuM6LoKQTLaB3r4CmmFsDwjaG04/9gHGKms499W7+b3z
JQbDDBuDERx4QoEXxsqIw87i6PkjmHuNwrEP/ILS+iyo6/kP8054xy2dQ7RFLPGn05trZL/CKiap
y3nWO4HvRm/iR9b3uN2+iMuiN/Nj6/KPrJjP1B5jdTCOx7xPMlZezWPeJ2mQ+oF/LRIX2C7mAGNZ
wyJmbG8PpZ3NDPuXr/H/E8MnCtoyKk/95UVareG4SRldjfFI9zyO+trJ/FG+n461b+A3j+H4IR9j
w+tP0Z0LKE80eKMnoHzqOorz2tn/F62ooUJvWCY5fgzSLS8wIjAoN0UQTpXGuIFPgCJ8wkDBVWLI
MY1sczMSHqZfJYw6CEWQjqUZ7C6SijRQKlVoaxtGd6kbkUoSd0rgmgxKFkpUxi8EeGGIL0KskkMy
lUJIgGUjHAd0DU3TkQnwvSo6HhEBwrXRLItIMoNZGURChsDHrlRRpZBMJkJfoQMjliCiWu9pvw9t
hH7WN08WZrWEG1TxgoBq1SUhy2iSgSZH0CQD4YWQdFGDKL2FMqpfpUVS6HVs1EQMT0gokkJjPs+W
/i4MXScZi6PIEsXBAWLJOGgKiqFixCP4fm2k3N7eSbVaZfToEfi+haJrhAji8TiFrl5C06djwxYa
0kmy+QYSDWn6XZPBaoV8Po9l1QxaLBWJJWL4tosq1RIGCQlUVcFQNVRZwaxUQJKQZRkhBEIIXNcl
DEGEEmEY1opfSBKeZ6NoGgESpuvh+gGvz1n3L4/QQXB97Cp+bf8fusNmLGK79H8ydTKfLv0VTfI4
XX+INcFYXvEP3Z7vIysVGBANuxx3oPIaS4Npu+yfrrzKkuCgXfYDHKv9nb+nj3/PqM8PmpHyeg5Q
39w+H78tUvajECm6L7M3I/TsHZJoHhhO8+FNKIMGVXkALRrDWF4mssQnVmxE01MoyVUUxqR4PVmm
pTPESEbxfZeRS1JU/AKOnsHINyB1VggiOkrCJi8kNhZN8vEGtKiMokskEmncwEHSAzo7+zDNKmPH
jqDiOniSgixLpKMZKt0WXqXKlo1ryaSjpFtiJHJxTBMsR2Ckk5hOFQjx+20yiSSu6+L5tYVNOQqS
DKqmoikqFdNECVRUWSMQAQjwfR9zq0ZUqza6ZhAEAs/vRdKbkBWTQTNk7cg1OHeGu7XthyboU04Z
Lg6YMh7bKhEIAZKM4ziokooeqoROrXCypxnEbI/eYgmXKFE5TjRmM1DooynfiBRI5DMNtLe3k8/l
KA9WiKgGVcvESMRQIjJaRKXsuciKRGB5qJqB53oIfGK6iqaphLoCsky5WMJzBKlUBteyiMQMAhUk
DZBCVFnDdV3KgyWMaLwm0r4PgUCVZAatIpqhkk4kcSwb27bRNA1JklBVFd/3CcMQVa2VUAsDCIKQ
atUimYoSCihUKlieTyBJvP7I2r0SnRdvP0ocXXxxj49T8fDROFydx3z/iO37W+UtdIQfhdjKPeeO
+LdrvzyAT2hP8ER6Jr5QUL+9+/Dpf0Zd0N8feyPo2s2KGCG10at0MUptwVVMzADMwSIxTcesuKTS
CSqBQUwVlNYW8bWArBaFqEeX7TM600TE9kk2Rlm/YQstqTYKVg9qTMMqCRRNJZaQUTQJxwU0Gcer
omsxXNfF9SxS8SiKJoEWoqoqTsmjVHbIZnIEjouqG6iJKINhETXwSakGgRMy4LgINUQiJPB9VFmp
la+0BIoCmUySSrmCH4ZEDRVVVQmCAM/zCENIGBqe6+P7AlmSCYMQOQaeSGP3DVL1ZLyxPuKS3dv2
QxP0OnXq1KnzwfIRLQdQp06dOnX2lLqg16lTp84+Ql3Q69SpU2cfoS7oderUqbOPUBf0OnXq1NlH
qAt6nTp16uwj1AW9Tp06dfYR6oJep06dOvsIdUGvU6dOnX2EuqDXqVOnzj5CXdDr1KlTZx+hLuh1
6tSps49QF/Q6derU2UeoC3qdOnXq7CPUBb1OnTp19hHqgl6nTp06+wh1Qa9Tp06dfYS6oNepU6fO
PkJd0OvUqVNnH6Eu6HXq1Kmzj/D/ABHHzd2r6UUmAAAAAElFTkSuQmCC
"
>
</div>

</div>

<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAX0AAACOCAYAAADdCNhSAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAIABJREFUeJzsnXeAVdW5t5+1djn7lDlnemEGGAaGoVcVFRXsYolRE00x
iTWJJtf0Yso1pphyTUz0GhNjSTXRxBRj7AWwIIqAitJnYJiB6fW03db6/jgwQjRFSCT3c55/4Oy9
yj5rnfntd7/rXe8WWmtGGWWUUUZ5ayAP9gWMMsooo4zy5jEq+qOMMsoobyFGRX+UUUYZ5S3EqOiP
Msooo7yFGBX9UUYZZZS3EKOiP8ooo4zyFmJU9EcZZZRR3kKMiv4oo4wyyluIUdEfZZRRRnkLMSr6
o4wyyihvIUZFf5RRRhnlLYR5sDounThNW5aFlBKlFJZloZQiCAJs2x4p5/s+ruti2zZhGGJZFiCQ
Uo6UzWazRKNRPM8jDEOEEGit0VojhMBxHIIgQClB4IdIQ+NEDbQOCIIAw7AIFfihQocKsIhFYhhS
oEKP6qoKtrdvRxoGvhcShiGxaBStIGJHqK6sQWVyHDJvMg888HsG+obwfYG0DULhcuj8o6itHUs2
M8zSxx8mmYjie3ksQ6J0iCFgXE0VUybUE7c0jeNqUfksiajNRd/8pdif8RXiK//RSZWmVXfxSkcl
kyt7aO1Pkfet1y03u7aDb5zxGCXvLeaWq+q4/bFZ+5z/7tkP8snjnqGtspqx537oddv46DHPsqC+
jRnnK+4+8W3Ude5k258m880PfuH/y7E9mExmI/2UMJGtrNAPvuHxHff5Sdp7MIGRkeScIZIqhYeH
p0Icy0QLjRQWeXePLpgEoYdlSQQmQgiCMMS2LHK53G7dUCilEAg0oFRBI5yog+/5oCWBp5CGIh53
CJVPEISYho1SGt/3UEqDltiRKLFohFw+Q3lFMZ2dO0GbqCBKTgRYIkLEMdHxHKJSM/7r5VT+xeCF
n7xIR88g2AG2EPihxeHzF1JbU0M6PcTy5cuIRi0MQxGGCktobOVRWTueaWMnUlaSpbaqnjBI07Kk
ixsXLd+v3y4cRNE3TXNE3JVSmKZJGIYopUYEXUqJ1hrLsjBNEyklhmEQhoowDAEQQoyUAzAMAwCt
9UhbUkosy8J1PRAhhil3lxFYVhS0RAsQ2kUIGyEMQGKYNoaU9PcPYRg2oQqIWAYhiqgp0KGPOzyM
UZpgXN0Y/vTH3xKNGruvQTKufjzD+T7KysooSaXIDPUQtyVR4VFdGsOxTebOaqKsOErMtqkuq0D6
inRvP8mogyWMN31e3ixe6agEYFNX+d8tp7TA/69J/PKjktsfn/Wa89Oru/ny5Z/n6hu/9ZpznTdc
xx9POp2mvgEeO2wJm4TAdQu/uaV1R/8LvsUoe3gfP6ecHn7GBziZBxmgeL/aEcUWmVCQjMTIBMNE
pYOrwNUuQkUI0YCJFwiUMAt/q2YEZUgCv9CGUgohIijDIpAmSit85SKEQCmFxkSFCqFslDTxvRCt
BaaQ5EKJUgJpSDwtCZUmUBYFuZEI7ZALTIRls6snRyQcjxIBfrSbZF4hkjm6zHZ01Oesz55DcEcP
f7nncYp1nJQfx/QTjJtQjZfppLq0lmislN7eIRJOjLhjYUlFWUkRsxonMy6VQEQT1JRU4oYt5D0X
MwradA9org6a6ENBsPcQBAFhGKK1JggCPM9DSonv+0QiEcIwHLH29yBlQbz3PCUUrHuxu91C21oL
tC581lpjmgamaSAEhKFGColSEq0oTLYQqBC0ISgvrQAdkE4P4IYeyg+wLAPHFIUbhPaZNa0BtGDp
4w9i2SGDgwNEIgkWLjyW1tZm0ukc48sdVLaTUpnjuPlNHHf04UjlMdjbxZTGSexoaaYolSKXzdLd
P8ykxiYsJ0Zr6443czoOiPqyfrb1lvzT5Xd+47vUpNI09xSz6PsX0DaQek2ZCWX9fGzZAGc1HrbP
cf2/V3Pn89N51+3voONzh3DZXbczkCrm7JObmfZAHel0gkQizawfr+ewB55jxxUrR+pms3FuePQT
lMu2/f+yb0EccigkZ/N7mtjE9/kYH+cHPM0RpBjkz5yBRvBxfsCLzCRLbL/60TKLbXn4mRxVlQ6i
P40p82jtI3WACkPCQGMoiWNbCAG2bRAqD2SI0IABFgGGpUDn0WgEPiBAFoxBYQosAZZjkXYzIEzi
TgQhfbwwh4mJ0gKhNSAwBGgEFpr62nqyuWE8TzHc1Y4ZQpFh0Vc9TN7IseDUxXQEW1h323qCO0NK
oykChkmkbI44cjGbd7QykHcZVyHwsq3U2IPUzK1j0ZGH4liaXTu2M2vaJHa2bMYujuEO7yDttVNX
PxXhWDyX23RAc3lQRV9rjeu6WJY1IvhQuAGYponrvnp33mPl+75PGL76OQiCkTpKKQzDwnM9Io6D
7/vYlo0TccjlclRXj6GyspK+vm52dbQjhKTQpUYpjWFIwkChNZSUljCxsYHWbc1YlsW4slp27mwj
n8tQFHfw8y7TpzTRuq2Zzl278AMNpiISjTBn1mwqS1Nk+iOUxauZVVdMmM+hxjhkhwcptgKKUynW
tG9GBD6JaDnFxVUUlVu8snMlKx9eRmtnF4GGD33j4M3PG2FmTRf2USkee89PqDvv9d0seyiKuNAQ
Y015PVd87xBueOf9nPWTd+1TZnHjNj62+BnOatz3+OkzNvG1D36Krsc8jmjpIR2N8Zc5J9PaVMvb
j97CJuCWH3+Ux+Yt4jdF76crU8U9fzqHfC7KLPF7ftXxeWZ8o5WpTS3wrtP+1cPw/x3v4+c008BG
mqhhF0UM73O+lD6msJEEaX7Fe7maqw6oP+EaWGEc4dvk+33ibhLTiKBxkaFBBInnB0hhYvgmUkLE
tHDdPMoLMAwDwzTReY0hBL7vo0KFKaIYRsGIlBQ8DSmrmGw2w7iKcYytHUdb+3YGBnsxfRMZGkgt
IVCIsGA8mmaEquJqJo6ZyvbWrQzn+7EbY/S29WAMGdQ5UaKLQkqmB7QvzbNtXQuUxqhTUfyMw/RD
DqO2ppqhnV0U1zQye8x4VHYIv7wSL5ehXMQpjSfoy7Vjhw5OvJJkyQSMkjgtz/WwYvVaugcG6T7X
hxP2f4wPmugrpUb+9X1/H7cMFJ4CDMNAaz1i0e+x8gvibuzjwtlT1837RKMxfN9nStM0bNtm165d
ZLN55sxpoKgoSXNzC2GgEQIMWfD7a3xCFSCkJGJFKCkpoqeni7a2bRhSMJzuxffyGLuXvg3LYuv2
bbi+R6KklLzlYVoBpqEoKymhLJXAmTCWifUlJE2PzW1baJo6jX6tiCaKKR8zDmfbLrb1uazbuJ2W
h59gIJNGGSY9Q4O4SpHO5t7MKXnDtN35Y876zOk811rLn9c18ditj/LES43/sN4njltBTW8XP/9N
I082j+fJ5vGvKbO4cdtrbgQAv7nwd3zL+jRvL1nJrDvqaa0Yyyfvvolze39FR1jHpu2NpNNJ7jri
LN5z/Z0szfm882ePsaatmofWTySS/jIAm7vLuOnAh+BNpYGtNDPxTekrRoZDWEUDLfyC93MBt/M8
80fO53FYxiJ2UMedvHae9hdthGgzQAlBTrlEZEgoQxQhQisMQ4JWKA3S1IRofO0R4KFNgbAEyIAw
CBBCEEqfUIdoJQlCA9uxqK+vJxqNsm3bNvJBjrETailOJVi/tZ+sN4CQYBkWaINQBYRaIZBgahLF
Bju7W2jvasb3c6jQhVBjkiBHls5Xeln38jpmz5zDtIUzyBv9tNt9FDt1hMMplC5mytQJzJosKLJ7
Wb91E42NTQwOSaKlccrGjsVs3cbG7h5e3rKZzY88Q7rfx6eXbD5C2nUJhxMHNMYH1dIv+N7EiD9/
j39+z/G9ffV7Fnl930drRsoDI4u2WmsMwySfz5NIJBgcHGTMmDGUlZWRTqeJxeLkcwFhAL4fEo3a
KB2iVYCUIFFIYWBagv6BXgYG+gncHFoHGAJiMYcwEHi7b1LDeRchJdI0MCIGdlRRV13BO899By3r
1hFTMRJSEYvEKCsvJ1qUYkdvmnseXcGuvvvpS+fIhyEZ38XPuwSehylAuR64AfVl/7y75GCw8uFi
bvzpKq64SPHMtrFU9XaxatNrBfyveWlnFeKjf98i/Mp9i1/3+HUr6gFYetjRTN26kSeWHcv4Y9t4
8k+LqXv3z7lp3Uc5+4XzOP5Td3DzU/NR6Rif3nrSa9o5acqWf3id/0nESZPmwP7Y/xku50Z6KOcu
zqOLSrbSwBTWM55WnuFwHuZEtjEBgKUs/pf3L9CEKgBlYmAQBhqkwDQNUCGGBFOK3QuzBoqQMCzU
0VoQBBrTNEEXjEq0Aq2QWEhhIIXB4MAw8VgR1VVj2JbbRrKoiHR6CInGzWZIJIvQSqG1whBgWIUF
YGEo+ga6GRoawHUzCEJM3yYaj5OVacgLEjvLSAYphrZn6JG9pKOQL+lk3GTJWeceRXZVH6FvkzBt
bNukrLKcWHGK9oFh/vjok7R39ZHOeXh+gJvLkgkkKhcQigGEjOIHGex49IDG+KCJ/t7unD3sibpB
CAKlkIZBEIYESoHWqDAEKdGBLtQnwJAGSonCXTnQCOnhODGkNJk5Yz69vb24+TS5rE9nZydSSsLQ
JxKxkVLi5bPYtomQEoRFIh4nn82RHe7Bz+cIlcYPwTJCHB0iLYNcPoMlLITUgCbjZjAdg6hhYfke
h08dx4KGFLnhIXa07aB5yw42dQ6zYstyOgfSdPUPkfcV2ayLY9vksoM4pqapdgwTxlYTsyyUgnw+
f3Am55+g9WvX8buPvptF994FzAPguelzqb3z5X9Y9w8vTN3vfsU9m/nfj19KpmoMFWYP809YwdtX
/oVL4nG4ByZ95b/oGApY4p2/T71rz3qIM2dtYFJFPy83NNFRXrnf13AwyJAg8yaIfgU9VNDDVVyN
BgYopo26A3bb/LOEWiICA9+QmDIEERZibgKNryWhrwvum0DjhSEgCULQOGgV7l6oDQvGoxYEoYFS
JkrniZgxrEicWbMOp6Ozi7yXI5Pz2NXaiYgY7DKzmOURUHny2ZC4mcRB45k5rESKvuEcHfleXOEi
TBPtRbECj4gTEMPG9fNEQou8DumPDuEGPslMjEpRTWkuZPa8YsZXTCVwXdZv2sK25u1s3tXPMxuW
0tM/TO9AlkwQksl7SAykl8GwTaaOr6NhQgN518JJ2rzS2HpAY3zQRF9KOWLNw6vWOoDaLfAFgX7V
omf3okphYVahlSAEtAoBG9NwkKZXcBdJxdNPr6CpqQnf93CiEVpbWwpPD4RIQAUBYRgQhmBoiW3H
yKUzaOUhpY2BQgFoRRAoPF8hRIjvKWzLwPc8hABLWghTQCjRrkLnXSyhCe0o9Q2zmTBpDsctgQ0t
Ldx0y61k033Eo0VUV5eTjMcpio5DBHkOmzODKZPqsU2TjVu20LLtwCb338m4L3+CS+5/nrL39KN0
YX5m3LiMQ3729/35/wou++EMvnXlIN1BMbMOPZ8bQhd/fCVr4iewtaeUmO2x6ZobaUz2oIQgMEy+
fOGVHPPTu+jsrOHzl/03627RHH/ov/1S/08jgBIG+BTf4wmO4jGO/5tlLTw+yfdwcPk572MKG4Cv
7EenEkMJAktgCoUgQKsQKTRoCFVhzU0pBVpS2GokAYEOQxCqEIhRsMcQSCzDRosQFfr4nsfTTz1F
U1MTuUwaJ2KytWcTptJUDUnyMoZQJrafIbSypC2blC4n6NUkXAc7lKS9LLnQww8FUluInEHGyJFh
mKJYEoYNinurQBkMJfvxtIUnQ0IdEvMi+EHAoY1zmDN1LrnQo6VlOzffchutg63YsTiVVSUUp4qJ
GYogzHPUzDnU1yWwnRq27NpKT3Hf/kznCAdN9Pf2x++JvAnDEMMwChE0u8uMWP8jFQvn9kw0CsJQ
YAiBYdlIIRAUfH/JZJzikgQ72jIYZojrFSKEVBiiAp9EPIoUNkIppAQdBvheHltC4LsIfAwhsEww
pY0UFmEYoJUkn/cwTRulQnw/wDEtRCjRoQEySi6XI50JWfviCyw4tIl8bggrSOOEGRbObGLCuPE4
doSJ9fXYhmDVsyuoq0gRswtPIsl4nPHj6g7K3PwzTKnq5u0f7OJeYwHPbi9c5yHf+fcLPsBwspaP
/GY+q97/I7JnHcV1Mx7h0nsXMz3Vzdf+92WyTpQbSj9Hn13Mg/efwfNl81jx9DGUlvXQ2VnDC2vn
U5zPvCnX+n+ZHdQxlkKU094LuHXsIMDkQ9wMwNVcxRf45sj5Crr3v9Pdgr7Htav26IQBBYNvt5dA
CYTYrewU1vpCAehCGbk7Gk9rgWlZmGaUMFBIIYgnIiRTMXS7i2Ur0vkcpquo7o0ipMnAWE0u4RP1
BFFlYXqCrOuTNxRZkYNIlpQSWC4Mm5CLxhBZi7hbglQGYTSgK9pB4CnG5ZswwhAnr7D9EvyMxXA2
YGvzS0yeWY/ve5ihhxXkOHLOVBoaJiIQTJrYgG0ErFz1LOMqS0glDDANHNOgvHj/wmH3cFBFv7Ax
qhCBs0fgYfc07m3h71NRoRG7N1pIDGmgNQhpYliSZKwY33XxfI9sepCtm19haLAbw4AwCAtWvRBo
FG5uGCnAMARRy8YLFBYaQ0AyHkVrm3TeJdQCaVhIA4IwQMgQIQpPK6EKsCyNYwoMrQhViOe7aKF5
fPlylj+5hjnTqnjg3t/jOA7nnXY8Lc3NzJvdyED/AJY/iI1FRVGUZCzC9pZmXlj3CqES5DzvzZ2U
N8CGzgq++dXpGFK96X23TDiOeQ3L+crO9/G9uTfym8Wn0R+fwj2LT+FX+U18/6HPMm/+SiorO5k0
aROPTj2GHY/Xc/Kuh2mouJPzW1by7VcWvunX/X+JH3IZ3VRyFVdzL4Uop4u5hfs4lYu5jQFeDbGd
zyoAVjGfv3A6RQwxmf0LK9RhQReEvVsDlEIJBciRJ/+Chb/HEHz191eI1DaQ0hjxJCghMG2DeCSB
73kEfoDvZmjesp6Bvo5CWGdo0Wdqemu6KR2WmIM2MmIgzAxmqp2tZhI1DFZeUBOPY4YWuVxAEIvg
YGNgkDGG8aMurgBbR3BcB2kEpGvWgQIjGaHTaqcqVcF9TzzJI48s5ztNn+KBe/6A40Q4722nsnXr
VmZPbWR4eAjDGyYa0VSmoqTiMda/spptO7L0eUNsquqHQ/ZreIGD7NM3TXMkEgfYvUirX3dX7as3
BIVlmfh+iCEtDFkI2yoqKiKTzmAYgtDQSBWSy2fxgzRa++RyPoZhEgQhWoApNL6bx7EsSlIlTJ82
lbbOHjp37kSHLlMnTcSyInT09LKjbReBBC/IYUcMlNZofKQhMbTGsi1sU2BpjWGFeGEGU+QpK49x
wvFH8PRTy3BzwzROGIshNI4hSCYcKssn8MLaF1j59CqkZRIrLmPG7HmMnzKH5q1bad/ZcbCmZx8m
VfSypbsMgHPnreOu1TMAeKp53D9V/8uXP8dz0+fS/o1eXtpZxXXvfZjBRBGT5uW47utNPL9jzD99
LQ+ech2rJ7+bea3HIi4ay4mT/8xpv13Ktz/9MfRzgsmT1zNx2ybMwWGsMg//jw9x4ebf8KvmtzN+
4HpuHr+OROMvKTrqP/eG+kaZzjpeZsa/tM1jWM50XuYlZvA8h3AVV+9zvphB/sKpdFBNG2OpopO5
rGEG63iU4+li/9ZMBALTMAiURrB7nU9ppBB4eX93iPWrQq+UwjB3b7rSIIREShu0wLJM4rEYuVy+
ECwSaIQMyOVdPD+NJsDzfIQYoiJtkQyLySX66TF6GX/udCoXV1PTYzFQtpnOljSeEpRXVZFUUVY/
uJq+9a3E3RL8QZ9IPAo5jeWbJFQUw7WICoPiqGQoO0x8UJNwY5DzKCoyOG7JYTy57BGy6SEa6qdj
CE1R3CFVFKO6ooQXXnyBRx56ChWxKXIqOWLRCczxi3h6zdPoqdv3f2I5iKJvGAamae4TnTMShhkW
9t3t7dbZE7ppmgYR28BAoFVIaUkZsViUwcF+DO0R+ll8L4fvZci7OaJRhz1btQI/xDQAFRRcMpZJ
RUmKGVObOOmE45g571AEihdXryGbTYM22NrSSlVFN62du+jp72NgsB/LjGNZBkoFmKaFZVqFMK+o
JOdnCYUiakmqq4oZ7GlF6IDisjImNExizeq1bNjUzMsbt3D4wiNpmj6HWYcu5omnV7JlVw9/ePQm
Jk2aRHpoiHh8/za4/Ct58hO3sXDiDsRHr2JSRe+I4P+zbL3zpyz5zWXk8kdxhncJH520mTvmP8zW
VANXnHstiw8zufoPv8Ppz3LCDe//h+09P+9SzMFerp3/HEdxOg+uW4J5fMg3v/5VFoiVPP9SjM9O
+QjXdF6NbI3TOuNo7ordz9Vjr+fQyZspPuUCLrv3F5xqfHF/h+Q/irG0Uks77+Buuqggj0Mt7bRT
C8DtXLRf7c7gZW7jQlIMjhxbxjGYBHyVL3MBP2UmL3Ea93EbF/ISM7mfJejd6byWcN9+fydpSNCg
VcG1Y1hGQQ9G/pJhj/BrQsDENA1sSyKx8ANFKllKKlVEb283UnsEfojv5/A8D9/ziDgRpAAVakI/
QbZY0G20IByft916BiuuX8aM26MsOv7tHNfwVYz5BsueeZT+zg56E90kFpWyaV4vren1TK6tpVrV
8vDNjxDJxBGhQHmKTMSh2zSwHEmk2CAbZCkSmhmVlWx4eR1KSMoqShnfMJE1a9awqXkba9at54gj
Dqdx2mxmHXYEjzz9DG09Lg/+4GZqamfgkaV7IL3fYwsHOWRzjz9/zwYr2GtBd7d1v2dzlmEY2LaN
bZoYuDgxk2wmoCyVxPc9skMDRKM2np8pWOFmSNyyCzcLTFRoIoVCiwA7YmPHHLTrItGseGI5m9a/
gunYNDY2csoJJ3LW6WexdUsrHbuGGVeTZNqMI4mmUkQiNplMmiDwQSgGh4ZIxGMMDvWw+sknSfe1
IYgUwkUra1m/uoXxE+u57957iMVSTJjYxLzDj2HZihVs2tXH7b+7liVLzuLxJ57lkMMXMhRsJbCT
ZFQWQx38fHgLJ+5g+ZaCRb/H2n8jTDzvAhKRAa486fM0nhth25cu4tnvz+Jjn6/nzxP+xOFHLmfZ
1HcAEKn+HAtmPc1Rxz6E0pJQv+reO+Wpxzh+ySkADKXGQQ6emH8ES79xEneOO5/2y6q57rrPYvc9
wvDpc3lpxUlM+tpHuPOLK7n3F6Uc8UMH+5GAzrqaf8Go/Oewg3HsYBwPcTI2LldwPQaKcexgDXOw
cbmSQooKF/t12/gWV/6NtsdyEbezjpk8xIksYhmLWM7/8Gl+xXvxiHAET7ODcZj4I4J/IOxxmwq1
J2VCQea1Ljh1EQYFwRcgCulbIhEbUFgiRIrCJs3y4hRKBWQH+4knorhuGlCYlsY0bbTes7/HRpse
XsSn6f3T2Vm0hcc++zANa5I87S+ndWua293raWqayZlnnsuJh59Ee1sbyx9fyaReiBW/F7fVpT/R
ywc/NY82v4Uw4uIpDytisbl3A3PrZ2NEhuks76VrRz+11eNoWbWFiqYx/OH+e7ESSeobJ7Noyek8
+NDDbNzZyS13/Zklpy5h6coXmDv9ELb35hg3vZrOXZvxDOeAxvigib4gROsApdVIXP4ecRdSIjBA
aKQEy5DYtklhlSeHbWly2RwxJ0Zvd3thF54I0aGLNAQYgjAU2KYFFFIsSKvQqxaQiEXJpdO4uRxO
RRlnXXAh8XiMQTfH6lXP893rvs8Pb7iJo48+nvPPv5BMPmTztp1s3tpKc3cPxp48PhggJZnBLE4i
wRFHn0KR5eP7FjG7CNwcxxx1FIEe4oILLuKGG2+jrcvlhQ2/56jFR5OsNHENBxEvxzNidPYNMpjN
UV5eTndHOxE7crCmZ4R/FE//10wo66dldzqG8aUDLP3J3dx69vvQ+UN40Yny05IcT31oBu6P6lh3
01LUu27ju5e38ZEr/ofPfOFru1sxCrsm92r38VOO40vaY6huLtdfWvAXf/3qawBoWL2WNdvncPph
D7N6fUBVaS03f+D9eJ+Du45/OzeZn+B29xymf/0yzrzUIDAMks6B5S/5T0CgiJPhaJ6gjTrWM5Vr
+QwANezkg/yEuawdKf8jPkyIwTDJ17R1BT9gE5P3OXYVXwXgSq7hm3yB9UxlgBIu58YR0d9DQCFh
3sXcwq1cst/fKTQ1hjawQ5t8aOAbHprCZ6lBiRBphAil0WhsxyBma7TnYWkD3/VIWjH6d+3AjthY
UkPoIUUeHbEws2BikLcUWvqE5ElXdXPc1QvY+OdBnBtKqchrEmPifOzMS/HtQoLFZ59cybeu/grJ
ohgnnHwsp515Dnnf4OW2djY2D9D/cpby1mqK+yOYMRsXF8sQTDGOIvKihTe5haKi8UhRRdbpZvYZ
h5PJZHnfhRdww00309g7xK2//j0LjlhIcXkdoYwRSVSRDwyy+RDfD3EsCxX4lCQPLHT3oJmShlQI
7WOikASocI8/XyG0iVYCqQWGDjHxsHEpdhSOdJEqR6pIYskcBsOY5EnFHSKGge2YGKZBxI5hmwks
GcESAlPkqCyNcMjMyfjpfvzsIIuOPoK3ve10HnvsEYaGh3ls2ZMcvXgxs2bP4KQTj6F582ou/9B5
3PiDL+MNbWXxggmcccJcJo8vJWYEmCKkKBrFMR36uwcZGM6xq6sf1wtRXogb+MQqkxSlilBEIFpO
2YTZhJFyhB0jl01jE+LmXBx8alMm7zn1SPzuzcyoLabMeHOF6ZSpW5g7dtc+x06b/vcX5OrL+vnW
mY8AsOQ9Xbx91gYAjmxo5eJdJisa5nLGXQ/inb2GppbN/OHuxxEnlJOqCnnmZfj4FUPU9DzBQw+c
ztevvoaNG/5+DP9Nl68b+X9FV2FPwOLH/5vnhuq5JH0L/dlXN674ocE7H76H21fMQZU5nL2rmJk7
NrJ5XAPzpgWvafv/Gg00k6YIgJeYxRGsoIkNNLGBXYzhaq7iaq5iA00AfIzr+QA/e922rudjPMCS
1z23dff+8/ASAAAgAElEQVQu4I9xPQDFDLymTBMbkITcyiU0sWGf3btvDEGofGToQxgjMF1cNEHe
QIdDCCNACkE0HsMyQRpp+pJbMRemiR1pUnx8lOgiMI50sY4KGBy3i/6GDvJj8gQyixBQFIkR1R5D
8Q7GnFvOkktPp/N3AUO/3UHSzzJt4XSOPe9M7nv0fiKDkicefYpFi49hzoKZLDz2cNa+tJYrPvJB
brj2qzh9O3nbnCm8+5TDGV/nEC3yQOcpcYqICovedB/ZoQj93iC+nyOn+vBz3ZRalSSTlfhYYCeo
rJuEMhOYZozscI6YGSHMZCiSATUOnH/KQuhrZlpNFN2/bT/HtsDBi94REqV3574RJnqvxRlpaExp
IHWIaQiilgVhnqQd4dz3ns/MWdOQSKRhM9A3QHvbLlq3t7Nr1y66B3oYymTI5wMCzyfve0QiNtPn
HoaUmueefQaJoqq8jMMOnQ+hYvz4sRQnizj16KMotQ0Wz5+NY8I7lvwXd9zxa1aveYHf/XobdjRB
/cRJjKmrZ3JjMdmcTyLloJSkqz0OhkQqTW44R3EqysDQIH+4/wFqJ5QzcfIk+r0hvHAQle+n1DKZ
O/NQ2p5dzZhwJ0c3FFETzSKEIgwHmDF5Jip4cyJj3n3IS/x61UzmNHZxcvAwj1181Mi54559kktn
jeNy+TUmTtzMsc89CWi+ev9izpi5kT+/1MTn/3QC//1tTe9ftnHd8iMK9e6O4tk2zmCWbXPGwhdn
sHGC4sWaGUhDseIXM1ly+Dp+8tQ8dp52DH63ZPmSI3mu7zBWb5hD05T1LFt6PInEMInEME1T1r/m
ui8b/zuKP/S/7Pyf+9k6dSoz3vcCx05u4Tft5/Czuy7mi6ct4fcXnMY5C+/hh0OnMOOOzZwT/TOf
ef9Xab57Kp897DVN/ltZxFIAFrOMpSza59wyFvGqv/q19foo5SVezTL6Rb5OiMG3uJJa2lnEMhbv
bn8Pd/BuNjN5JE3Cnv7/elF26Ujf+26WXMYiomRpoBmA9UwZOfdhfsS3+Tw2hQXxKDmO5gmeZz7v
4k6eZf82QVhuhD5rAC3zOLliBBZ528MzBIbQ2JhAHC90Ga7qoeGUaqZOnEBlrJJjxs9D2hKhJIOZ
QUKh8YLj2LhhI0HKpvWlLXgeROMxutdsY9xRE6iYX82mZ7bQ/GIbstxHFCuKzi6mLWgjNjOBWWlx
0uJjKY4VcfT8BQgRcObJJ3HHL3/Fxg2b+O0vf4chLCZMqKahcRzzxkTJeBArjqOw6Gl/BdMpoiM5
iPL7qXCraeuHu55aRmN9FZMm1ZPLaMIgJJ/uJRENaDyskc3rlpGSnRwyuZiaIpdQZcioLNMnNzJc
2rlfY7uHgyb6gSqEZwGFXNW7EWhMCU5EIoIAW4IR5rns0guZOnkiq1Y+Q12yiMrKSoQwiM+eST6d
w/cLO3yzXo5sNkvO9enrT9O2cxehhr7+ftaufYnZ0w9h1owZlJWVYZkWWmsWHnksOlQk7CjC8xlf
X0d1RQnRiMV73nUeF190IV0DAzz17HM8s/IZ2nZswYnGUVLjxOI4VoQypww3FBQn49hGSD7nk8l6
rHlxPcnSQxBhyIJ5U2gYEyN18mEM7mqmOzPI/MaJjC81qS6qwYlGSZSUMNDXT0lZOc+uWvOmzMWv
V83k9oXf5QclP6L2+Ems+59BZr10B8BumWjlUj4wUn791LM4/bheNn3wSxSvFchoFesnf493bW6h
48LjOTf4A/+98cecOfW3rF50GE8/eQyTm9ZTTjePPLyEcV/+IRuPOJuB/hzZHRtINrcx/vBuvic/
zufXfI+dFVUMtKR4N3dDDprt8ax8nRi196Rv4JnBE7jyvzZz84c/yB9/eh7mh30WWCupn9DMhHdV
8GJHDVcOXMMxG57i1+POpWHeBn75s0v47IJrgDPfjOHlXO5kKhu4jyWcyv1AQfj35q8/w6siW8Mu
fsDHR9pKkEagieCNCHgtO19T/z38ep+27uI8AJbtlT5hCoWbaQsTmEDLPvWXspgyepjKeqbyClPZ
wBTW802u5J38lklsZjHLiJOhmg7G0jZi4bfsTtXwRtFag1dw3YDGDiyihkYaIQmjCmla9Fkv48/O
seC0GSwcM4dZ/mS2P/YyJ42ZTVmyFNO0cGrihL5PNp9HVSs2653sODSLzrkMD/az46STsLWgo62d
aFWSpnObmFs5Ba8/hxGTDFqDTHzbeLYGLXjKQhq7MM2A8vJi7MYEs6YvYA6H05txWbV8LY8+tIY1
K7ZSG6/C0j5GkUJagobEdPK9bZhVw9AXEA4l2OlluH/rSkrLFjI5GMOC2dOZUF3C205YyHDndpyg
j5mNddSVOJQm60haSZKpctLDzZSVVdM3kN2vsd2D+OtUCG8WxRObNIATieC6HrZhYkhw8y6JaAQp
AhzLYExFGVdc/kF+/MMb6O7YycypTcyaOpmiZBLf80gkktSOqWXmzNmkUin6B/ooLS1jKJ0mVIJ0
1iNQguFsDqUiBKFDGIbE4/HCAOx+6YKUkrybQWgfWyoMAnJuhpdfWQ9C7l5s1nT3dtPV3cXAYD85
N8vg4CAon+KIgYeJl8vzmSs+RMOYKlp3dnHDLb/imKkTKE1GEJGQSMwg8H3i0STxSIqX161nctME
TNuid3CIwWyensEsg0Mu2VzA93/xp3/riz5++vtneJk6ln5S0puNctvNq3nkzKNJpxN4nk1RRys3
//gKrrj+tYnUMrEKXCfJgydfR3fFVN59xxn88KPrOfGhT3Posz9kOLlvKOa9p/+YlobCrs6ioXYm
LW7niIXLR85XJrtIpof4xK9+PHLMDQwi5qvptK+84PN869rCRqC+WJR7zjuTTXUTKU33M5AsZuUz
R1L1XB9/0aexVUziitP/h9/e9V4u+8h1JBJpZBhy7kN/oqO8kuMP3b8XUbyRl6h8imu5kY+QJ0qK
AUwC3scv+BkfYAErWcCz+3MJ+0UnlfyIy/5umb2fAq7mKkro40QepoqCdVlKPz4mGeL8hdN4L3eQ
IUYfpdzHqXRSRYI0wyTR+itveHwrvjlWF99RiTdkkpYZckEPMauSiAwJUnl6jXYWXDmXnY9t49sn
X8Hd3/0NA62tNMybyfip80kmiwiDEMdxGD9uHLNnzyYWi5L1FeVWlN58HxlyGOmAAWnSlfdxXI3w
DZxsiuJYFV4kTybaS87sx4hohnMuofaQUpPL9ePms2zcsIloJEI27CMXd+mO5+mUGYb6cnSv3EF0
m6bMS2LrJAalrChezTWfvoBTwmls7cxw7fU/5bjZYyhN2MSiUSIRG+0rHCeK4zise2UDTU2NiIhD
uifPcLaHjj7NkJdh7fFbuPfc1fv9EpWDJvrJ+gZtCokTtUFpbMNEhwGBH5CMW3j5YS656GL6eru5
754/4bsuYeBhmwYyyGFbNtXV1TQ0TGJiQwORSATf9ykvL6OlpZmLLr4IjSTnelRV1SGEyQ/+9+fs
6glHYv/l7rBRwzBw4lFKKitwbJOiqIVl7X6Bi+NgOTFMpTF0SCaTKYRq2gZDw4N0dXWydvUzlBWH
2NE4fV3dfPj951GditLZ1ceLW3ZwfOMEsoM9dA/1IBxJViuKiitIllTQurOfZ55/GQwBUmJH4wSY
DAzl0Nrkhhtu/DcIkyZqh3zyl5s4rqqd4xed+LqlXrjyJn71xYuJ2x6+tVfkR6iQye+xdu4FzFpx
O4Yq+MdD/fpRIHu4+7fvZsvmpr953vdtpAwxjILIf+LT1zB2qI2P3nkrV132Wa6+6TuUDPVx3g+O
5ceXreVLV31hZDHXND2CwObIhUsZGChh86apFJlDXPHJ76CEACGQKkRojW/ZHLpuNW+b8cC/TfRj
ZMgS/4dtncXvmcIGruXTfJpruZtzeDe/oZDX8dVutjCRuzh35LO/VyTOfFZxEg+9pm2JwiR8zfG9
+eucOnuLvotNBI/1TGEqG/bq29wdPgnf5At/s+39Ev1vj9WZW/MkY5UMDqUpL4uSzYMwMvTPa+eU
DxxD7cp6EoNJ7v3T3ajBDL4VQQY+sSBLJBJhTHUNExsaaJgwAduyQSuqjCJaett51yXvJYyZ9Gaz
jEvWkfTjfPfmX7N5QKC1gZQKM+IjHYm04sTtEmqdONGIRSJqYdkSQ0hsK4Jl2mBZeL5LNt9N3uzH
rw1Y7a1ne6KPMCHY9dDL1PYXsTO3kQ+/7xSOkNNRmyJ0vtJBzTSHnDtIeihLLJokmw0pSlaRKq6k
uaOLZ9euITQsbOUQiQvyYYIBd4h1J23jwdP377cLB1H0S+vrtWmajK2por1tB7GIg/JdUokiykrj
fOKTV/CNr32djo5Ospl8IQJHGoS+h2MrioqKsG0LFSpc10WjqampprGhkTFjarBtievmEEKw4NAj
ad66nTHjZ9LaUXg5ixYQqELkUM5zUVqTy/sEnovv5Qj9kCBUaGmihAkqwDYkpiFJJOJkMhm0DohH
IwihcN0eMvk8fbt2cMFZJzK5tpRUsoh7H1nKodMbGervo62jm3wAHX0DdPR2E02lEFYCZcR5ed0L
lJSmWLv2BRYuPIrSskp6unr58S0/PyBhWlDfxspt+6ZzMOpqmPCNhWz5wO/eUJtPf+pWbj7n/Rwx
oY0d1bVMadnEHzeew4r2hXTsquHKL/17k3Jd+ruf8dMz381V11zLhOZHWPT1zdz77UU4+UHe+YNH
iccLj70nrnic8oE+fr3kHAAuu+YGxqTSnHjPB/nJh+7n1rPP/7eJfjndnMRD3MF796dpxrON7dSP
fL6IWzEJKGaAKH87Ad+te8XjKyQ7d8fp/zUXcSu3cfHI5ySDDO21u3YRS0dcTbdxIRdxO9sYj7H7
5vEL3rfPDefvsT+iP/lzc3X5bJv49BRPvOdFGvrH01zZzBGXNDFp0lhOqz2Rb3/pGtqe7WTQh3Qc
bFcSy0HMHiaZTGIbJioI8V0XKSTVVVU0TGugqrqSYhkhP5DBjCaYffgC1rdsZ3z9TDq2uww4MGjn
CI0MTqARQxa4DmkyuH4Oz80RhAHaD5HCRiuDIIhgizgJM05ECmRE0et24ifyFJUI8vnNdDZBrqKX
uRXlnJ05lFn9Dfxs9W+YN+tQvMEsrdvbUCF09AzQ0ZshUVKBsONooVjzynqqkuW89MrTzJl/PImK
OKuOXsfyM578v/e6RMe2SMRiHHboITzQuROLADsa4dSTj8e2NF/83GfoHxjC9RXCtFAh5PwQKU2E
bRAIE0NaWBELK1EEWtMzmKbjmWeRhsCOGKQSUSorStnWsp3e3mFC8SRDnolhmpi2TSyRIFYUx4lG
sUwboW1sw8QxTSKOhWlHUcJCmpFCzh0RYiDIunlCIdHaIO2GhRczmCnygUFx2QTWvtRC0jDo3NXL
5IapbOjdxcpVz1NXMxnflWxpyzBn3pEsXf44k6YUY0oDHfokHIPqsgTFjkRk+4ly4NE7x2+uZKUF
kyt7iZgBR3+il+YkPPAGBf+4yS0c+d2L4bvwM+rRCG46bxsVk+/nqiV3w6PNhO/aNxjsnsWn8OGj
Vr1ue4OJJJvqJ/1Tfc/Z8BJ9qWJaa8YyZ+M65s1fCfOLuP++M3EnxvjDYRfxYPw4AM6/9y7uPeYk
PvWLV7Plf6n/HXxx2uM0VfZy69nn/61uDpj5rKKajv0WfGAfwQf2Eei/xXi20cZYAE7gYSK4zOXV
9aC/cPo+7dXTMpIeeW/BB9jJGPoooZkGLuJ20sT5GRdwDMvYwVh8bL7AN7iGf8/mtoExvaQqUkR7
qikzKtk5bxNzvzCJyV2TqF1ewbd+/316gmF806fENyjvNciIkLyRx49GcA2TwDCIJxIYGggVHcNp
Wp56CksKbCtKcXEZZcUlrG7fRnf/AAF/Ysh1icgakrKSMitBImZCzCaMRUAYWLaF41hYVgLTiezW
ihhS5sgFQ4SRDFnlk8/6xGyHoqEoQY/GjTdR9mgWpUPWLuhh87S1nOANMXZGE+098OyT6xlXV0M2
l6ale5hp8w7loSeeorGxkYQlCbSHFTeIFkkipSHpWDckXxs99UY4eHH6yiQeT+J7PrZtUVFSxKc+
cQW333YzG17ZxGA6i8LGCyEZTzJ31gxS8Sgvrl1FJjtcyLmjIAgU/YNDODEHISQ1JUUEIoIrTPoH
ejC9HezM5UibCQIZo7qsEqTBwFAfg5kO3O1pQk8ReqKQLVLoQoo+UdgMYjtRDGlh2zaOHcUyTQzb
wrIsIk6UaDSKNgRWNMJAfwfrX3iOoqjF3Q8JlDKwI3ECkSYaibCoqJ5Uoog161YzZVo9JnksHaA9
n4a6sVRXllJXWcWurh6cWCk96QNLCvbZE55CisLCWu0ChfrU2bR/8S4eeGrfcpcf/RzfOeth4rb/
N+PyH9v06sLcnkf7y+7cLSZfA5hBVVGa/17y6oLk6Y8/yJmXvf7bqc6YsZG6khdec/zZGfM4smEH
x0zaztiSoZHjC9espOY9l2PKkEsXfnWfOnf8oYyy3UsDd/6olpf8En64/BD4SOHYWe/fyWODixn7
oySfuunbXH3Z55i5+RX+VZkLSujj7fyR+ziV5w8kKcp+sveN4hFe31W3N9v+ziLrZiazeXe8/t43
i+UsYvbumP8HOOU19Q7hOdYwl/AAJcVstElvyJKaY1H6WajqreMS7+089PP7ePi5P+Ol8+QjIWkd
MK6onMkLZ2IXR9i28lnSKkSFGilMfFczNDCEZVkIoLS8AltHMUKLdEcXZPtIhy6hTBH4krE1NeS0
pCfdxqD2UDszuIEm5ytsBSEBoSFQ0kRpg5hdhCUiYAqceATTNpBCE4tECqIfiWEYFoaK0T6wkxe3
LiW+yaGj9DnWilISfQPYYQWRwOGE4lJqSqp58flHmDRpFuQ9LOWj8jB+fCOReov50+ezOd5K+1FZ
Wko2HtgYH1DtA+Ccs8+juqoC383wnf9H3XuHW1Gd79+f6TO7l9MPh14OvQhWBETsLdhiiRo1mmgs
MRqN3xhLjImJJjGWGDWWRE009oZYUFREAQWR3uEcTi+7t6nvHxtRAqKi+fnmvi4u9uxZM2ftNXs/
s+ZZ93Pfv7uFxYvmc9NvbqKnqw1BkBDlssyCoslE4yFi8Qghv152wRFkEokUkWgUTZGxbJu+VbV0
d/dgCg6i4qKKHpWVMY6bMpFiJkVRDFDRfyjrW1rp7M6j6gEUjXL1rqdglQQQwXJMSqUStm3iui7p
dJZlHy+nHOo8CoUiiqYSCcdo7+pCVTVi8SimXUITPYIBH/U1NaxfvwnLtnAyLp7oIIkez70wl5qq
KgYOGUM43oeBQ0djeS62nScUDdPVncR1HGrrGwiGo6xctzNN8cviwbfXM7/2MKrfX0bV5Vdz0oFX
c+Nxs2lL7fzYf9SotST6VHDDtDPgol2f75JpC7h97j74VJO8qTCsuof7T3uelT+bxsctVSx9/VjO
OOtvHDq/jbX9B7Ng1ARKms41j5v0bdvRj3bELXO3v75u1jTmrBn46c534EP6c8d/zHg/wdxL/87k
P+0sLaDKNucfvpSx4QzyEXnaZpaDX1VPFwtH78Xgpo2cMvt1bvjRlRgfm5w2/yzem7n7Mfw8ROkl
QLkU/hwe5AHO3mO5g93hWJ7jJY7CoMBJPMFyRrGI/8c8089gKeMAOIqX6KKSZj7VXvpgG0XTIM8p
PLbH4zHavx9hoZZOo4Opxx1K/PdB7r70YVqyCSTPQJZLqI6IIetE/FGqYtXIIZmNJchZZUG1SEQD
RGzboU+fvnR1dWMLLrLkoIsyfavjHDp9IsViFsvxEa/pz8bOTrYm8vhDMTTRRbCKeCiUXAlThKJd
pGTm8WwL0XIopDKs/mg5Dg5J2SNXKIGsEqmopLMniaxpVARi6JLDxkkt6DcJFHJptMUCiRdKaBsH
U4x3IKhFXpw1j8qKKvqOG0c+WGLAfhEy9gbShoIyKELRaCZdBYWtIuM7hmCmRPjyclU74VsL+uPG
TKRk5kklXG7+7a3k8z20t7ZglSx8fpVINMaQIcNYv3EzY8eOJRqNYWgqkubHLlogK7hCeaFWkhTw
QJcVfD6BQiHPQVOmMHlUI2HHhGIBSfEz6bAjeGre+yxdtglXLN9AHLcEjozkeaB4qJ5Snr1vW+sQ
RRlVUzBLOQRRQFEhEgkwfvxoWtrKjAZFURHsIq5dYt99JlJfX89DDz9Gd08GyxGpiNWSSqXIFUV6
EibdvZ0suvUv1NZEGTlyMLV1Few1ZgIjG0fxz0cfZv78dxkyfBDZXNvuhnC3+Ev2QpY+sRdXXPUr
uqc/yYV/GLvD/v6xJB//392ErriansvGcs/gIcTyeWDXrjwD4olt/yd57/L7uerk3zL9kXVM3zqb
2bOOQy1lGD1mERVvjWXxiB3/VlPtjmsKTX8sp1imL3ibird2pp+V/nwjli3hegJB/VNhtIeO+S7P
VZ/DmuAdDPvVxTscYzoyd788HsfdC/4JWsAl9Yff8evzL2fx/Em4B/+Z9YVL+U0wwJ0b1vH9zuVs
e0T5ypjEIiawGIDfcPWXznF/WezHfA5mDhLuDhW1W/nvS21fxw1faJhyI9duf703C5jOG2iY/JHL
KKHx6NdIb/mrPUS9QI+1loXX/BPteRWfF8XWSnS7XTQG6hg5cCRLt2xh/LhJVMQqsVUwfFG8tAmi
h4eIaTlIsgIIKIqCX5dx8jmmHDCRA8eNwi9Y5JK9qHKA/Y45nqfffgdr2QYENYBnWpQF2mVsRyAk
q/gUA9sIlfX6vQJJxcEO2liehSBKSLJELBxj9KhxtLd34QkihiCjppN4ahVhRaaxTwNz5i6hVUxS
iik4tRaW5WA7GVJZkw9bMzy15HWmnD8FR7fIbuji+PhUTqm+gj88+E/al69FGNZK4tCd6blfBd9a
0F/0/gJsu8g777xJsZTBtbMYRgBVLWHoAeqr+1ERraHDSFEZqUZRNCRZx3F1HAQi8TiGpiFLErFw
CNlzGTpwAAOq/Bw+fQp2Pk11xA8liZJUVsK0rDSuWUDyXFRJwxa2GaMgIAoSnmThIeA65S+LIIDf
XxZXs22QJG97CkhRJBRVoqzx7aJJMsFwgIsuvJBsrsBDDz9O0XJBMpA1hUAohGH4CIaC+P06um8Y
+UwvH65cRXJeB+/MW4hnQU08hs/no7u7lUMOOXCPx/cXfW/kgyPG83hVhn7B8qz0E3kEgPU33kEq
GCJiFFg7pPw474k7rw35VZMRtV38evYUmu/+G3879HuEHi4RfCKFaWrMnlXmuptauTL0kPfn7hT0
Pw9v7DMFdiHBq0ouqrRzYdq6kxdQWruQB18/DX5VvhFlfX4C+RyJUISma/5IsJBjXngUdRu2snJj
jF8LKt6dx/PT/Q7lj3f9lsv+EsF5SWLxsV/s5ft5MFE/V6/m83A0L/Aix+y2TYQEl3I7BXQkdl2Y
dzCvs5C9dyml8HVQRQcX8NevfNxC9mEh++zwXoQEPvaMS74wu5g6uY4RW/ox8cA4rYNKzH16FTF8
IItE5RiVsUp8vWn8VVE8VcQRJYqigaIZGIaAz+9DV1SESBhRcGkcPIgB1QEOP+hAnEKWmlgAu5DD
8RvoigrkkMSy1r4oKEiqBKKA7QmotkDQdnBdEQsFW5axJB+qHxw9gmnmt8m7W2DKBAQdvyMgCg6e
5FCKh4gXda6afCEUVToOf5yKqUmqAyXiZn9ymkgqZJKTSuQWrqN2VQX529IUmtIUizaLYu/wQvYh
AhP6EBAtnIzIIGvPv7vwLQb93u5WgiE/B+y/N6GQD0GwKRZzmFYBFQNsCIVCJCuSaIKGJGjgqvQf
2Ehrh4MqyhTzWfrW1RHyGSgCjBk9mpggUmjvJuQT0SSFjCaSRaajcytDNYmA34djuwgKdHR1g2ih
KDKyqOO6RTTVKAsyuWUZ57JUq4fPp2KaxbJPrmMhimWzBgERSSqrf3b2Jvj+D86juXkrsXgNe0/a
B1fU8QclWlta6OlN0bK2Cc0wUFQRWRMp5k1QIoRi9aS72xkxegRXXnUJpplmxcqPvnggPwelNSUa
jbVc9355e/XAoUxYuYjGzesAWOwbw/PTjuDCjWthWw43b/iYdcGjHHn36Txz3mPMvO8UUn+6meaa
ev69bhwnDfwXg4U1nHjyIyQSMea8diQAQ4etZMP6IVR2r+blyccC0LdtK77Czj/81QOH7vTel8F9
707gsP26mbrgbI47ezXenXcC8KfJZ9J4z3xa0wFC516xy2N7whH+eMKrzDGn886Zb1DQoyw//VAO
O2GPusJcDtrt/mGsZg2N6BQoYlBJJ+vY/Q91GKs5hccBdmLpbGAgg7ZVxc5hxp51+gvQSfXXtkQc
wtrtBWEdVAF//srnqF3fh8Z3poLbSynaTjQqMeT4AmqvyJBRwxE+aiPS66O6Ty2O7oFoI6kadYMH
ImwtoEjluFDXUIdf05AFGDd6NHWKhtnVi+4TcDwXW/Vh+kS2dG2lUXTRZQW2ibr1dCeQBQsUCU/W
SMpFdCWI4KiIpozhahiFDBHTR9F0ME2LcKAKK2chCgq2IuIoHp7koHhFCkKRC8+5CHmpTEVsKH2r
G8HupRg2ae3ooCeRItGbQldUDEWkKOfJF2xSjohcWUGFkaRf4wD+eNsvMM0Obko+/LWu07cW9N94
4/ltzjgOmqbiui6Ktq1QwfOY/dxzfLhoARVBlYJpkzctjKCKIoPguVhmHgmHbKKbSn89xx9zNIok
4lgCXZvXUlNTxUOPPcmqjl5SpoNPEzj8+FNQVAPbEXBtj8VLl2J5Wfx+H/lsDl2TaegzkL4Ng5FE
tawBIgjbK9QVRUEQRMoFxCKiIAMyrgeJgomgqGzetA7PdSiYRdZvWk+h5KApNiBQKDlIkoLnSsiq
n0w+hyCEqK9tIBSrYuyYRn5+5UV4VgFfMMaiBcvZf8qeje93T9jVgZO2/YMr9dt5/+XpTPmc3/nM
+2uXkpMAACAASURBVMql+5LnMbd2ClctexTeA9NU8QeydHxUzyldP6Bx03rOkZZw75UXwC8/PX76
wrcZddLpXDnjXVZ3VDCippvrZ03j9+lu0sHdz1KXNNcwvmFHL4HzDli8fZF53oa+3DBr6nbz9MpA
FV3ZXXPirz3iLZYOHcWaVSNo/9kjCIBRTOD9aPxu+/B1cAqP4yDyEkexhAl0UcXBzGHNZ2QMPsEI
VnAks/BvmxnPZep2mYZPKmc1ivyc3/3X+vtNYBxLOI7nt2/vqfZO7/JlPPPvxQS9Coq+ViI5GTfi
gBKi8rJarrroFJxXMsjNWyk4Wcil0TUdURSQBHCtIorgkexsp2bwIE74zrEUcln8jkpb20bC9ZU8
8MSzbGnpIWc6SDocduJpSIKCa4GgiCxevATPzaEFDXpyGZSgTN+6QQyobUTVZByviK1nMbUubDGD
K7nYsoAcCmIrUFRkSoqEKNgELZU22aGzI0tlKoDP82jqWUWL3kRUlhEKAnJRJlwQUDxQ/SLdVhe6
YjCgehRKrJbJEwcz89JTKToaqlHHktnr4csR33aJby3ojx03BBBxXMhmc2QzeRTdwO8PYLgZXKub
SXsNZuL4wXT1Jlm4ZCVtPWl0zUaWPUqlEmFd55gjD2Xi6FHcf/fdtDY3Q1UDbjHBT35wOotWriYj
hhG0EOGAjmUpeJQleyVJQVRkHMtD9Suk8xa6EcC2LRzHwbYsZFlElsta3QIqsixh2y6uJ5UXm0UF
PBHT9ZD8IQrZBDnLRvRskpk0suJDkhXCgSDhUJRYZT2+YAUbtrQSr6wik89j6BF0zUc44nDZT39I
0UwRCvhJ9WRYtXzjHo/vUz94fPvrLb1hfvr04Xx/3yUcM6qcTvn4bwmGnPFLpK3vM+vGp5ly+TIM
o7iD4NqdJ7/E0NhKQs+sYNj6a6nvauPqnjlMb9zM3rmFBJZ0cP38aZyy13Jk0eU/yeuy6HLDUW/x
7NJhLG2p4ZjRa7Dl6i/se9RX2O3+npxve8D/5eFv8auj55LXdK7qfz4HPf4qxZ+P4Ni3ZvPs9CNJ
BAfxZryK7CGPEE5/+uRxa9dVwHe+sC97CgmXY3mBY3mBVTTyGKfu1GYkyzmRp/gtP99BsXIab+0g
laD/x8zfIE+B//deC/9ZQ/BZfDbgA3u84BwaEKX/xABaMcS6kkoop6MWCxAXKUidhFSHxsZG+u29
D23JZtYuWMDWnhIBRUGXBUqmRdCvc9J3jmHsiOHcdcftpJI9KFoVBTvB+T8+kw/XrcUs+dG1CBFV
wypJKLKGbZUN2CVJpmQ7aJoEGYs6N4wv7SDES2Q1k1w4T1uwjY0D28qSlRYkiyb+dBFHtTAcGZ8l
4QkeXU4B1WdQKBWw/BpNpW4EQSdiyASkEOE+FVRU1xIIVbJuUyuxinqqsjZBPYhuqEgDBCb9dAZ5
rY0uz6XFTZHQm/dobD/Bt6e9Y3s09O2DJKokk5nt1oOiCHa2bJcmiAqqoqGZFjVVYWZMn8zsV15h
0bzZxGNV5BJpNA9KmTTt3T30uAIjohXkcxJ516Cqz2C6NjWDK1AI+Ch4BqIexhXAsosUMyVKFqRF
i0JOICVK+HwKoixjWgUUCYpmD4MG1WAVS2TTOVLpLAICkgiKCK4gIpoWpUIasFE0Hc8Dy1MQBQPP
UQgaARqqa0hk83hCjni8Bk/0E4xWoCsBZNclGhB4+G//YP2q96mvqaOtI8GWLXvunHX8uNU7bF82
fcEO2++EGuiztZz7sRf14K1N037MO8x5fgb8XzmXf9G/j4IRw+k7XKfpluUkgmFmnLIJF4GOWCX9
42W+8MF3nMl517IT8qbC4OsvJmcq/Gjyh8xZM4AD7fQObW47cTa/PuYNAIbccAkAv6k7jXtLd+/Q
LlnQ0GWLoq3s8P6AbX3QzRLXtz/MR+ePoijA7865dId2rY9ewS8/uJTbTz2Pi59+AGfpVj5HVPIb
x3BWcx030EuUO7hk+/sVdAMQJkXXbpymMtuUND/BtxHwdQq0sWsvgunM4QlO/Nz9XwVZy2JgpIK4
rw+6FcTN+sArIkpFPLmEVZTIBf0Ew2AWDaJ1tUyZOoRXXpvHrfNeJFoZoTfZA55LNp2lsydF3oVh
/SpRsgqWpVNdM4B165rwhDxyXkGwghhiGEEWEEoWXr6I5eRoTwukXRXbNigVFBzXpjXSgrG/TnZZ
J5P77UVdopKmziaSjVn6Hj2UzcV1rJu9kf5d/YkUYgiBInqPh6+g4ogiOTlLUJYhL+OL+4jUhEib
acyiQri2gqKl449VoGkeAVHC9Dlc9bdLaViRx+lTRcepNm3i/yhPf9WqddTV9UdSJVTFh22biIKI
KHjE43WsXN1BXX0d5557GhXxKKJjcedttzJp1CiCho4iiZiOSygQQFNk+g4aQJ0vRkSSGXnAPiRT
OQ4+7FA+/PPtiK7Llq1bueb6mxg6ZAjZUpGqUJwjjzoay3GQVQnbNXFLLrlMGgmXmF/hvPPOAjtP
LB7B0HUQJUpFm95kluaWdl6b8xZLl65AcEH0ZGxBJGBEyRcsBg4YRjBYiaGHePDua3nzzTdZvmoD
qEE2tyfozVgIkorhN/BL0LxlJd1iL5qo8NSTT1HXdxCevOfK18JF12HefROKU5ZIsB2Rkl22pfSp
Fo+c/zq3vTmG7334c7xDz4N5cH0zfO85D7ief5z5DGf8YyaWYiLLNqW//oaXphzCHVU/4Ip77+Dq
y3/JO85UeAFakiGuV6Dz0fh2nceHjjuN/3NtoKz9bbM/PwXS2xYgT7vsD/zzryJ/KVmIXrke4RMJ
gJeevYvz/nwrf3r5OlTFRLUtIkaJ8Q3tvLepAe/OcjtHFPnVs/346fd/jd//+TUNB344n5GDIljp
Cm5orONnfxD514fDvobq++5hbtOW/6xEwXXcQIzE57YFqKadc3gAE2W7hj2Ai8QNXMd05gBlHf3d
G5Z427XwPw9vMo332O8LmUeflWUwUXb4TAIu+/I+b1DWU9IoUuLrGXwUWgsoqg9HEAkIMlnBxpQ8
dE/BZ/jZ0pQhbCic+Z2ZVPoqKYouf/399UwcPZKgoaFIIgXHJOA3MHSNwcOGYSoyEcPP5P33JZPM
ceiMQ1mx8i4KZg+m63LFjdfSOGws3SUdf63MjGOnE/dEMsh05WR0PctiFrD+SIcKL8wvR/wAX51B
RVWIkp4FTcG2BLp7elm5dSOzxr6O0len20uwaM17eI5IybEoeQnUOomiKhMJxbj2smt4f+O7LNuw
Hg+b7s4WktktyLIfT80Q8AdY393M8D45okuDvPP4GvqNHEuf9Nfga/ItBn3LcgARy3RRFIXm5mYS
yW6i0RANdQOYO28FgrACxwugKmGiMY1cJk8i0cuBBx5AIFxByO9nzfo1LF26EMs2adqymRbTYvGS
hUQrYkQrKxBFSKVTBIMxPEGgvSuJi0xvOksmm0dWRDzBI5NJEpBkDEVi06p1mPk0TygONRURhg8d
RHWfOipr6xBdqIz4iIeGMGLQIHL5AulMgVXrtrK1pYWunl5sVwHZoLsnj8+I8MrcRWSyJq5i0JNM
o2kGUVHHQ0GRIZXqYu3mdQzrHyUSi5BxPUR/kPHDvxwL5vPwScAH+NXLU7hx9lTmX34/k/q18KNb
HkLccCTnn/VpxeyGxsOp79PE/CfuY0V8BLf8ph3BOp+FW+r58Klqlr+QZW1nNxO6fsyP+r/AhuLJ
QMX24yPpT631vv/cP5mzz1RsSeKkV59jS20DVb1dzJ48g9G3vsEDv/0FY09Ywc/X3MLkOy6jcenT
24896qUfw0tw67bt+8+dz4zrPmLYsXBwQzO//Axz5tUBR9HyWAM+X47vnrrrBa71f7dZPH0AK04b
AafDMXN+xFU3Lt9l228CD3I27buY9bZRA3hU04GFwltM2yGN00HNbrVsPgmulXTRye7SZAL3cw6H
8ioRkgTZ2V7vIOZy0GekmHuJ8gwzmcBiEkS3q2S2U42FwlLGkiRCLa20bSOJ19PCe+y/07k1ikzh
beD63fRx15BMGVnWKJZMisUiba0ZujKdVIZDVGbreem191mUaMVxDUQxQGVFiGLWIZvOM3XyAfhi
IQIBg3WrV7Fy8cd4ts3m5s2oosqSDz8gVhEjVlmB7VkUSi6WJ2IpBuuzKSw1TTFl0tSr0uUayPE8
q0tvkxmtU10XJfnSAlqWF3lx7wCDtP4MGzmM0JAKKmsDCKaHnxj1A+JMHT6Jtakmso7JEYEZrF27
nuwkG8uSUdQgvT05fEKElkUljI4G+veESCTyBBwJ25XAk5GKYFsia1cncIdoyJVRmgIr8PsLrK/d
9MUDuRt8i3r6ErYLogiO7VIomXT19JIrFIhE+oDix/VcZMPPuL0moHgFXn19Nk1b1pOzHNZtXoKi
qPglF9mz8EcraOhbhVgqUShkUQ0VWVUJhEPIuksub4EgI2t+8qUM0aAPy7OwLAvDMLAtDZ8hsnTx
B6R6OpFci6efbmbyvpPoam9FUETiFTFGjBhFRWU18aoazFyBeDBMZThA2Oenq6GSfMkiU7Bp7cqg
yZ2kMiWWfLQayzERZR3HVvCQ0SUFy3awiiUc12No4xg0xSSRzVNwwgwYujepwjenpz+4sheA/f9w
Lslbbt7+/sRD0txxyg/ojFcSs6oYY93Lm51DKT3dS1vC5saj55Z1GQfAfgPKRVaLRoyjZmUX+wY2
4p+8GYB75k3kVz/6GWPWlo1NHjruNI6ZO5uCrrOpvh9trfXMa6nlspMGAOfS+EgH3pku18z4FS0f
DcN0rkH+8Uss/nBvJn5wD5/Fuffvz/L3T2bzgINYRl+kmMTga0UGDtrAoYe/9IWf3b12GLUVBtMW
zePXTOeAlwKUln+z3PrPopIuxrKUdziQ4ayihXo+YC/e5CBAoIOar3X+XQX8Sjp3SBFtpYHXmcFo
ltFODTW0M5EPP/ecMRKcywPbt1/ERw3tbKXPdunkdmpIEWY8i1nChO3SD5/Aofwk2Y8trN7FovWX
gSO5FIol/GoQ1xMpliw6exJYuTxhtw+i7kcyfKi+IJP22QdLdpn9ymy2NrdRsIus/WgjqiISkGQE
G3yRKI2NjZhFi2I+h6qrSJpKMBJGLrqUSg6KY1PhePRkIFIRIxsFqyTTGU6gfEejbovI8tuWYG8A
SbB5NPkQ++09iZb8FrT5UNO3lgFDRxKvqScUjyElc0wwGhDw6K6uYaI8iHTewsagsyfLmlwTuazJ
h6+vxnY9RFFFccNogobjCLieiFry6M11s3e/0fR3VOjpoT4zioGLxqHvqT/NNnxrQX/i3vuAIOG4
ZfmDYDhGtW2jKCLpfJaSa+F5FgdOn8IHHy9EF0qEDQGrlCdrCQRCUTRDJ6h4lNJJSpZLzsoiWDaZ
TJpid5F8sYgs6/hkCc0QqaisRlF82FYC0yySz6bAc/FrIqNHDuOxpx6lo72FQjaDJgmk8gJPvPQy
iixSX13JqBHD6e5JIgoSqqIwbtx4KioqGDh0KH6tiOV3GDa0L8lsEXV9Ez6tgraOBMmMhyobOA5Y
noeiGBRNC58WwBM88rKELEZw7RJGRGXv/XxkS2EymT03QF7+i7t22M6WVO46eccAuXJQI1wH+1zw
JOcM3YxftdguynjA5597r+UfceETZbrmvA19WdFWReFPv+Ymrtze5tD5b+AJAnqpxIW5v3D0m7dz
w98+pWuu7qhk9S2VcEt5e7+LTA7+6+GMBxyuJv9QE28/uX951g8EM60c/WJZFviG6z0WPgJ7TSyv
SUyfMRtB8NiyZSBDhuxcot5RUQ6ScydN5vmP32PhHrs6fTksYwzLGIOP3HZZhs9KGnxdREiQpFxz
Eaebo3mRv/P9ndo10Y8m+gFlmYRFTMRCIUGUo77AuPxoXmLRtr4PZzXrGUQtbdRSXuj/JO1zP+ds
D/6H8BovcyRr+Xwl1S+Cb2AYuVmjWLJwPfAHw9R4dRiAg4MtOBSsEgdMO4APPliMrbjUqCZm0SNj
2vhDIQxdJaholLIFPEEklcljFkpksmksx6JolpBkHX9AQveJ1FU2oFgKipjFKxbJWGnajl5HcKDA
Xm9O4N37X8TtyNNtlxAVkewWj+da5/Oi8iYDKioYP2wc/Vtb8SlRJEFi3KThhCs0Bg0fRtgI4/gF
Rg0fTFcqhyRvRdF0epMZOrtymKaLiEQmW0BVfZQsG1XVURUPJZojLAlEsypmhcLEvcII3SJe7utN
Br81lc3jv3uaJ8sqAjLZbB7XdTEMhY2b1tPa1s7pZ5wJAkiCy+uvPE+fqgjRgIZjFXBsiUTexBU9
zGwCz8xj2QKWHCgLozk2nuCSy+eJROM4tkAmW+Sg6YejyH6SqS7q6yp45ul/c8IJM8lmMixYuID1
Lc3YJQvPs5FEsVxyLQioioxsO1TFI1hWicp4nMbGYYweNYp0sodYJMpee41m9NixNLW0EAxHyORt
AsE4nqhRKuokE3la2zro7i0XXTS3dJDPl7BcF08SkRQVzxUw/H4sGwpFE9NyePD2H+6Rml7Pw1Ev
nt55weeifx/BXW/vzTXep5Wud/ocErf8fqe2333gBLYmyzn4tlRwh+KuzyKolRhZ18nbV/6DZ6cf
STCXZUjTBk67dAYj7QUkxu3Fsy/1/1L93n9gE6eduRnrkiH0ROM0N/Wl9EYPybvb6a4cwaGv/BSA
VLgvFT1lJlJL3SQevGA+tXUtbG3uxzXXfX6K5BM0blzL6QOf/K/r6f83cTYP8DozdpBD+DJooIkZ
vM4LHINBgXN48Csd/3fO3D6r3xWK6EzkA2Z5C7/y+I77537eoFkD8UwV18tgmzqu5tGxZTOh78ep
7YnT3xyG5XTy1qw5ROsrqTM8zJKA6XokthEq7Ewet2hRtF1KmozkCniuiyd6ZPN5wpEoliOSyhSY
dvDRSLIfszeBNqFA0/TlGE0Gw94ZydtvzaZ1Y4oeIYPkuMhEKLgGAddFMrLYBZd+NXXkxVaCMZUR
w/syYcR+5NoFqsJ1jJrYwMjRo2lp78QfilJyXfyBMIqu053x6Epk6Gzvpqs3STZv0tLaSbFg4po6
qBqua+L3wpgVHuR9JIRONu49nwVH/+t/T1r5uO+e5gnIiKKCbTnbnHJc8oU0H324hDPOOAtRVhEE
ED0X28zjFHP0tG9l7eqPcTQfuUIeXXLQRZdszsSWgqQySTRNIRQKkMvnMXxB8CQsEw479CgCgQCt
rZuJRgx++KOz+fEFP2Tj+o2IgkAibYEg4HgerusgCiIuHp7noctgFgvU1lQS8Blk0klUWSTo9zH5
gP2ojkWxXZNgKMCUqVMZMHAoiuJHC0YoJNO0tLSTK5RQ9SCWJ1O0XBKJLFvbu+hNF+hJpCmZIGoB
FNXANG3y+Tz33PKDPbu4dwm7vLB5U8b/01/sEPRVs6zmGSjkGfmLVznmr6diOl/9IfAGM8vwTes4
du5sbj77Euy2PH8aEiZnqqiS/ZXPqQY81j10P/edcCYAimVx03XXcvVvd+b533C9x89/U2a5PH3C
P9k06jAEwePKq2/YqS2A6DjcIP3ufzLoC7hcxe/4A5d/oxIQn1BIvyxcBFxEXuVQljKWH3MXQTII
wEIm7VHQH/nwvt7Qlwfh2RqQoVTUEHwi+e5uhJkaDclqIp31qMECiqWQcS2UfBedbb2s27QaNJF8
PovmgewKJAsFTEXGKzrIooBqqKTSGaKxCmzKceHgYw5B8Bs0V3XDfp1cP/RsfjflWj5u30SPqCOl
U3ieQo8uggDhgovnCciWiqd6ZOw0fauiVAV99PZ2ouoqqs/HlCnTqJMNisUi0ViUg6ZPZ/ioUeC6
CKEgpWyR5tZOsnkT1QjhigqFkktPb5rNrUmyWYVMR4K0Z+HFIwh5jUywlc0j32PO4ff970krL1my
hGFDG/H7yj/UbDaDgEcqnSAajuKYLoqq0tXTRSadIptK0reuBj1QSTZvoks6qWQSx5AJREPg2dil
An5DRpUlIuEggiBgWTaW7SCg4FgFMAVqK8MceeQhnHrSiSTTCXKFPGbRQcBX5t97LrgSSOWCD08Q
yeRyBAIGkqqTKdmI/hiu5yAZOm+8+TZmLke//g1MmjSBJ594BteBmupajjt2JsGQSiwiMXBQP3LZ
AggqrR3dhOsNqisasFDIFF02bO5ga0svebNATVUV7e2fr5/+RRAuuo6FP7uPSf3KOh2ZokpX1sdp
D51Av1gSttH+Ehth5htzmFr4mBsu/jmTBzVhOjJVwSydmcAuz/2JDg/sKO1QFHVKiso1yydzZ+Mg
ihs/pZzuyU1k5eV30O/EMsXx2iPmolw7kJuuvArh5xeQDEVYfLLL4Nf/TTi5hes+I91+6r+OJR2s
J+ev5M6OchDbf+YiBoxpIhpN8MTjp/O9mQ+wm8nq/y8R2cb+OZsHv7IMxJfBCkaxYpv06Ok8wiA2
fI5rbxliueqFI3l5uw0klE1W8ntIK001d5DOVhNUFSwcXNsl15PBKzhEVT+iUM4OJLpTlHpLdORS
DK4LogdDZNIZlFCA9p4UMV2nLhKjYHuU8JA0E0VQCFREEEUQXZusnQdBpYck0vB2NLnEsd3HctEp
V5G1UvRYEkmzBFIA1faoTtkg2GQ0C1v0QLFwTJuIT0cSfPTmdQSjH45koekuc+e+TDZtUd9Qxz77
7MPfX3oSadbTxCNRjjv2OKqCEapCKgP61VDIWziCTFtHN6E6PxXVEoLkku8xWN/RzaatnThZlQF9
QhTMr/fF/daCfndXOyOHD0eWBIq2SU93Bxs2rEPTFEYMG4skSTh2nnnzXiMcMlAlkb2Onsq6tWvQ
gz5ymR4aqqLgOgQCQaLRGNF4jIBPoqa6msqqWlQ9wB/+fCfpZJpgKApOiu8ceQivvf4GF/7wPJLZ
HHnTpmiJeFK5ulai7Jjl4SIKHrhl67VIpAJZBk8QkHwRbNmH7dhkSznCfoPGkYNQNI1FHywglc4Q
CUWYMG48r7z0LKYkIysqferqiEWjhAJBKuvrcUsmumhS01BDriSzaf1autu3oKg+2rI9WMXdFyl9
FTyztJGzHi7LSiZvuZlb+SkjNqzmtMFj2DhiJOO/vwbnxS08kikn8/tFU9sXbgf0zzJLmMCz5z8G
wKNHnIggwOY/VrPp8k9vAMfOfp4nr1R5YciROwT8PcXgGy4hpBd5/6mnuemZI3n7umomtC9l0ZZ6
DnhI4JB7k/RETsED/vXY98hlA4RfeY/Ry//FoA2v8vohN3PpnwcB8O7+/yIaLff1pO8+ypjlK74x
aeUvg1P4F0sYv8uq3E+gUmIAmxjDx9TTwm1ctn2fnyyXcjv/4Az+xE+/4d55DGPNDn3rIY6NTB2t
tG5j6zSye0nfG7gOCZvBrCfBrlOBXwSxGzxFRHI9crpL66YtbNi4joAss1dhXzwhBKrLvDlv0NeI
Y2ku+x53HB+vWktAc+lKpqmp7otazBP1GYQCPoJ9+iDrORqqKqmvGIRP9nPLXbdQlLPEDxiMOkVj
+qhJfDxrETddfxV2r0ux6GALIGKjuCK4kFYEJFFF9GQUx0HXNPwxA1XyUFQBT1VwtQC2ZZEvZAiJ
QfaZ2BdZU1m5aAGJZJJ4rILxo8fxzsuvUnBBUTUaGvpQEY+h6QZ1ffpQLJXQbaiuqiZZrbFifQud
retRpBp6lzXROuPrxYVvLei7iBRNB80QEEQVUdbxBBndF8C0bWzXRRcUJDxkHPyyQNQnsf+EkYR9
IqlUkkDQTzaboZDPUSjkyeayZBMF2prbGD7SZPW6DThWkaBfp7oyxAU/Pp8br7ueZctX4CCSL1pY
LnieAmLZnM7GAVwECVzPwxf049M0JEVFloSyNVqul6KXpm9DPXWhAGccewg1fpWiY6HoGslslnvv
uZeXX3yWeDSK4o8wYvRocukEiUQSy3QYPHgwe+01kRUrl3HAjKkoaoj+DWHyuRBnff9ccpkUq1f+
92iFsG0hF5jUr5U/v7kPcraJWSdczH0/eJ5BW7fwxt4HMm3hOwjA4pdd/n1XHdcd+Ra/uvtm7jnx
LCateYpHtlWaHsjbzF0Z5g8rD4aVX79v5x3wIfec8iLrjUEMXbQe+gB9oBlY48YZNvNiEsPyTB60
mglXS3AKxBM9BI/I0fToeN6avw/HPbKUt464lj7N79HxuA0ngySU/XVfOOZojn1+t134xnEKjzOX
qXzARPrSxCpG7LDfRGMNjTvdGDSKnM2DPMLpbGIg3yQu4g7i9G7f3kR//sFZzP5M5dpU5rKJAbzJ
QXRSzVTmsi/vs44hjObT7+gv+PV/2DPuWGD3ZSAi4VkiMipuXkDT/Di6gxeRMDWTYqKEqsvYXgmw
0RSFkK6y397jiQQF2jImmhHGS6VQMmnMbJ5MT4JUMceKrWl8/Txe27qZkk8n6XYz/aQGZg4bwj+u
eYDVH2xEKMjk8yUcQaLkWaCUNbY8XASvbNgu4OIP+DA0DVFRESWBolWikOvFFHM01NdSE/DxvWMO
pj5kULQtZF0jlc1yz733MuvFZ4hHo2jBCCNGjSGfS/FeIkmpZDFk2FDGjB3P2tUrmT5jCgRiDBtc
iSDVcvRRZ2A5KR6U/r4nl3o7vrWgX1VTjyirOB44Hhh+P7V1fZBkAUlRsWwH0XSpq6nlsIP3I2bI
NK9fzkcfLkI0fCQzGUzbIRQOAR6qIhMKGgi6D8/zSCXS1FRV0dHZSTKT5vTTTuLHF1/AlqY2SkWT
TK5UlmRGRBDKhiyuaCEIIMkSqiyiKgo+wyDR24snyIRDQVRRQFUkPFeiIhJmUN8KzEIOUfYQHQtJ
FqmJhogGNH7/69sQRJEly1Zzz98ewEOkqrqOESPHYNs2r736CqlskpbOrbw9731q6vpx5z33kOre
SDQSpCJiftEw7haf0DQ/DyM2rOa634t8OPoShk1dRseaenz3v8atzQNZffCjmP9o5eDhZSmIJ1u3
IAAAIABJREFU6RXzoEzYQfQ8LnjiIVqnV8O98JtjX+cfL/fj6iu/nvrfZ/GjyR8gCPDqiiF8Yu7U
t98mmraU+ePDHjuJZmB+21Z+e9R8SmmBQ/azuO2Xi9h8ZV/O3/AxboeI7+V6Rv5kCxcedAcPV2W3
kxrb2nZtJ/hN42Qex0LhI8bxFCcwkI3kCOwU8HeHI3iZO7n4ixt+AxjAZuBTds5CJvHytgtfRwuN
rKKSLpYzipc4mg0MYinjaGQV3+XfX/vv23EXdy3Ino7hhnAEg7p4PwS9gKKoeJJHPpuntr6Goycf
ji9isGndKpYsXYEumPTmIG96xOMhXCuPpmsIER1d1VEtj65CEX9fmeZwK/scNobR3kBuOu03OFug
lDXJmkUEVafkWMiShOCVUzqCJCCKIookoCo6fp9BoqcXT1SIBoMokoCiSCCIxCJhBvWJUSrmQRUQ
XBtBFqiOhwn5FG7+9W1ICCz+eBX33f8gDhKVNbWMGDkax3V5/bVXKeQydLZtZva771NfN5g777mV
ZG8n0SBEnT1P+8K3uJB78LEnegISoijheUI5peI5WFaJ1uZW9t9vf+LRENhFJCdLunMzIR08t0R7
TwpB1bEQEWUZURQIB31k0gnCRgxdN8jl83iiwNTpB7N2/Toee+LfZHJFklkTz/EQEBFFGc8tF4rp
uo4tlBBFEZ9PIxoK43nlFE82m8ETdQxVwytlqayuZmtnggH9+zGoPs60cSMYGouQLRURNYlgLEJz
SxOjR42kmM3jyQqiovPgw/9i7jvvI8oKnu2iqzIHTZ9GZU0tiUSKZcuWoygKl19+GcNHDKU72UO/
YdO+0YVcgMHXX8ypXeV8fT5v8MM5DzFw0yZkafffhVf2O4iDF7zNnaecy0/+eS/LBg/nsGWv03fO
7+n6wGVjd2yPuvpZfG/SUh5ZNJbDhq9n9o8fZVbv/hzlvsuBU+bwztvl4qRB4no2uDsqTv3lB2dx
YZ/yDaEmlMGK+/j45vu4++RzENsKnHHP3wkNkBi56G1+fNcIlh1wFk/Ne+i/upArYX8tJ6nv8hhP
cuLXdqPaHf5zpg/lQq3PVg+bKMxl2g6FWCIOPvKczYPbpSWi9HIJd2xvc73nfeXxrXqiv9f3hSHU
5qvIukWkgkFRyeIKGSLHx/GvNwikatDUBP60QzqXoNJnky1adPZ0okghFD1M0c6i+QUED0QUNE1F
9Od5t99aBuw9lH0iU1g1exVvPPwC2aSAmPCwJIGSALIqUypkUD0PRRJwVQ3XcTF8OtUVFQgiWGaJ
TDqFIBkEfH4oZKmoraapvZuBAwcyqDbGtPEj6Bf0k85l0QI68ZpKNm3eSGNjI65p4XgCsmrwwKOP
8867C8oeIZ6HIokcevAMKqMxOnM51ixfi02SK664kfEThvKQ83d+VHHz/x57Z59ph3h+fxBRlLEt
h1KpRCDop7e3k40btjD9oOlUxSsIBzS6WzdQSrdTX+HDyqewkYhUVlNEAVlFkkQK2SR+n0I2WQQk
GkeO5PSzzuKcc85l9dp19KaS2K5ItmAjuOVHNUEQwHUJ+nwUigVkxcXv8xEIBsFzyoVjpkkg4KNf
/6HUVlWheCVCsTi9OYvX57yBIbmERI90azvBWIgZh87gmGOPRlFEBNehVMhjGAoF20HQQjz6+DO0
tHdywszjeeOVWSxfvoKtbe1UVVRx+KGHUVFZRUdXJ8tWLmfQ0CHcfPsje3Rx7zh5b+/CAz9AEj1W
tFUysrYLgMPvOp1XVg2m/Z93ceep5wFw6stP0W/DVv74vQu4/NG/IMs2N/7wChTLBAQsReGX99zK
zedcws/u/DO2qjPqw1mcofyEzuV13Df/q/PeRcFFMsofbcnV99C/Ns0jR53E1pp6bFvidn85TVC0
ZHSlXFn8+5UtXPb4fVjWrhkrxxnP8qx/JjPTT/P78JUM/cn3wbK4eOoC9r5NY/2IIThq+bO8tu9U
jhr72v8T9o7Cp09sX8S2EXCZwttMZh43cc2edG87RJzthuYWKgomlXQxiUU8twuxueGs5GSe+Nzz
Pc1MljGG/+Mmfs+VeAg73JAu44/8iZ8iY2Gj7JEx+sC/jvGqX+xLlRWnqJrY3SJGRCPZ2Yb/ND/i
Ro/+ymgEpRunrZdsPkG/uELCNOk2ZBp8tUglD082wWchKeAWYVP1Fop7VzDQGMyFY07nijPOpfnD
XrrSLigCvfk8tmDjehaqLCBaReK6gZnJgaGiGwbBYBBRcImEQ7S3tlJREaOuYSB96+uRvRLRWJzO
ZIHX576FJtqERI/eza0EwjqHHX0EJ558ArgOpWIeRRRRRJeS4yEaYR7997Ns7ezihO/M5LWXX2T5
RytIdfeixWMcMu0wahsCtLTkWbd5BYXzXV44+r3/PfbO6lXLGTxoKMFgGElSEQUP2yygawqy7OG6
Np7nUShZVNU0cPwPzqChKoBVSPH+u+/x5HOzaEvlsAWZKVMmE/CHWb38I0aP34uLLrmMp595jmOO
m0l3T5KNm9tQdJ2SZSGJKmAjii6aBIamoSsCIcOgMh4mFo1QWVnJgP79aBw2jKYtmxg7ejRGIMwz
TzzGtP0n4QtFeGvhx0T8PnRVxCeJuI5Etlhg5aat9D72JDOPOYqQ4UPXgqhSgVyhiKwFCIYCSL0J
SqUCo0aP4tRTTuCPt/0J17Z5561X6UrkCcUijNprArPmvMnNXziSu8YlTxzJvv1bmNSvdQe2zR+O
f5VXbhqMYn8q0TBv/L48ef2rbP3NXOJntvCXmRdzxrX30JP3YWsyb113PM9MP5LfjWog+OcjWH5+
D9/966Ms+/lQnl+2+0IcVbKZsE25szsa518XP0cg5vLnkeey7J3hJIL9OSx1Lr1bK/iu9XceuuEC
LrviJoZVNfHhVfcy/uYfcum0BZzz6HGMvetNNu7Xn33T79OydWduemq4H5rKr28/7TzOuXMWD2S+
x4OdYRbNXE5zjcETBzzID0/4GZVXLOSo1/ZwcL8CBrOOKbxNA+VFcQeRX39Wg3ob+tBMmBQn8hTN
9NnjgC/iUEcr5/IAt3MJl3A7AH/iJ1zGbQB8xK7lPVYxghu4jp/xe3zsfrHwKn5HG7W8yqFAuQL4
kwXmSrq2SzV85f5/bOO2ewhRyEoJTJ9LUZHwokUk2U8xVSQjZqjqaxDvN4BpM86gb1TCFATmf/Ae
bz88i1R7F+mQSf3x42mp8pAH1DDe+P+oe+84qcq7/f99+vTZ2Z3ZXmBhl6UjTaoUFbG32KLRRGMv
0RhjnicaoynqY9RExSRqNPaCJjbEinQV6aCUXdr2XqbPqb8/BhACNuT7+HsuXrxeZ87cc99n7529
zn3uz+dzXUdwcs2JrH91LRf+5kq6d8Xp7Wijx6sixARkSUSydRTBRrEt8nIDCIaOryBAXjBIYWEh
ebm5lBQXceT48WxYt4bRo49AVNzMe/1fzJhyJIrby5KVG/F7XLgUAY8oYJQIWA5sqW/m7/98lh+c
dgo5Xi+SAy41RSaWRMLBF/BBewfJZJzhw4Zx/tln88icB+hOZ1i0YD66k8QmyMSjJzO/dvEhze0e
fH/aO+kk2Aa2kUYWLPxuCY/HRSpt06+shL7ebgrCERYvWg5Wkjdee5GxIwZy43WXUxgpoCC/gIaO
Wvx5uaSSOjOnTeKmG37G3Nff4PiTT6Kru5eMYZFImiArZAwHHBnHcsB20NwSkyeMZsqEMUiOiWmk
KcrPJzc3j61btlA1sBJJFIj3dLKzbgvhcIRoRzNF4RxUt5+agQNY/9lmOtvbSAjQHk+hGxm6YmmG
jChj2Sdr6F9SRE1lJXoqgaZp2Dh43G4kQcIwTNxuDa9H4dZbr8c2BZIpHd2SuOPOP/Hm2/NJZMyv
n8hvAI+a7edO+QyuHvAu953xDm9/UMqQSZvp+3U9Dywez2ctl/Ps2o0kzrqAfxx7E499EqKiq5lp
Q+vpzITZ+liaX5Tcx+q1x/FMw2g4EfgaOQHnods5beoLlJUFGd/3KbcvvZlJ9b/j8ZEXsqpuKnKZ
ySldb7A45yiKcuvZvHkoY1b+jcXn5nH8xMWI1/6G0pwoT60YwbCidl5dX0Pg7hFcGptDfbqcxx+9
er/x4s3Z/P0BA2rJAI+fszB7HvgYGD3mE564cw3/vFcBJnNgOdqhI0wHnUQOOF9HFXW7DVT2FS/b
Fz/nXvzEWcmYb2VkMollZNBoJ5+TeJN8OvgTN+6VU5jMUlZ+y+rjKraygJn0ZwdDvyIir6NSRuN+
0g2QzeA5VMIHMH1pWkO1xMt2UHN2Bam4jeoSMRI2zQ3bcfUGcBf6eePVf5FjW7z86vNMHFnFtVde
xXDFx7IyD4tdvShHFhEc5efUogGcX3UUjz6zgquvvZFYbwdq0iJl6PQK4I4a2IKDaquItoOqOEyd
MomxY0chKgLpdJLK/GJCwSBbt9QyqHoAkpUh2dfNrtqthMJ5dLU2EPJPxxPMYXB1Fes3b6WzrZWE
AL2GTSqZIBDXqRlewfJP1lDVr5z+xSXYehKXpmFh43a5ce1W6HW7VfxehZt/eS0pRFIJi5Qd4w/3
PM68d97BOO+7qax+b6Tv8vnp6GjG9mtcdN4ZjBpWQ6yvi7q6WhavSNKXSaInu9DTXfi8XmTBT2NH
in++8DYRzUISJbyqyA3XXsaRU47i5Vde4sSzzqGlsydbzaqbmKaFadmAgyIL2JaDY4Ms28hChn6l
ObiEJF5NJppJ0dndQSKVQHNrZEyLQMCDJ5CDKYhsa2gkI7u5+5FnSRk2ja3tCKJMZ3cXIiAIIr3p
FDs6ehjhqNh6hvq1mygcUIPXVYSCgZMycUkKHtWD40h4ZBXFslmz9nM+XruZJSs3kjJg2ozpBPOb
2V773Vzvx9+T3b65rDXEu++cSFXVFiZ+0oUmJ+hNubjq7X8jvHgbxw+pZWx5M2d8Mp/0384hErmT
NTUSVxQt4qFtVQRH34M4YCovfnYyWz4Mf82oX8CUJKoHbcL1PMzwLuW5QZsoLG7i6RVDGdv8MJ0/
PB7TK3L+shd4ffKxXNQ8h5Uzi0n9u4uevuxXs7E3SGNvNpK7sSWfpQvf5O1jZzGr9j02Tx7G8mXT
9o7X6w9CD2zbVsWrf8mmp84+4TWCi9az+p52Vrfn8dCiFn637E9c/8px32lu9+AUXuMI1lJPGZsY
zMdM/NK2C5mGlwRTWcwSjuIE5jGOlSxm6l5dnm+D9Yyghs0MYyPzOJFqtjKNRXzKWMaRFdJr263T
k8b1jW4oCbzUUs0qxjKE27/0inRUPKTYTn/mc/xBb3iHAkGCWFeCJB1MTGhcGj4VtT6XVbu2s2z1
+6RTGcy0hVfPIeDpQBcMaluj/O359yjPSdIQ6KJoahEzp83gqtLz+PC5ZZzws+tpaexDT+tYNli6
TdoUkB0JQVbAdsjYQjZIK9sUFQZxizo+TaUvrtPR3kksGkdSVFK6her2EszLxxAkdjU0I2oB7n/8
JVIO7GpsRlFc9HV1Y9s2Og7xVAq1q4+05CUaj9P0yXoKzhiA48rHcHSclIVLdqNIHixHwuvWUMQM
a1ZvYOGa7axcu4aUqTP1qBPIK6lllXro3tnwPZL+lKnH4NMkcv0asuwlP1JCbijMrvoWLMDjklm3
fhVej4YoWri8LlLpBIahM3jscGYWF1Pf3EYolMvpp55Ka0cXGcOiL54kY1gIgogkSdTUDKavr4+m
piYEQQTBwbSM3SmbOuMnHUVHSwsGzaz7bBOGYZJKp2hsbCYaj4MD0XgcxwFJljFsh0zGJGWYaC43
DgLJRBzLdnC5PCRTBg1NLQQ8HvS0yeKlH7NsyUJUR+ek2cdiWgKW7WAaJppPxREkWnpStHQnMSUP
hg3rt+xkSPUA2rsOXTf7pflLOWvbBzx2+vnU9eQRXWnz0bojePza83lKuQyAX78xkwvHr2N4cRsT
+zdiiyJSvcNVOx/BG0mR/ugMtBuH8fK8iWx85+CqjktveJwp91980PeeO/5Mnnnyp8iKwYDSrdyy
7H8449FzqNTr+cnpC7n+RI2528uBfGAd7zBl9ye/PC1x1Ib1rBs1AoDRYz+h6ImnaFohMnreEJYs
mw7AWec8w6u7axLOKnqR4zJvUtr+c4YUtjNxwyr+fvFFFL//3cyl92CPcXk5DWxi8Fe2XcR0fsPt
GCgMpI5OwvwPNx2yPv5ZzKWcBlYwDgeBLbs1bxoo563so9i3RjNfZDU9wU8wUGiliNP490Hbt1J4
2AgfIHN0gJETBpFjyqh9GuEB44iGeumJ1dNpj0IKZViz9Xn8QS9pdwhRc2PEE0hmishoH+XVwxki
RDi5dwI/vuxyelvb6LZlUr0JcGwsy0aUJAbVDKanL0ZzU1M2ew8bwzKxkDAsGD95Gm3NTRhWKxs2
biGVSpNJ6+z612ukdR3TtDFtC1PXUTSVvmSKRMYAUcpyDzKmqZM2dFS3h1gsRd22neTn5JBI6ixd
/jELF7+PKtqcOPt4DMPBshwMw8DlU7GA1t4krb0pMoKLNCKrPqtl+IgIlqf9O83x95inL7Nmw2ck
ujtYoDo8/dTTuF0qp51+GoFgDsm0gW0b+AMBivLDSLKIZRgMGzGIVWtXMVzI6ozf+ItfsaOhCcMS
QZDJpG2QJHAEhg4Zgd+fQ7+KgUyccBRNTQ3EYj1s27oZUYUFS1ey7JM1CLaDaZok4jFkScJybAwb
EBQSqTQer49UMoXHm3U3Ut1uIiE3jiCSSKUI+0OYGR1RlNF1AytjIbihp7uXBkGirasXtwg9CR1H
kDBsyBgmbo8fGwkUL46UdfXSXCqCLOOIMqZ1yLEaTt+5kIkPX8rGG/N2n3mCO05cyOjX1L2/9c2t
edQUdnL9jI+RJYd6o5S6c/J5tO5iPprfzLmTdcbPKiOe0Q46Rur+3+NSLJyHbseUJFIJicAvvqgU
vXpQJTAH0xa5zK5Et6qBbtop3fsUcihoiRRy1UtPcA6vITyXXb0eU9XOqdVzYX+dOV587iIuznl+
v3OKYZDQD498wb6r53Gs+Mq2t3E7d/Ir/ou7iOPjDU75TmM/wcFvtocL+2r6RA+zEfuXIWjG+fiZ
BbDFZJiTT2NsM6m8JMedeyzlPh1v1MeWaIRUJfhzJHKFXNRigZJpPpbnb6PcLKVqW4if3fF7Es1R
orKJLSUxdBPHAU3TqBk8FF8wQHm/SiZMmkRTUxPxWC91tZuRFfhgyUqWLF8FjoNlWcR748iSQDKd
RtHcWA4YloPtCJiGgSIb+AJ+cgLZ7RlJVMikUvjkEEgipmkTjyewDBtdN+jri1Hf0EJ7dwyX7NAX
T2E5CoblkEkbuMNBTBMc2YPLF8Kyd+EPBJEVFzYy1nfc9T10l47viLbOBmwnQ9qIkdDj5JcUIKgK
az/bSL/+/RkxfCglxYUUF4axHQMcE3/AzdJlizjtnHNZtHw5d993H02t7Zi2hGWLRKNJEBVMw8bl
8uH1BgkGQ2iqB5fmIZPRkRQRWxRwUEH2EtclUrjoiBlkDAHVE0C3JRSXH0F2MWjoSEKRYoIFpci+
EIHcfBAkQqE8goFs6bdp2vgCuZimjabISNjYaZ3CSD7BYJBUWkf1eEEQESUF2wHdtFEUF7ZlkufX
yA+4kM0oXpL0y/PhE3Vy3IdO+nM/qWHN1nziGY14RiN2710kdIVp8mLuu+AK7rvgCl65dC4n3Jog
5fdgCwLldiOnL5rPH/5wIs8mzmLIzT/6UsIfU96MS8lmhjxy5oU4gN+lE/F9YWayZ+y0oaBbMgX+
OBWR7NOLWzGA/SUd9uDOU95n22+/MNWee8n++d+//evdPH3iWfzhpzcwa3AdomCDcPC52lIwkPmT
ZgJQFoqy3eqPoSj87dyvl2T+tviU8ZSzi+u+xBD8fq7nV9zF7dzGXM4+7OMfToj7FVllMZC6r/1c
zkGMYr4NtK0SJR0qBaZCe18P/lI/qpZi08aVHJkbZNDoXKQqgWpfkPy0l7TkEKtOsrp0E6PHHE3m
uU7u/ONfifVuJyFkEAwP3ckEyAKiJCNKCm6fj2AghOpy43K50TNpZFnM6m6hopsSfUmHlK3R1p3C
sGwkzY2gaNiijOoOUjFgECUVleQVlZNTUI7qzSGRSBMMhAgFg8RjcSzTRtN82IaN3+VCERxEyyKS
F8bv85HO6KiqB8cRUJRszZJp2tl6BNsmL+Ah162gWUlIdFGZ7yOo2ni+JrX66/C9rfRlKYPL7YCQ
QdPcGGYGX8CLbhrZO280SX5ePq0tTXi92WBHTiDMxddfy+/vvJN1azfQ1RNFN0R0w8FxFERZQxQF
NE1C0zS8Xh8etwdFUbOeuKKIaTuYjo2RMVBcDl5vENM0KCqrwEnGGDp0CLW1ddiAaWdTNuO93fSm
TDS3l3AwQKK7DcFIICESDvpQVYWi4iKKI3lEe9oYMqAMr6ZRXlLMggULUASHSCiAZWTwuD2IkoRu
GAiSgiRASHMoDSqcecxEqqpriOQXYNsW04849GKnWEZjeHEbK+tLCLiygmq3zF7Cpv5VFHe0ctLi
91hyxATy3qpjYzrExP4Jno6fy+qXE1TUL2XppyO+0Tj3/iirg7MHfz7zbc5/8syDtr144hp+fvqn
RK78OSlD4Ufj1/H0igMzSV5cPRRV+oJ0Koe7eOAH8zm6Zjtv6Cehe738esHvWKOOZjEnMGvwNvzx
XGI+/wF9BRoSZLr8/PvetTx3wpkMePEZ+Bs8MubKr1CXP3TUU8ED/OyA8yU08lP+8a0Ctd8HBrGZ
ySyjjMa91+ojBmT3+/8TuXQziKw157l84ctcy0AOxURFFYpw4io70xuJFrdQ2K8PLVpKhwte9W4j
1t5DYbGb+rZG4gVJys4aRIFUxGUV53H/1Q+x5NM1ONE4mWQSw0kSVVTklAscCUlWcPu8+P1B3F4f
sqIiqy4EWQLDwbJtzIyB5vLiC2R5oayiP2ail5rBNdTVbkOQJNK6iaWn6evuJp7JFpMWRgIkoyay
nQZbJNfnweV2UViQj5gfprerhcGVpXhdLsrLSlj44YdokkNBOAdbz6CpPlRJxjRNZEVDFR1yVYEC
n8SZx0yiuroSf7AY1RtHqvhuT6nfG+m7FY28omIGFBcT9HoJBnzEE9mtFE3xkIw20NHehaq4qBpY
xYiRQ/F7XVxx+VXUd3YR7Y2TzpgIooLtCAgi1AwaTCDgwef34PX48Xq9qKqGadrIsrBbYEtAkBR0
w8SywDQsTMvA6wrSE42yZUsthqEzeuQIWlubcbs0hFQfibRORVkZftnEVZDLjCPH4vF5eff9haQs
m0EDK+hqa0Q2FI4YOoCCvBDxaJRBA0pwqQ6zj5kJ2HTHM3y+FXTdQFJVbEtn2KAqRgwZnP3SmRaK
5iKdydDJoVfkjilr4bJfPoZlQ8rr4cNhU0ipGh+NyhpWn7pwPnlv1bHMP4x0/6Fk/jWHfOcVOjpP
4tkvIfw1v/obo0rbAPhw3BT+2u/Hewn/jit+ye/m3Pml1+M8dDvCNbcRf+xI8rxJPvnFY9SfMJT+
v13IHfOnI4sWRYE4P5m4huflo4hNnMUHN3/A+cceyV3H3cDJ4qMMETu5tPIKlq+YRSTSxi/V/+FX
/3ySk+fP5+17fQys2szv2P8aNlgjuPbzX9JYNol9OOmwYU9O+h4MZz0b+GL+pu12pwrT+f8bwt9z
Tfu6du3BvsQ9jUWsYBw3ch8Am3bLQ/yRX/Oz3emfNbuFI/4TVd/gqeBgiA9PUHNGESXiYKKDwhQ5
RUhdKloQvLqb3Gg5TdZO5GtL8Yg6M6xxlO3M4+qzfk6y3Satx5H6LDKyi3gojZLQGTPsGFxeCa/P
hcfrxevzo6gaumEiShKOIIAkIEoKetrEMh2MjIFp6bhz/PTEHOpqt2EaOmOGj6K5qRGXS4N0Vjqh
X0UVuX4Zr5hm+qRx+D0+3n1vARnTYXBVfzrbGpHSCmOHDySSFyIei1NVWYzMCE6ZPRvBhu6EyeZt
O8hkdARRxbKSDBlURfWQ0YhWHFG0kJQQCaOB/ODBhRC/Kb430i+N9KNfRSmxni6qKvvT3tJGblAj
GMxF1RSC/lzyI7mIgsWsWTN4+ul/8uabr9Lc1kbKcRFL6rjdXpLJFJrLgywpuL0uPF4XjmPS2LQL
PaMjSQqpVIoxY8aB4IAkIogisiyjyAqi44Ch43bJdOEQDoex9RQeVcanwFmnnsC6tWt48e2lDKmq
ZGhlMWuWf0h1vyJkRWHi2OGoniCfbvqcXJ+baGcLLz39KIJtc8klFzNj8nh0YzSCpaMoColkGlEU
MAxjt9yEgS3KmJaFnk4TzAmSSKaxcZDlQ7+jF422+dH4R+lfUcemLcOoGZxNv6vf1Y++vhx+e+HN
dLQXEov5GTLjCm44+lesfe7gWzl7sIfwLVvgyrtmMGT7FmAbd57yAc/ddskB7bvuvpu8m2/e71xZ
TpTOu+fw3uZKbmx6gIJbm6leNZ+d0VyWPDaXitYmVrumED9fZYE2lXvXbKH7zY389tHZXN46g7LJ
S6G2hx9d1Mh9HTfyxLb9nW7XDzwwmNpYdqCl33dFDZuwkDiTV3h1d6HTHhkCBYOTefOLa2I4r/CD
w34NX4Uy6jmdf/M2s/eamlSzha0MopqtFNPCIqZzPG8xnxPoz3Z2UMkcriJMJ7N5m+ksZPo+loqD
d6/o/18iFU8gF9j4d8pMjR/P5s+aEcoUIolcBiTDLE+uQJpio9lp/rvkp6x+8GPuf+N5tnVtx0mC
lfaTkX0IVoy8HjeCy43pEXD7PTi2RUNjIxnDRJIUEqkk48ZlF0GIWV6QJBm3oqFIEo5p4Xdr9AhQ
WFiItZcXBM45/UQ2rF/LU68uZHBVf4ZVlfHxkvcYWFqAS9WYMnYUqifAqs834XcrRLtaePGZf+BY
Fpf89GKmTz2S6ROOQNANJEkhmuhCFkWMtIEoKZiOiCOqGLaAkzFQFZAUIatEZv8f3d7Pu3DkAAAg
AElEQVTZuW0rib5ekqkMTc1dJNIpFE1BVRXcGljpGD3RCNdecyU33nQ96zd8Rl80jmGBZaWRkXAM
E1USESwDsHHLDhs/20jGskHScHuCuGSLWHcfIa8XK53CUhRUzQ1mEk2Vcakyli7iGDZ+t0w82kV5
SSH9+pdQUZqPYerk5ASYOnYQ0abPqEs30b+8mPb2dnp7+kgnkgg2NG3fiquilFnHHk0mEaO2tpan
Xvo3M4+ejaknURyToUNqQBSxTAPT0BEcCz2TwnEHEACP14dl2uCALCnI0leT8FehuLONp9+6FMeB
hp4AOZ40Adc+Tw5L4JoJ91J3Uxee0plfS/h7IFzzxWp15GiLl1YPY8WuEn5yx4Fyr2P/57K9x0kt
a5gdivVx//mXkzQU6p6o5uhj5/P8fc/j6YiSSvlZWz2UmeM6ueEff+f+8y/nmE8WcZ50I7eNfoHM
XSM4edE7tLS4GeJrYfjgNfzLdxojj1jN72//IwAdud88pfS7YPPuTJ19JY73XclvYDj/zZ38iRtJ
8N1WZoeKJkrYtds5K0jvXvLfQX827pYY3aOrs0fILY6PTiI0U8z1/Jmsr9Phs+38OtgNQRILuzHS
YRZt24nbiOLu9dGiu/hUXUjuFI3IJg93nnYzv7vwFjat20ZzKorhyMjYmI6BKIFoW0iWRDKRRnVS
rFn/ORnDQpY8+H25qKpAT3s3EX+QLekMtiJlxdPMDLZg43F7SCdj2Ba4FYVodxcV5WX079+PsqIC
dN0iEMhl5pFD0Tu20qb0MbCiiI62VuKJBL3RGEHRoaF+KwMrSpl1zAzSyQQ7duziublvMuPY47Az
KWw9wejhI0GW0C0dw84aN2VSFrKSwZYd/DkBBJIYtokjaegH8Tz+NvjeSD+U60PVJPIiJcTjcTKx
FH2JTlRVQBHg2qsvZ+jgas4861RisUTW8sy00TM2msuDgkh+fj5dXV1Zr1yPF0114dMURMMibToo
soQgCeBYGOkYbkkg2t1GSBVwZBeFOSoVpWUUFYwj1teHSyvD4/Xg93pYs2I5jmWQN3MmE48cw7QZ
k1m0dDmSJKGKKt1d3TS2dOBxaQhpnYKCCBMnTiQZ7UO3JfyRUkRXgISj8swzT3LirBnUiBqS24cj
iBiWiSg6OLaBlUlh2zYev5dEKoMkSiBK2M53/2P77VU389u/3o0tCLB7gaDLMiXr13HNh2ew5MNz
WcLob9yfIDjskVTZEyvoirvRdZnNbXlc+vzJeFQdRxC4cqfFpa/cz9uTj8aZlzVZaaaAWx+5l6Tj
YdzEjdz87j3M2fULFMUg7+G7+OmiFMNrN2FIMpc98zSKYnDF9I8RxxXxWbCM3GgPT51zJpf8MkT+
kInIF72AuuB/h+i/CSRMruVBJKzDtp2joH+lfIOIlc0CY892k0wrhWTQuIl7sJCYQ7aQ7cc8QSdh
FjBzrzzEvn2ncVPDJjYzGAOFO/lvqtnCebxwWH6Wr0Op3Ec+A/Hm59NstZNscYilu1lfvowZ5xzN
1PzRjAxW86PjLkLvNOlLZMggkbZMvJIbWXGIhEN0dnZhqyq5bg9+1UPQ6yZj2ui6iKrICKaFKkvE
e9vxuyRaOloJexUs1aG8OIfCcISyKWPp6uhgxMASPF4PPq+HFUsXIjoQPmYGE8ePYeqkcSxYtBBF
URBEkWQqzfaGZvx+P33xBAWFESZMnEhHSzOK5sebW4yleEjZbh5/8glOO/4YkoiovgCOAKaZde2z
LAdVEEibWWtHxaWS6XNI6zYcJMj+bfC9kX5ubhBRlFBkm3Cel4rSPJYuW8ioUaO55ppreeutt7nt
tt/Q1RMjlUphmjaiQ9a6UBKwEJAkAU1T8Pm82a0cGcLerNxpLGOSyMSw0hZ+j0gi1UNpYQ4DynNx
bBs9lSYcCtJU34DthZHVA9i2cwfhYJj8cJiGoA+Py0VPZxuvb1zHkDHjkLRsICtt2ITyi2ho7aSj
N0rPrmaSts7ij1YgOpAxDHr7UkydfgxLVq7HX1DKqo1b6ezuY+rMo7FFKav1I8nopoki2KBIJNN6
tnrYAsuw6Useuprea9NnU9qWzUW//4Ir6AmGGHrx6/QfF+PhuwbQOR5++8q537i/wkCMrkAOxUc6
gEPTx+Jek5W0qVDdUUdNQRfL33iNitZGoh4fT6nnEvX62F5awSs1Mynsyur/2ILI0z84C19titfs
U7nv9OuY868bWHHd33m963he/exMgtEduNuzAcR1/45x4rBaTpv7GasopOLWxcw9O0Es9QaDrq3F
/WKGs8a+xREb18PhE/r81gjSy/X8hQZKeZwDt7sOFfuSsocESbwI2Ag45NLNKbzO41zCxfwDgH/y
YwpoYy2jWMsojuMdimjhB7wMZNMvbaS9N4r/xJ6nmDvJ2k5uZRC3c9uXVhQfTqSLIiTKainvDaL4
RyBX1TO/6nkmDyzn1qHn8q+573DV4/cQa0uhpy3SgoUpOciyiOKI2KKDqsq43SqKooBgoSgieR4V
l+ommtSJJ/twEHApBpaZpDDXR/+iKizTxNJ1QgE/7S2tGH0i44ZVs6VuK5FQmIL8MM07Q7hVlZ7O
Zl7buJpho8fj8edgOQ6CKON3B1B9nTR3dBNPJEjraZavWE0qmcKyoLs3wbSZs/lg2acECkpYvmoD
bZ1dTD5qBo4ok0qnUCSBdEZHNjUUSSbWk8RR0+hGEEH2Yjv/Rytyd+3aRiAYwDJ0NEVGcCz6leRx
+gnH8ttbb+GjFavpjfYgijLpjIHgOAQ8PkLBHFRZIBAMEgwGyY+MIBwOI8sysizTHlApLStjZ1Mb
Hy7/GNMyyQn5SaXilBblE3BpbN2yhcp+/dAzKRLJGLJchKzIZEwH3YRoMoPqzSGvsICGhnoamtpZ
sv5ZvIEAXV3dZDI2hp7BMh1My8SyLFSPSmtHN5adzfpxe4PUNbZRWlaB3x8k4BLoam3K3ql35/OL
okhaN0hasHlLHa+99S4pE0TVTUFhEfX19Rx3wY2HNL+5j33OmIH1jNm0fu+5+hNLuH/jOMZPauOp
5w6UwXUrBhceuW7v60+HHsFfz53Hh+OmMHjHVq733sMz1U/wwZHT+L2g7tXdKfDHsW/6nD88cQPF
7a18+FkF1SN1bEGgNVyA+20LGT+FnW28Ne80Ck9s4/e/uJDLzn+KsvYcal6ey4PMpeiWq/ZcKU/9
R0rjH945ar/XzpjbefLkc9hQNZit/Qbyuzl3omrZm+QP5/+L83e38/n7ON94nonm06Q2ZLhi6ipW
DD2C1X8T4aSVhzS3B0OYDq7mYeZw1TcuVhqzu2rWS4LFHAUInMibpHCzgKMPaH8ib+41WB/NatYz
ggp20bdbe3pP9a2ExUjW7W37D7Jxj68ycPm2yKFv7/FKxrCcSfSwv8rqbw+hX31HN6l6F5ut94ml
ImQm+QhNG8458Vk8fNH9LNy8jrQB3X0pHATAIqC5CAX8uGWZQCBAbm4uuaGh5Ofn4zgOqqLS2axQ
XFJKfUs7S5Z/Qsa2COUEiMW7KCssIOBWqd2ylX4VFZhmhmi8j9KSQkRJQLdsMqZJXzyB5HKTV1RI
fX099Y0tfLTxWdzeAK1tHaiqSiyRQDcdLNvEMix8ATftnT3oJgiiiqx42dbUTmFRCf6cALk+mc7m
BnQ769CnG3o2y9AySOkG63fU8va8RSSMHhwhQlFFPp9OXMfvvsOv8nsj/b6+HhRFIC8UIBGLcsEP
z6OjrY3f3Pob2rvi9PXFMEwHy8mKpIVDOcyadhQhvweFNDk5Ofh9PgKBAIFAgJdffpnRR4xmU0cz
lZX9UCSLyvIitjc0kE4k6OzpQZIUkr4AWiDCms3bcbtcdKdsVm/eyaJP1xNNGtjOKkzTBFFAzxjo
uoHt2Ni2gdzeRSqlo6pKVmHQsnG7PLi9Eo7tIKkaqqKRFy4gv7CYYDBIW2sLn29cR2lBCK8isLOh
AcsRsAwd07KIZ0ysuM7Hn23js6ZuPIE8jEQKX5GL6CFYDO7B86uGMXVgPZYt8N/LZrNjxoWUG7t4
7JEk8eYDc9r/eMr7DLorh3fzjuEIew2NhSW8+MDznJt4hoFL6pjq/QjHA6vnDaZoWS8vXbKQ4kCc
BxeN58XVw/jJxLWs+liguyuPObVHQi0EpBR6bQ7dyW08t6uYlfU1eNV6/v6rCcBibnumH9DvW/9s
zkO3s2HgYGauWMJrL5Xg05t4MjCShy67cr92N/7yDl5+6Xx+0u9RJkw/mTlnz+NvS8dwjr+O1Qz8
kt6/Pc7mRbZT+Y23c/JpYypLSOFmANt4kOu4jdu5m5tpo4AA0YN+ro2CvRo/axmFhcwqxrKKsQB7
Sf4/jw8Xmg6iqbOd/od1rEzGIpHuZldRlKqr85npHIP9qcifH3mIVLtOb59FyjaxRBFVksgPhpg9
ZQp5ATeOpJObm5VWDwYDBINB5r40lzFjxrC9u5v+FRWI2PSrLGP7jl2k0wm6u7tRFYWY5kUNRFiz
eRsuTSNmSnz6WR2LPl1HLJPB/mg1hmngCAKmYZJOZ7D3qPXSRSyhoygCiqZgWQ6ax42mSRimiaK5
8Lg1Qrn55BeW4tI0Wpoa2Fr7OaUFOXgVgV31u3Bw0HUdUZJI2ybN0R5WbdnKhvp6AnluBMlE01PY
rv+jKZseTSPa00Mq0cdf5zzE3Lmv8MZrb9HZ2U0qbWI6YDhgA6qiUlnZH7dLpTg/QmP9FjQ1jK6n
SadkcoJ+BtdUE84LES4spKOvl13NTciqitfvx7Qc1qzfhN/bRE93L4qqIggOsVgUr9eLrqcQRRFD
t1EUGUXVkBUVQdTQAgEQBBQnjYhJv34Revt68fmDSIpMb2+UeCzK9ddey0MP/xXLFpBFEbciImSi
1G/agEuESeNGY6VT9HZ3IYhZU2lHzPoMGbZA2nQwHAlRdVFdUZGtDhYOfe/Or+k8tvwIBhd00n/Z
fNaefCz3npfiy/RdlNurWDO4iAjtzH7lA24bdwt+f5S2tiJcoQyPBy+mo6OAGXmrSDoefvnhBC49
83MaegOUTrJRf3Yro0paWdNYtE+vPj5k/xX6N62E3Vfe4fSXC/j3D9r2e3943SaEa25jfEUjb1zx
PA/fdA3nzX+FxoIDicmUs1/zH09Yy5NnnIexbNc3uoZvgkt4jDc4mXYOLlOxL67hQR7iGjSysZBq
tqJg7C1oMpFoo4DaL9mjWsm4vceHU2P/Iv7Jk/z4S9/fs8ffRd4B71Wy47BdB4CjpYifGCJv/ER+
6j+e9f/8gCf/9TFWm0mvHiUtKlleEECWRar79SPgclMYClPXsoXCgnxMM4Np6ji2yfDhQwjlBMiL
5NMVjdPQ2ooky7j8XmzbYf3GTWzb0UQ0llUVdRwru+jDRpQETNPE1G1UVUHVsnn9jiOh+vwoiopg
prAtndKKcmKJBIFATpYXeqLEE1F+du1VzPnrI1i2gCrL+DQZxU6yrW4jMiZHjhmFrSfp7e4EnKxU
jCRi2A6a6qYvlcaWFCxZoV9FBbreTTr5fzSQq6fTCILAq6+9wYUXXcSG9Z8TjxtIkot4KomiyMiq
RmV1FTl+L8VF+ZQVF+EPBjBdAeYv/gRBEEgmk9TvqsfvD9De3obm9eIg0tbWQzDHT1q3sBHJGDYV
FYWYukU0GsXBweVyoygKOTlB3F4XbgQymTSax4vH66GhqZWCwnxM02Jn3Sbef38+H330MX/+y4Ok
0kk8kg9RFjBtk6NnTufPf/4LgRwvquigWBmqysso9ozgg49WoDoGBeWFbN/VDJaFZTvYdtaMIeKW
CLglBD2OV7bpaaxjQHkhTnfykOf3LwuPZEK/RiY3vsJZ10a48oK+g7a7dfYibjpmOY9WXEw87sXj
SbKpchAPvnYTimqwVh9GyXU3sCLtYFhtvMupez+7/J7dZfpZc63/IPz98atjl3LXe1P4/JY5lOZE
Cfziv/jlMUu5+7QPEK65ja477+ShG6/jjjNPx3rj3f30fPTSCLA/6W8YOJg7MjGWjspu6Tz4119w
Xr9XDjr2gnFTOHv0RnZ153DJq8/SVvz1BP1NcCN/4gGu+1qNfMh65ObRjYpOGwW8xqn75ffveUrY
V/rgcOIq5hAgelBD9TIavvbzM/mAf3PGNxpLwMY5xGJ/xW2TLO/hD0U/5M8X3MGq+pVkOv2kPGDq
Om5LRpFlBlQNIBzyESnMJ1iWjyccwe5rY/6ST7Asi0Q8QWtrK4qi0NfXhyBouD1emjvbETUFy3ZQ
RJV4LE3//oNJJnbQF40hieAIEInk4eAQCPpwCyJ6OoPL68XtDVDf0ERJWRmpVIqGnZ28M38ei5cu
4b777ieVSuCR/EiygGUYHHv00fzlzw8SDPnwqBJu0WLIgEr657p5d9lS3IpNYUERdfXNWLaB7YDl
CGTSetbz2+XFzljkaF4attQyeeIQ2tXvJsT4vZG+JMn4gn5OOvkUevuiez1zRdFCljVE0UGSNcLh
QnKDARRFZuWajWxcv4Ee3UYSIZmO4/V60B2FdMxA8RcRyPOTMXSqC0rx+XxIooIjCLhdXqx0GicT
xzSSGLqOaRv85MeX8OyzzxIO59C6q4nioghV1QMJhXJp2rULxdFxbAOPR6O5uQkzk0a0TBRJRDR0
fLJKQhBRRJG8nACRSC5Txh3B2JFDGdS/lCce/Tte2SHa00a/kjwyqRiyKGECgijiWBaylcEnWoyu
qWDGMTMpyMsh2tVGtN+hZ6X85vhFHFHayomP/Jw/3vPlcg53nLSQmMeL20hzxQsPU3PVpcDU3f+z
cMkGAZexN1tnR1eI9J9/T1Ovn4ArQzStURnuRf3ZLRjWF8HBG7t07s3LEuKlk1dx13tTeOOBLu74
7yjwJwB8P8+SUN6tt7Bh1HPcZp0FfCHPsKMrxPiNTzOPI3Aeup0hv78KodOBTlgUmMhSBrCrOwdD
VYl5DkyNNE2FmsU7OP+itdz3o18y54GbuPrCe9BOyBzy3O7BvfziG7d9YbeX8OFEkF76yNnvnJf4
QVNEVXSS30DYbToLmcYiYP8U1LGsPCDO8Cw/5Hye2/ukcgV/Q0OngVK6yeVQdvUTMZUir8Ql95+H
y5FJ5mlk3BZmTwbZ0VHNEIrbIK84l1xPHpoMq9Zv4JN167F1AVGEWLyXQMBPKmPjFmQcLY9wOBfT
thhYUIDmdiNK2RqdgMdHOpGksCAPxzEw9DSOIHDB+efw5JNP4ndHaN7VRFFhPgMqKwmFQjTX70TU
kyhmBlkS2Fm/A8c2CHg0EMAxDVRNQ1QkJEkhL5RHfiTM5PGjGDtiGEMGlPPEY39HtTP0tTVREQlh
phIoooiz27zJsR0EwySoKgzrX86xsyZTVlxDd88u2su2fet53Rff30of6O7rI53OrtRcLpWSYj/J
RIZ4NI2qKKiaRjgnD7fLjaqpuPI9TDqqCBQP0WgHppWgrb2Fzo5uiov6k0k5aAGZXQ27sEVorKun
uLgYGRu3LCFKBqpXRVREBEdEE2XKysvJCYWQFRXR7aEzlqYwrdP8+ee4VJmiSA6FkQjzu5rZumUL
ve2dVBYWkZ+Xx+TJk/l88ybeXbAATIPhVZUItoWT6KIkz4eRiDF29CgytsmIwZWUF4cp69efl974
gEQsgyCAqRvkBnI46+QTEUQBRAHLsRFLw7R3dBzy/IZ9SX4zbzrOV4i2nTHyc9pDebxyzMm05UZY
edxEXl//EXG3l1FbNzJ4Ry3PrxzGvZ9O5YKa1Vw/4xOuf/k4/rJwAhua8hl3z2VcOfVTFmzpz6uP
v8OAcDeb2w4MYo6vaOSEh7Oh1Zsv6WHuqecRbPycO9bN4tN/v8wJl53EiIIOXpx9OrfccxMbRhQx
fF0lc188H86dS27Syw2/3kxSczGiuI1Nu/u9pvVh7vjp7Txw9O3EXg0ybsla3j9h/+2kpsZyzm78
V/ZF1k+EOQ/cxOgxn/D/YNv7fxWX8A/u48sD/YPYTDv5ewOsH+wm7ZGsZRLL+YCj2cogBBwGsZkt
1LBv2c9t3M4LnEMJTbhJcxu3HzRu8bM9E7sbZTTuNY35tpAEm85fd9AUTKGpIo5jM/rScYTyFOb/
5n2820PkRjJIIY2Aq4Kg2UxupAJ5RhEeWyWe6MIwE7R3tNDV0UNhQT8yKRtXUKO+qR5Jl6hv2klJ
STGy4ODVJGQNNL8HuVfBFhwcy6asrIKCSCEgIXp99OoGcV2ns24rLgWKw36KIgPo6mljS20tic42
+kVChHNzmTBpCpu27WDe2+/iZGyGDhyI6Bjo0Q4iORqZdA8jRlSTSGcYO2wo5aXF9O8/gJfeeJ+u
7jgZPUMqkyCYU8IZJ8/Ae7IbQUpg2G6KSgawqWTT187jV+F7I/1MJoXH48bv92KYBtbuHHx/wI3H
JaIbBrNPmJX1r1UFPlu/iuOOnkF3RyeqpqAKbgoKS1hvJcnEY0yfPI635r2PVwyRH/DR3RsloMrk
uFUKw3moikgmkyYWSyArLiwbNM1FOFKIorowDQtFMLEzaex0gpKCXJLdrZx9+ik0NzUQ8riwEn30
tjcxatggEvEE6VQUQbSYNGEsLz//HAIO7e1tZDIpttz3F6ZMmsSECRMYMGQ4XS1NhAJ5xA0Be3dF
nSAIWLqBYNs4ODi2QPYf4AiI30EP7/LnT6Y4ePCAIEDInWLaghxeT88m3NPFaY+9zIXjXuTy8r/x
+cAaOnLDvPTZeaSblrEqPo7cKbnMaNzJgq1ZH9o9FomTzonxMHM41jOPa6bdxjUv7S/pG3Sl6Uu5
KAzG2dIe5tob7uaS4cM5ae4ITio3+XX5HVx4wpPYbSY7lsyk8HY//TZvY9XK8cypvJLx/1jNimFH
8NE/q7ml7lgGF3YyO30jybIKFq+/jtN5lQltSw74+YLB7yb8dbgxlI2E6dwrfTCNhXuPI7TTsdey
/UBopMng+kbj6PtsNZ3Li7zDLD5mIh8xka1UcwSrWcNocvYp1lrENBop3X08nUVMZxoLmc6i/WQZ
/jcgpm2CyUIqdDeDkiEy6Q62PFLHtokikSlFxNJ9TB48iKA/jGU5rNzwObOOOZZwtBeP4sKt+Cgo
LGfDhgxWKsWsmVOY9+Z7+GSViN9LT1+UoKaS43ZRGAlleSFtEo2lkRU3liXg9XvIzS0AZARBRsHA
SqWxMwkKw0HiHQpnn3EKzQ0N5Hv8qEmLtvYuhtcMwkxFUeKd5KZ7OXX8CF556WlEwaSttQVdT3H3
n/7C1MmTmTJ5EoNqxtDZ2kIoGCSmC5imjWMDjoSpGwjYiIg4tgmiDTYIjo3w5fbX3wjfG+k7CKQz
mWw+rSphOw6aWyGV0hFlAU0QmX3sDObNewtNVMhxywwe2I+yaZN58YXnmTVjCmXlxbTU19JopOhf
EmFgeT5nnnEKr735Bqu6OlBkkZK8IONHjyCZ6COeTNNY34BLdFBUGZem0NfRRsjroaiwAK1/Mfnh
PBzLxO/zUhDwsHTBe4DDlHGjKQj6WbFrB4FAgIKCfNatW8mA6moKi8K0t/eSTiXx+PyoHj+mZTLv
w6U0dMcYOXAgopGhtztKWfVQnN2kLwoCGT2NZRm7FTglBEHAtmywHYzv6JzV3PflcriqbPHhymP4
e+fVPPjDS+mY6abzzlZ+dfY9nDfoSeZdVsDyflfQfNxdeKuLqB01jefrr+P81zv5xfI7uG9B1izE
OqmIWyv+i0muU/ig5kChtccveI3GgmKWjJ7ADzDIKzK4oUXA5WQoG9DIyVteZcUto6ktGsBF655k
WN0mXGqa1LY3+evZP2GrWM2nreM5n3u4JXoqSZcHtsDIdxfz4XUv80rlaSijU5SW7eLlly74TvN1
OHErd/A7frP39XA2MIitLOYoLuAZKtmxl/Rn8zZPcyFX8xBzuGa/fs7hBd5mNmfyCs/tTUQ9OM7m
RV7jVKrYSi3V/J3LaCUbZ4nQgYHKGkbTb5+xz+ZFXuKcvX3UsIkmSljEdNoowE+MEaynlKbDMCtf
D0OS0S2HSEGALieGo6TxZxTS7ycYf/1E5q5/g59efgdvPfceCa9JIL+AyqpKZlWU8tLcV5g9YzJl
5UW01tdSX5egLD9E/5IwPzjzZF59/XVWrW1HlRVK8gKMHz2SZDxGPJmisaERTbBQVRFFtIh3t5Gf
4yM/P0J1RR4FkTC2aeBzuSkMelm68AOwLKaOHEmZz8/qthaUgItAOMCHWzYwvKYGKW3Q09dHJhXH
H/CjujxkDBfvL1lJY0eScUMqEfQkvV3dVAwaDo6AIMhIooKuW9iGhSMLiIKA4AiAg2kY6Ibxneb4
e5NWDgZzCOaEkBUF23YQBLBsC8jeydwujTWffsz4UYPJ86mEfDJ9Hc2Eg27OO+sUhlZXEPTIlBdG
UAWDssIQ+SEPm9atYMbEMYwZXkVNZRnTJ45l5cdL+WTZUsoiOZx6zBROP3Yapx49lZOmT2LnxlUM
Kgmj6DEULFKxPiQBVq1aQU5OkMoBlRiGwfSpR9Hb3U1PXw/+oJ+0aRBLJWnvaKOzs4uC4iKa2trY
0dhI3a7/j7r3DpCivv//H9O3795ehyvA0XvHgqKIKPYk1miM5aNGjSZRE2M0KmoSE2M0do0xscUW
YywRRRAUUDoIJ/XggOt9++707x9LFWwQf/7y/Odmd2beM/vevdfMvF7P1/O5g1WfbkLwBKhvbufV
196mvTtJMmPRsNNZJxgM4to2hpFDlPN1B3enTrckKXktfVH50nn8PNx5yvu4D83EfWgmqrT/xaMt
GaBvy3/4w3euJZhOsqm6hrEPZhj1wF18cFYhWz1HoJhp/KrBYwvGsyE3hLmeY4mN8vPAD67gxKF1
3PPbVgq3xvno2E7MlZcxbHUNt7gGnc8+QP3DfyPiz3H6mE2cP3gVV1Z8yCstv+W6Zx9Fw0AzdNqi
xbSrxTz45nXEkhGir2xCtUwcUWLc7/MSDs3jSohM6eDaV2awalYA88MY2fn5J/oHhekAACAASURB
VJhRibVc2fQQcsJm8JB1nHPe0ywZ8fVN2r8JPM4V/B9/AcBLhkFsAuDHPLSb8TKRJcAeBsxzXMBJ
7JF8vo2ZzGY6Sfaoh6roFNBNAd37pHZGsIaXOQcdDw1UAtCLZrxkuI2ZLOJIIN8x3LFXH8HLnMPV
PLT79QaGkNypnb+BwSxjIv/iu2S/4pPGocIsTiMXuqiWjul36fHq2CoUmCIfvDWHk288g/mL5jC6
uoZIRMSjqcRTXRSHNM753qkM7l9FQJWpLC1Gw6G6VxGlBX42fLKc4486nAkjhjGgT2+OOXwiyz/+
iCWLFlJRXMApxx3O6ccdyclTDuP04yZTt3oJ/coiyHoCjwSZVBxFFFizZiXhcJC+fftgmCZTphxB
LNlOR083nkghKVshR4CGDoNEVqSsvIzm1kbqd+ygbnsDa9dtImuJtMczvPLaW3R2J0jlDOq3N6Ko
GsFgGMe20XUdUdFwXAnTglQmh2laCJK60+f74PGtBX3dBNMSMSwBw3ax3LyxSNYwsSwTRYSFH8yh
dXsdF533XRRXx8glmPvum1h6gsbtW5n15uukYt2cfOJ03n37Tfr1KScR7wAMjjxiEv36VdHS0Uq4
MEKfftUsX7YYj2Tjmml6lxZQUVZAOt5BJKBS1buEeDJJWjco6dWbeDJNMFJApKiUkt7VdCZSRMt7
02fgEFpiCVp64iRzBp+sXc+HCz5m0bLldMWTdMWSdHTnnypcUSWVNakYNJhNO5pZvGo1Kd3E3Sm4
pqoSpu3Q3t1DU2s7W3Y0sWHTNpauqKV2/VY+XrrmS+fx81ASzOvay9f+GuMAfH8Bl+0P6yj3i/zl
ihlYlkJ1+XaG3mmybNRVNA84mqv//BS3XXMTN7/1CTOOfwND1egVb6XVV8KH15xMx7VRFkwcy9wz
/8Jv5z0GgGIaRJJxnvrReeiah6Q/QGNhLw5fvhxDVnjsrIvoTPtI+gPEg2EeLbmc0654GY+Y5OPL
j6cw3kOgK0HdBXfzy/vu5S5B5c4nZrKlM5+X3toVZUdPvnhZIMZYNWksf/jXbbsVPiet3SOY/PO/
P4QgOCiKgaIYXHLZw9x866/4xU23cVufb1bxsocCZjOd25iJjsY/OI8uogRIYaCwmlEsZzzDqGUm
t3IbM4kTYQLLuYU7OZU3eJzL6SGKg8Q/OJ+JLMFG4lTe2p2nVzBQMPiUYSgY/IT7yeHlJn7LCbxL
Fh8GCj8i//3YyPsVej/7dLEHws7PEuUP3MgaRlDG/lZ9BvvfnCzdi176dVDcraBlFKQeGzVpUJwR
EHJeGoVyelotMk6S+UsWoWFz0fdPwufYGNk4c2bPIpfuoaVhB+++/R/S8QSnnjSD2bPeol+fcrKZ
OGAxadJ4qqoqaWlvIxwtoE+/vqxYvgSv7ICdobJXlPLiEJlEB4VhD9UVxSQSSXKGRVmvCnriSYKh
AsKF+bhQH+uAqI+y6kqSXXGyTTHMxh4al9ay6r2FfLRsNV3xDF2xFJ3dcRKZDCgqsWSK6sEjWLet
hYXLVqO7AggSpqmjKSKOa9PenaS1o5vtTW2s27iFpatq+aR2I+s2/o8Wcl1HwbJcQEJAxnUsBGS8
HhW/ApVlRdx0/U8J+2QEK8Ovb7yef/7rNUaNGk1LayNtrW0oioKmaQwdOpQVK1YweHB/6jZ/SnFJ
EStr1xNLJghIEogitevXU1xUgK36KKzsA5JEQs9RXNWHTZs3E4vFcV2JjVvWsm7TFizL4b0PF9Pe
1k5Oz6GbJpZtE08lcHBxLQePouARZNKZLHXtMVw3r0uTTmUQRQnN66WwqJCYYSHLEl4txPI1a2jr
TlBRVkQmmcTr8dKT1lm7Zi2WA+m0npdjQCCZSH/JLH4xJvzh/+Bz0n/OQ3dwbPx93vtoE0Ob/ok2
dBbrVtzNSx/fwzlTnuXUzreptQbQ2lLO+8tPpCLQQFdXEeWdbazMjOWof7zO8qNPpjSY4t/xMYwZ
0IZsmWx8dSQvVkxDXC2yXRdYvzYExHlyyHFc+3/jeW3liwyXLSLePHtm0VvHcvvGXfaIfbnmAIXC
wPW/2u+9gSXdLBk+hvPfztM0n/jehUzlfcJNCTojUexWiXsu+jFVL9dz0WF/olc4xaQ1yxn12l5m
38MPZXa/GD/nHhTyT1i/5i4e4moK6cZG5O9cxCSWcBQLOIYPaKI3DTtz6pCXUahhy+7UzJ7TrSVG
hG4KuIS/ksXLC3x/93oHiT/zU2CPhMJnlw8Fuyibvfcq0iYJ8BanECPylXoVvgwJUUeLFpNoSmFJ
Nl47h2yFCIqlFFopli/6mOd/fT8jU1FyTjszf3oNz739EoNGjaCzs4PGxqadccHD0KHDWLFiOYMH
D2LjhloCwSBbGjaQNXKI2RxIu+JCFMfjpbi6D4IokUilKerTh21bttLR0YUtqWysr2X9hjp0w+G9
BYtpb21H13Mk9AyuJKDrOoLokjFNtKCDKTnYOngWt2PjgiuRTWZBEgiFfQSDATrSOqrswe/zsmTl
Klq7YlSUFpJJx/B4NLrjWT7ZsB7FkEhlW0lnPCTtJC3BA9Ovvyq+taBfUtaHeKKbVLIL29npD2k5
aKqM69qMHz+G0uIC/DKY2QyaV6UwEkTTZDriOSIFUTLZLKXlvYknUxiWzfKVK5F9XpasXEl9Qws9
qRxud5JkKs7mbfU0tLWztq4R09ARRZF0Op03SlckctkcXkXFtCzMtm48Xg9tPUkQRAQEXEnAESV8
kWIkTSUS8FEaDBFr7cSVFCxvvqFLkhVwHYoKCojFeti+ox5T9mJmUgQ1GcF1CQTDnHHKCYgCZDJZ
XFFm3sKPKYgWo2oBdNPE4wnQ2fP5hdgvw/FnddCVXs+KHfs3KwH86YIfYZ65BJ9j07txKZqeoKMj
X0wcpX7Cx1PHsXV1f2a/czKjRq+kxl/H6o8KeV0dwJmj3+Af4lHEPhEo3dzAdU8fRX1XAQCPnvMA
F7y0hxbz989o0HzniQPr/Vx6+EpkyeHxheO5YnJenuCxc//DYwvGock2fQpjDC7t5PU1g/jRUSuo
6yjgyd+M5XnjRP6+eDR/WPAea5tLKB+a5TfVT5IyQsxYNJd/cj7Bm1Zx+XEf0532YHsFJNHl05Yi
hh307H4xRrBmd8DfheN5D4BZzOBSnqKZcjopYgv9sJBpo5QpzGc543ZyXyr3G3eXns+uAuy3hR/y
9O7lDor/q+fT+UMLLQOe93yQ8pKxbCw3SVDdTDCTYeDEYymrqKYoJtMq1BOVVQqDQVRNpr2zi+LS
ElKpNMWlpcSTSQzLZunK5Sg+H6trP6W+oZnuVAanK04ylWBz/XZ2tLazpq4ewzSRJZF0KoVtgUeV
yWWzqB4vpm5iGDZ+n4fOnhTCzrjg4MVyLWSvilPg0OeIcirH96JJ7yaZThH6hwdVVpEUCds2KApH
yOQybNi8Hk+gnFwqTkAVEQQIBAJ89+TjEQWbTDqDqHiYv3AxZcESVJ+FbviR/QKJzMH7bMC3GPT9
0bGUVglsrltOZ9tmJMkl7PHgWg6Ko+OTwasp2JaB5dqAQDyTYtbcOazb0Ux3dw+ZrI5l2+i6iSAI
ZLNZZI+fTDabL4yK+TZogXwqqW/vvrR3duEgIQoioXAETcsHa03zoHq9mKaR77RzwXXz6h6u6+Co
abq2dRLw9aVL1hE8CaaMqOTNuvWs78oRLa1EV70gGQRFi77FxWQEkfZEBs2nks26GDYItkE4CIKR
ASeAKAkEgiFytkDttmaqBgzl0011DKjpT+3WbQc9v2sGDiPz+hgeOu9trn5xX0aNRzHJeH30alpG
a/lYlk24kqM/vIuZ2ZlMEt/h4/syVLStZ9aCFLCalcBKABYzevV2zlg5afdYs/YyDFl3y8MMvevq
3a8fPntPfnpCdTNFgQx9C2M89fFoLjl89T7nlDFkam6/liuPWsajCyZw+9ZOeBuufGl/XuUF09fT
vzjPznnwg/y57Nru4XNm8dTOa+X8aUeyfWYNAAPv+DGvXfYShTfeiPvQTIb/5mrcu77OjH51FNG5
33srGUsd/feRTdgb34RswhfhSBayaLcR/cHjv92RW7FyAiXVNbSes5L2l7bRPxGgRK4kqenkhGYs
y0VO5kjYCpLowTQFtJzNrNn/oa4pQWdHJ+lUBttxyRgGlgBZ08CrBMnlDFwEJElCNwwEQcCyRPpW
9KO9qyPvuOlAIBDB5/cjCAJ+fxBN0zANE1VV80/ztoPtOEiiiCApbG3bSLlSSdrVSYQS9G2Os/L1
Tzj+irN5LziXQFuALqDY72WoEqZWd+ixBfypLKm0ieF4wcoRDopg6chIKJJKyB8kZ7qs3dpEn8G9
qF1fz8DBFSRaD22Ovz1jdFFB9fjp3380HkWjpXEzlmWhqRJYDnPmLOTEY4+jwK+hCgp6TuDc869g
yYqVrKi9n6CmEQkEaO3oxhv0oXh9mE6+ocvr9RGPxyksLCQYDGIYBoFAIM8W8vnzBiaiQCqVprWt
Fa/XjyhpFAajrFtfi2NY+DwqrmuTSaWoquqN6s3r2zuGjZnNoogWHgeSbXH8Wt7/UpAldNtGVSRw
TMpLi6jdug3BzKAJDo6ewquIlBaFqCgvQlMEcnoG27bxeDSsngSinUMwsnhlF8U9tCs6QMsLx/O0
8ho/fPY7XDNlCQu3VPG70+fw5GFjWTbpGs547Ye8euaLPHrVWhKXncLa6Udyb+UNUAnnj18LwOT7
LmHhz57irneP4topS7n66GWMrWwhpauUhfZNQbkP5ZUYj3vgB9zy1lT6FfZQ3xWh6w/3AHv0+C99
/vT99ikOZHh0wYTdy8KPb+VACGQ/v1P51reOYf1FA/ms38fm9v0lBA4FZbTsl37ZhXlM5Wj2pZGe
x4vsoHIfKYX/VUiHKO37RShN9qJf7RAC003CPyti072L6asGSSdilEgRPpr7IV3FU+kl9kMt8NGi
6Rx70VlEFi2n9qm/EvZ6CHt9tHb1EPb6Eb1eLEB0FLyal3Q6TTQaJRwOo+s6fr8f3dDx+rwYhoEs
icTjCTq7OvF6/ciKTaQgTEPjRizDQFUkZEkgnUhQVdmbQCCAR/DRLAYoacvSnUkTr7QhJvHKbc8S
Hw2DmwZR4BbjT/eQlDP0qi6jfe1ylKCCLYKjZ9Bkl5JomP59q8DRcWwLx8zi0xQSVgpNEpAFGxEH
IXdokuvfWtC3LBNB0JDEIvpUjae6cijbt62lfuunlEUjTDhiEoZuIygWsixy3yNPYHuKSBs6f7n3
HmSPFxuJtRs2c+fdf6SspBzV56elpYOiaDH1W7ejqV7OOO07zHrnHXzeAJIoYxoGrguaz0fOBNMW
UZy8haKIQEDz48gGeipBYTSMneym2O/BGw7RRRzH0imURSb0GcSpx5xA+8Y2Ply3CV2VsVyXoCpT
Hg3ywwvOpbmtlWUrVuLzSERKCshm0oiCRWnIS9ir4VpZFFnBdS0UwSXiVfAJBgWai5vqoOQQjNH3
Rt3TM/j14xl+/sj7FPz8Ro7o28i8u8/mX384koeu2UTf+rk09OmDep3Ae+aL3PzGxRzzwR3oaoBI
98Wc8E4dR9Y0MOuqf5DWFTyKhXztrSx7/988cPQp/Pax32BJErK9Jxi8+aMXqLjlOja0FaFb+0v4
Hjugnnmb+/LCxf/kkbMv5qLnnmVtcz4n/OT33+CON17lDv1hbtX27y7VEjkGD6llBnlXLvvBmVTe
8jMeP+8t7i//Hhs37EncVFXX805gKry2Z/8l23of8py2Ubpb5vjL8Dt+uXt5b3liHfWAsgh7b/tN
WCwOZy3TmEsbpdQdQOfnFu5EwvncY4s7C0VbqPmvn5ttWziaRPCNvsRCKqP+HKFzUTuxp7cTDtoc
MW4SEbWUrJIk423nsb/Pw0kU4Hd9/OW+e5FkFdOGNes3c8fd91BWXIbm99PR2k00Usi2+uV4PX5O
P30q77zzDoFACMXI5rV6dsYFwxbJNrcjKS6SoiGpWj4ToEgYmTRezYPgESkK+yhXAyz3SUQTBorf
Qq0MMrBfDaUDw7y+ehXT75jI7MvnM9itIqL5uezCM2hr2Ubdez58fo0Kvx9dzyDYJtUlEXwSyKKI
iI2CgybYBFQBNxcjpIFoJBGjh0bl/taCviiLZA0L11SQRQ1J9jF0+FEMHz2WKy49D5+Qwqt3I2Q7
kUSB7lg3Tkhl2LDheBwTDAkXiaH9B9C3spKRo0ezoW5LXnNfklFFETOb47m/P82QoUMY3H8AwZCf
OfPeB0HGRsSw8h6ZkgCSa+KRZCJ+D/GeFFdddjGRgJfWhm2MGDqIYHE5t9Xfi540qCqIUCF4WPLe
fJo3biZoGKiuiWuKlJX0Jp3twtVTiHYOv2DRr7SASCSI31eGKgkMHTyIbDKGpubloG3LorKskOuv
vRJJEikvKyOdiNPe3v5fmWtXEMEr8ofrr+em6y3+2M+H8uATnCevov+WdzFlL+pxIumUn+cmfwf1
1U8wFD9tZaN57pb/4/nLf8zbk6dx0sI5WFEPJFOcNmIDj99SyU3TH+aRM86iOVhEScTi2hfyNEWf
mv9hflZgrSISZ/HjL/Lgdy7jSMVgaeo87rv3Znb8vAztFxa5+3/D39aPp3VdgPN/91fG/KiYUx/7
PhdO/IQHfzSHw2++kCmXP8QH844H4KVr32Gb05cFd/wbgNGX+Wh849PdgV8QHK6esZLk8F9x+Lqf
Ebnf5kSu5bhZSw9tThH3CfjDqCVKN0exYL98vkHelazPZ1Ih2k4Tk13NWSI2XrK72TUzuY0IPVzM
32ij9Et5+ruw68LyO37JTdy9e6xdsJB5i5MPGPA9ZLGRdrtl7ZJY2IW9u2/3vuPfdUwHARsJG4mD
kWHoCouMyvrJsp2+ybGk/xFDGLGFib8dyrSJI9nmrUfpKoemJL0sHbMpAaqfylFDwcziWha2CUNq
auhfXc2wseP4tK4OyYVwIEDA6yWdiPPic88zYMAABtX0JxD0MXfenLwVIQI5w0BWFDRFBiuH5DpE
wn5inW1cdvH5FIeDtDXtYNDAGspDvVj+4L04mXqMERqDR4ym+F/N1K7ZwoCkh82XzqLf7VNQ/9lJ
sC6CrndgGjsIeAupLismFFIJ+MqRBBjWv5psKoGIgyRLWEaayvIoN15zLaKaI1zQl4yV4N/V73zt
ed0b3x57R5BAkBDUXSwelbTuIBgKf37kaexMG5ecM4OqwiCmkyNQGGbUxHEMGTwYI5dE1kQEWUV0
bSTBoTAaQhYFPJqIzyMT8HvQVAFNlelfU01HexPBQA2iKOO4Dh6PF3GnGqYXgwIV+pSF6WrM0q9X
EUP7VSDYOv3LRxHr7sJNJZHsDKfNOJbxJZWsfPsd3ptTi+VAVJSJxRN41SBH19Rw+PQL6DI6wUxx
2rQpTJo0FtsycCwLXJtUKo2AQzabQ88ZBDSNM884FcwsVs6kpT6BLxBAObDHxSHD2XolJ86ey213
jCLjK6Lf1jm8s66MZ8+/hfV/9NN97i8Jx7Yzd9rvuOHRAXj/PI6HtMs4IrCU504+i6lLPqQpHmJQ
aRf9imK0jOrP+t+Po/iydw94vLJQkgXBIxhtf8KDZ83iT6dczZ9+e8s+20iCw5TzdM4+7hnGnLCa
YcfewvXR6fx7zRDGVLSwqrGMt2smM6yoA+hHIhFi/ANe7t5yF8lkiE0bhwJw1vZnSSbzvPaB2+rY
vq2GG7U/smnjUEKhGLFYnurYYxX8V+f0051UoAU7VUX3vqOP0sU1e3HhP4tL+St380scpP3olCW0
8zhXMJ4v1v7fJaOwN3YF/L23OZeXPvcOvortXMzf99v+89CHbcC+n1XERcTa78L3VZG2cqRtiV5u
DSnLBElDXjGWlqLNPNm5GGPENgIhh+NCowklSjECZUwcMZCTJ4zEyHSjefwokoLhWDiWQTTsRxUF
BGw0VUSVIRz0YZo6o0YMYfv2bQwaPAiQcLDwenxIooRPlVDsLFHNz+CqErobNzGkb28GV5WjSC59
SocR7+pET6cIpLo4/bJxzBmeodeTG5g/uwG/JWCrfsa01bD5T4spvmQCZ547GbMnh0GUU06YzPgx
g3GcHLZp4NoW6XQa29QRZIWsbhAMBfjeGadi5xKYeoKWhIUWUtGk/9GOXNsB07EQRRtRBgsXARHB
9ZHNmEhuEW/O28DUyaMZPrA/puCns6ONksPGkmhso6qojJRuEAj40HNpli5ZxPgJE/nggx6Ki8I4
ZgbJKxONRAkHPSz9eC1bt25F8oawbZ1sJkN5URG9QypXX3wBnU319Bs4gOKAS5/KCoIeFxEZTZbI
yuB1dK66+ByKoyGK2nMsbWnDI8jIiojsuHhd8JnwyTuzkUlw5PemUhD1M27wcBAsbMsE1843odlg
iRJp3cYVRfweGZ8aQJNELEsHZGTNQ+oQnLO+DO9MP47+Y4qZfcN0Rq59nhOHplg+tBZ5bR3tF3sZ
tu6f9Ns6F1uSWLvAZvSINfz8hLsY9It/csX5j3DFkTeydHueGTR23SfcGfgdvLBn/GeWjGTCTQJH
KFnenzSDmzmJ8vImMjUB3rrnu/zaOYq/N/6Ohqp8MXHh0ml8WDMNXoITAvO5fPIn/GhynnO/qqGM
MZWt/PXx0bx8xTsID+UNYM566c39PtcrL/1g9/KmPnnN/F0XhEQist/23xTmM4VjdgqXDWE9axnO
CGqxD+A5ezc3cQzzmc8xu2WMd+FM/slvuZkPmbLfMVT0fQL7fKZwBB8d8Hym8y6Hs/gLz3kH1fuc
9//XEgwA5Z0RLDdFc6gLb7IXckbA9JqUdg1F3iqybavE3wZtYP7AzfyqZhquLKF3O2T9Inpbhj7F
ZWQzBiF/ANPIsmLpx0w6/DCyyQSFBUFwdGwzQ2XvXogYNOyoY9v2erRAAXbWJJ1OU1oYpSwg8+OL
z6ezeRt9+/enyGNTUV5GedSLZehosoylSvjI8svLLmL+xEbO2NzOus02hlhISEriOg7FQgStPsXm
Rxcz/yKd7424gMGhgZQNMnBtsGw/OBa4DoblYAsyhiPgCBKKqhFRRDyOiKQqpLMeRE/eOOZQ8K0F
fZCxHQsHE1F0EFDAVREcFVUpR9ezNHRYvPDmaipLN5A2vFSWVuHmdDq74/SudnEByzIIBrycMG0K
/3nnXZqbG/H7PAwY2I/hw4chCiKpVIxNm9ejaiH6DByFJEl4vR6sTIKbfnoNQqaL6iF9sCSbk6cd
mXfCUmQsy0RTVQKBSsSkTXFFBD0bJ9SZQkilUQQJy3FRHYGQJCDlDASvRvu2egTbQFNEJNPCwUIR
XVzHwbRMTFtE8niwcbEcF1wbRQQcE1WWsRwRGwFHOviO3K+C4uIOzn96LtvuepQ37v0rm4YPoKl3
ESrw0RHXM37ZYziSQP/xQT4wBnHSkheY1OcTevV5lE9OHwVV/Vj/1Fv8/YNSzvznr7n66GU8cFb+
0fPCSWv4adc8ZueiHPmbu1k0+Zf7HPtOcQF7qwh/OH/a7uXRY5YzzrOnMW1MZZ6ucOkR+zJ+/v+M
DziGNYyklDY6KGYacz932x/wDM9yIbDHqvA7/Iv1DOFfXyBn/Nk7+V3B+kDYFfAPZISyNz5l2BeO
szdaPqeQfSiQ1S3IuQkYQjkpNERvHBcZyQS8Pgqa++FtHUzHlq38vvxf6KeV0WnkMEMGnRsT9LId
HBFM28Tv15h+3NG8OXs2TY3NyBIMGzaIQYMGIkky2WyK2rWrCBWUUNE3gCiK+H1ezEyCm6+7FiHT
SZ+hfRFkkelHT0CVFQxDR/bKKKpK2F+BJtsEzRD+iMLUmIf1XRsRHYeMBMW5MI7ZAR4/Q3fkkNa7
xA/L0T+dwbRyOK6CIsi4gotuGpgmyD4fpmFj5Uu2eQq4YWHmsmhaEEu0cZz/0Zy+6nqQbRXXlhFw
kWQRkAAX2zGRFRkQMS2XxlYbT2Q0K+okNjVsQUjVUbulCdHVicW6qOzVi+deeJWq/kNpW1lLaSpB
vKODwy84jyeffILqmv5MOXoyS1fVYrsWjuvg2jaSJKCqMqrrQXSyaIJDTjfwB4PohoGMiJXLocoy
Ka+Dq2cpymmsXbWBmGXiICLbDrIl4bUlJDuvi5Rt7SHg+ug2smTNLLIo5L9CQcByZSzbxjFyKK6D
XxUQJQvDdjFMF03V8utNE8xDN0b/Kqis3MGG+4+nV3cLwx+og/7NdI8pI87t3DL7HhaMLeDp9y5j
XvEYaltKOH7RfAamC5jedg/nXfYuY8cW8fqUOxly51X7jHvDL+7k5t/ft1/A/yIMH7lqH4vH/2X0
EN3dOfsA1+y3fiT5z7kr4O+NChpZyOQvFGL7JvBVrR5hX3G3/xZSmoYtGPhMPzoGoqAhYOGIaUxs
PHIBgZxGYV0YvauIpsptLC9rw2iaR+eWZQz/dDuyqNFtJQhW9uK5t16hOjKYjvb19Cp36Ght5IJz
zuQvf32CmkGDOGb6VBYvW4PhOICMY6lI+JAkP4ovh+lk0F1wZQVBEFBFL7Ir4Lg2aTVFzJZRshId
Hp1l29cSSSQQKKUZhSIjQSpoE5YUipxKNroivlQHds5Pky+MmOumyJbBcDAkGcNxER2QVQlBdpGw
MFwTy7HBMRGyWbSAhuIcWt73Wwv6ppBEQgPBRRAEBFkCTMDBdUQER8B1XRBcTFfEwYeeE0nkcrjt
FjkTgj4PCUNlzeZ1dKZSbF44H1+ogE1bt1PTuxzHBtcRsEybto4uXEHEdhxkJT/BFWUVPP/ya1z4
3Rnojo2RSiHICkbSJBwpIJmIo0kqlmXj4hKV/DjNbcz7z1xEWcHJZpFcCUEW0CUBTRZAcDEyOeJt
3fh6F5JwsuTsvIJoKh1H1/W8qQMSyWSSYDCALcmkcgaIGjYyjivi2iY9sYNvzjoYRKPdEI0ybfF8
5hx2DABae5qyR1cj3J/PAy++4UnKLrqaDf94nr6BOnKaxqWvPXfA8a5+NJG1xQAAIABJREFU8Ul+
I9xF1tZwxa/2U/tdzY08/doonlg0loU/+1ueO/0Z/OTKu3nkyesAUD4jPnXjr/bkq01UFMVAdGwk
e98LqGwdOh326+Cz/rFfBBGbKD3IX5IX/yPX8xP+/LXy509y2ZducyBZhc/iEa6iih3YiDuLtvti
BQengeS4RSQdC0lN4iWAkPNiqTquLGCRRLIdXDGLrPgQcpWUbQ+Q7GxmVbibiqEVzA+sp/rjEsJ1
Ctsa2+hMiSz3zCIaCbF582b69i5DcV0k08ZMZ2lv60AWBHB0FMmLY5lUlfXilVde5fvnnIBjGkjd
cQSfiyWY+H1RyKi4uorsKKixepoG2IRXb+KN11ZSJZZgGNsRfBI9oTBlupW/gVNtUm6WmJqmEIGE
DY4h0m1k0BM6YtykI52iR7KwU1kqtQgIIZJGBtlVCQciSHYBrV3NZCoOzRhdcN1DKwocLE654veu
1+fd3fEq7GXjJ7h5+xrXdcHNeyaKgoAkCKiuhdVSR3FZMaJXRNBsFi2eQ3d3A7FYB5Kg4dNURg4a
jE8R2bRhAznbpCuRxB8sYOSo8aSzBjYi0XCY0ogPyUgzfuQQCsNeEqk0kqISi8WQBBcrl0FPJ5Ey
BmosS40nyuLZ76N4NLozSWLxJLKiYHkUQo6EB5EkFsGh1WiVxWhFYVpiOqbpIMsiAg4Bnxc9k8bj
VWnr6ABVYdmKT+jojuO6MpZu4NdUXMfh06b0QfE2X/90hrt82JiD+m72DvqqoVN04Ydc9dKeBq8j
++1g4XV/y39XP94TZHfx7Xchp6g8c9q5TP9oHuetf4nOgihFPd2oPoPsYIUzj3qBSCp/YWsoy9Mo
d2noGLLClLt/wJxrnsWv7a8q+LfTzmNrZR/GrF9DZ0Geg9+T8SAWK/TuaCHlC3D5q8+QU1UenjWO
G16bvt8Yrnv7Qc2tINz+X/mnGc0qVnNw3xHkhdyy+LiEv37hdu9yAk1UcCFP8ww//MrjV9BwwM7g
r4qDmd/hr1/iDvngMARVRDJVxJyEpVpIgoQrGQi2AZaF5Gi4poagyLhiBjwpYtZWIuUmzUeshR7o
eSROvL6HVBb8iolfERhaU0NQUanbvJmsYdOdSuEPhxg+ajiZjI3rykRDIQoLfAhWgnEjhlAlldFt
d+AEc7R1thOUw+SSBvFMipZedTSPljh7QQFrn11CUNSg1aBNdukWJUJOCJ+jo3sVdkTrqbjlGNgk
UJoOkeq0iJkWjt+LaLiUK36cbAbHL7C1uxNV9bJi6Rp62rKkPBlcXyGymcLzgyDrbm04aD73t3an
r5giqikhICKKMpKkAPlgbwoWjmTng74j5NMxgoCFgChAShfxukEyWQlJUCkfeDzJtYvw6T6S6U5k
W2bNus3I2IiiAJJKIFSI7cD6dZ+SzBoIoopH8+IYWXqVFLNhSwNmppuhw4aTymQwdB0RB68iUFNd
iZXIUh2OsmD5WpoTMcZXjyJWn0aRRBzXQXBsMG002UvWccmlsziWRTKd5rXZH5LLWlRV9EIW4IhJ
4wkVFtPS2IA3VIApKTiyDzTIZXNYSKiSxoCB/b50Hr8R7BXSDFVj3I9sjli6g4/q80n4RVur9gn2
u3Cg9x59/y02FKr8yv4hr3EMfX8RInzJR8Q3BSmqt4ifP5De7S1c9Po/ePq086htLuZx7UTurH6d
j294ioae0AGDvi+Xof+OrTz+vQiz1/fdLd0w+RkvLUWlXP/so/zm0p8yZsNamLVvM1dJIMU9ty7m
YCiF/02kvwLH/4uQ3emE9dRnpC4OhKnM/VoBHzikgH+wUMki2kkkBzTBhyxrmIIFiDi5EKKr4cpJ
LNHEdkwU20UyHDymTKLdxBR7UfzCYJKj2xFvX4/zrw14lugkWzOYosySTRvxCwqiKyIqPpSIj4zj
sHL9dtJZA0QPqteDaWTpXVrI6m1daN3tDBs7lLZEJ6YBrqRgBBzCAwuwAr0ZsbiJZ9e+T+OPe1MV
iFD0227srgwlZo6UDLItolgGld3QvSVDPO4S7FT527yFWDmXsvJKLI/MUePHU1lczI6GzRQUhFF1
B1FRkD0iim2QbkviizgESg+tf+dbC/onHzkQfyBAOBQmndZpamoh1hMnmUyTsMCVPNiOgyjJOIKA
ZeULtyI24ycOoyluYOZEDEPF56viqCPKSDRvY3XtLLK5blRFRHAtFEVBFGWSqQz9+/WlqWEHflVG
ECREERI5na6eJClFRJVdPlq+CkX10NXVQUlBGEWw6FtVRWMqwZq6LXS3NGNkkwS720mksgiuiOtA
BC+KbeXTPqJLae/eJL0qOWwEWUNSZTz+EK6VI5HJEE/EyGV0TEHGFB28/jBiykRSXQRRRvV6mXTE
YQc9v4ueLkCXNxCO5U3A3z75YWac/MZX2nfO4cfs8/rNY05k6laY8Gorfz6z7Cufg081uPKlU3j4
7P9w9csnc+qIjcx0X6LquZ8BcPfpc5g2+CP+PfVkLho2jLWtj9L/t9fy5PffIFKY4KqXTuKOk+ft
N27K66N2wFAqWpvYxWQ4vG8jP5z0CU3Lyujd0cqS4WO5+a/3s2T4WNbVjNxn/z6FMeKXDtlv3K+K
K3mE7VQzmtWsZvTu99cxlG30/cJ9T2QW7zADgM0MPOhz+Lr4rNXhN40ZvM3BXFTHDyhhij0Sf0gl
25Olq6mHjmQ3iXgaExAkPzkhjqi62IqKZYDgSDiIHDvuSJoboVU2CNYGCdZVE64oxzm1nuQbcTa/
v55A2E/GlsAGRZWJpVOMGjCEWH0jtmQjKhapVCcIIl1dnaQ0DdHnZdvyjRRSQKYlTklFgEbPekZM
6IuxWuOJ5sVo/fuQuX0zg28YT3eumUpJI+f4MR2DjOjiKDHe6ysxqlc/+m/vxPSVY0h+kGwq1GKc
RAYzY/Kx3k6h5OJr6iIZ8tBTINGiZwjrIv6sg6RJRMYc2sX4Wwv640Z4yGQSDBpUTiYroh42mGAw
iG3ZxLMeNmzuYmt9Pdt3NJJIpLEl8t12uRT+UAn0dCDbIuBDdmWMdJaSaIgzTz+VhsY6Plm1DNM0
EV2biN9PLpmgLFpAT1sLtu2gqnnjdb8cJZ1OEy4oJmckcVwHUZSwbZuCSIRMvAufV8MbDmPndFpa
GnG9Mt6qPtiCl462dgzTAlvGr6pYHpVIdSViYQRBNcHMomAhyC4+TSBj2nhUhbbuLgYPHMDipctJ
GSYg4lEVJAFEj4BPkxDcg6/Sr38/wCejruaSp/KUyFMezZuetJcMp7AmTjpUxtKf/55jj3tvn/0a
GyupqDiwUXbwe1FucQ1OvO65fYzLLz9yOWuaS3nq/Dd2a+8s/NlTzHg030x01dHLufu9ySzcsoeu
M21QXh52S2U+SM699hla43s46p2RKA+f/TaT77uYRTtTSbvw+0t+AkB5ZxuQ9xEeWtbBoq2VGOOr
iAdCbK2oZuDSdTx/WwlDoxuB6n3GqG5u4Guk2fdBCR2UkLeynLAXf37X8o6dd8idFPEmp+2z73iW
7w76e6OSHZgonyvtcLCoZMc3YrYeIElqL53//xZqSgKUNcLQkRWYsQzhicOQQxq5nE3Octm8tY5N
29PUN7bT2SUgixEk2YeZyqCgkWEVqiAiOl4ysTiVYhizaSLtw5dwzNQJZNszBH0BTNPAdkyyVpSC
lEJPm4Wk2EiqgS2kEAUFU4ZoSYis0ICuZ7BwkBQHVVIISWEKxCI2HqNjq2V03BqnWooSjYQxiwrp
6kjh8agIjkzKyWGFsxx99vHEGrvxBGTiepZi0SKnGNg+HSebo9qysdvbEQcEeLN9M4FsMbKgUlFa
QkO6AbekhJBjEbUPrcfkWwv6paUltLe2EPB5UGQXr9dLOh3D6/UQciwOHx3hiNHjkJQjsR2BVDaL
aYEiy3y0aCFnnDEN1etFQEBTFLwehVwmhSqC61iIsoskuggeDXImjungItDT00NzYyMtTY00NDTR
HYsBIprmYd5HC0gKKXAtPIrEmJHDGDGwHxtqV6MZNqP7D+XTTzfgjxYhFZbQuLGBxqyBIYFq5igO
BiguCeMfUEGPZJFJpikMeKkuilBcUs7EiRMoLCpi7vtzKSsp4tVX/8lFF13MyNHjuHXmTGqqehEM
hDnm2MnEuzro7Dh4ZSVRtLGlPewKXc0H1JL2WmiHEA1Me3fqPutV1cDoewILqicxZf4du9cZhopk
m8h2Xg55NvBL9d7d65XVJtMFl5fud/mNNpPbf55msn0TP2+fCRhoD+XQ78ybcDTG8oGivqKaW0c+
zun6qzz7xP9x1z3XceL1zwPw1pTpzJD/TuiGPOsneH3+b/Leu7n74jwL5pYn7uUPF/2Y1y57ANsR
ufPiX/Hq2+fxqHIFr0w/jdsVP9e0j+Zv2Z9x0/KTSPwxXyu4/dJfUNVlY+vfUOcbUEXD7r9jWbXf
+l9zR174i6/OznIQMD9TYL2bm6hmG0NZxyxO2mddBQ1cwHMHlHkQsXEOUHz9IkxmAcfxPnfwa1xE
UgTpxxbO5uV9jvFLfsd2qnmZs7/W+LsQtcNEIwEiYQ8ZO4ffI5IwuvD7gzhmmpFjShk7phRNCCDY
QdIZgaytI8omn9Yu4eTLL0c0XJxMitLifqiSB8E02Bz/hIqKCox0Fq/iQVIVdDtDykwS1zJ8enkd
TXoDWxu30tDUjJm18ahBfKoPN1uC16vy7qvv0LQsxxXTRjC17HC21W3Co7fQ+7sq9b4EyWqZ1miC
WFogJ0SxUmlClogadmgtMRkpxfBYFp+KbRQEqwhO9NBLK2XsyGH4FC+dmzfTkmpg3sdJZvz5dIaX
VLJjy0ZadrTQp2oIktYLf8KiNrLkoOZ2F761Qu6Df3zI/c53z+D9ebM54YRprFy5gvLScspKy/Bq
BsEiP7l4D95oIa07GhFEGcOwiBaWsWxFLZMmjsVxLDweCVG0EAQTw9Qx0pDNGiTiMULhMGF/ENd1
sHUDBAFXclEEmVw2hyLJ9PTE8foDpNJpPMFwnt0jK0iigGDppOKdhAMe7JRNZ0+SmG1g2S71tZu4
9/f3kbIcDEXEkRzCXg/9qss54aTjyOYSiHqWbGc33oIiOnu6kWQJVZNxXQHLdDjv+xfQt08f1q/f
gOE4jBwzBkVW6OnpoqAoQlt7G+V9Jh1UAm/sm0vdk358Eu7cc1AGPMKf7+/iqA/vYsQbj6JYB276
6inoS2fhIHZUH8Vxc28+pO/3QGMDFPTskSJYPu5yxq94gmcufI+eghqSwXKCyWYA+r76e1Y17nvX
Wx5OcsXSJJacD1gXv/Uuf/rBlVz37KM88b0Lmbb4Q9oLi6huXMf3Nz7LxXeN5c8/2cKQ9a8xffYN
+4y1fPwVvLXssYOa25OFCe7ed/gWEvI3KEL238ZqRvE6Z+z3voLBVN5nCZMOsNe++KwZ+oFwu+t+
7fm9Zs2P3F+EbmLWnNc5bcY0Vi1dS3FlCZVlVQiqTGFBmEy8nWA4QrKpHdu1yJlJwiVh5n+4kqmH
H4/gC6C7Dl7NRBJz0Jkm50IikUJyFLAFCqIF2KJFzskg2OATfRi2jumYuLg4tksubSILKo7sRS8y
aA200KPEiBk9IAuoiFgZuCVxGydVXECkpZg3Fj+HekMj8ZSMLpZhi+10944x/p4JdPZ3GRIrZFij
j5QlYGkRgq5IrL6O7p5O/NWVyL2KCAQ8XDDiO2TXdLLB6WTcuFHUiBqtW7qIllTwoP08vyq483+v
kCvIAV545XWOO/4Y3vtgMd1dPaxZ28jYkePIpdoYPKiCcMRHW/tWikqKcFwwckniXT1sWr+BZHec
stJyRFGkX00lqgq2KCF7XCL+MJKkMHfuB0w+/CgSsW50PUekwEO4wIvtKnm3LsdGtx3MVIKyXmW4
eNhR30A6ncW2HcrLy1F95eRwSIlJ2nM5/H4f5WVltHTFyYT9pHImgqjg9UtYgsPUk07ipBknEO/u
orioCK8vgGG6iJKAbedwHR09l0WVvTiWSyKeIxIuwrAMttfVo3pUEqkEuWzeuOVQsOnd+xBOe42X
b3e59KyHKP+Jh7tmZhnWbxlnXjiRZKCcYGqPE1Jb6UgkS6f0gWr+cv8SOoqHcuYr5zJwc14iOR6q
JJzI38V+dPj1dN98Jv1vuJvVoy9i08BTufWO/X9OL577Gue++B0Keupp7D2JttKRDBq0jsaVxfSt
n8eGwadz4TPHM/N2lx9e/Bh9qq+kpWw0y+SJ+431h5sXUzfoI+6/rpHL/jKJZ5JNFP3kFzwDeH4y
k4W7PjdwMWMBOPeFM5g39Q7u+9kOLvnrkTzwky2c9cpZRCKHZpz+PscylXy9QcamlVLKaDukMb9t
DGQTh7GEwzi0O8lDQTxl8fI7/+Koo6czd/5y2jtMVm/tYewgmWysg1HDq9ECKp3dW4gWRnFNEdPw
0tnmsGN7D7P1hRQVlqBpKtV9e6FpYCsKIjah8hJSsSzz5y3kyMMn093ZBjj4gx6ihSDIIobuAgLp
bApXdAiXhhEJ0rB9B0pKJGqFGFI6EEVVkSUJI9fOYG0KzR/XckP17czR57Al0IjPsbBNmYhaSJu3
h4m9hpPxxNBKvVwVvo50KoashTG1GJ2TW+lSdDzxAOXdBfh1FWWbQlo0GScU4Fnl0iz1kNV9SGRQ
Q/+jHbmFhRKDhx9F3ZYtDBwyisYdTcRi3WTJUTOwBle0aOvoRPXIdHXGKC4twbYdliz5iKMnH046
lWPrlnqqqqr5aNFSQmE/RUUF1AzshWmY6IZO7169aWjcwegRI9iwYR2RSAHZTByfz4PPq5DKGhQW
FuLxqDiOhapBWXkxLc1tNDc3U1gYZuWqNQiCSyQapbqy6v9Rd95xklVl+v/eUDmnrs5xume6J+dh
AjPkMCBJgllgV1EX0TWCAdAVXMXAYlpdEMEAkhQJkocwOTGxc55O1d2V062bfn80DCKuocHlx/NP
V1fVOXXqfLqf+973vO/zsGXLc6x2u5mYGEOSRCwWK4YJetHEKos01bYwOR5ncnwcybQRi/WjY6FY
KmK3W2idNwevx082nUVARFUFHE4nNtNBNpdD1yEYiFBSNRKJ2TvkjI1V4f3u4/Cjqzjrrhu4/Wc3
cOLGp9nY/z3YkmbLphtmymExCcZ7WXToVwzVbqDs2zV4z/kpzbXraHpvht+KD+AO5Vny+1uZ1/47
fOlhTARKNg8jD1tpXh7hsl9dwJZNN5Bzhtmz8uNsfP5rHFj0AdqO3sdl91xwfE3VIzNkcuNlJoG6
XgKJPqqvELj3+d9x0jNfJj4lMbDpBjrnvouKR3/yhu90i/0zHPrKc6w/+n1++YEnmCybEVVbc8KL
mKbAyvddSWi663VjorFDXHbPBbTPu4D9Sy/nK1+3kvZUkWmefalkJaNUMfq6597phA/wbh54u5eA
Jyhw4iknMHpsgrnzl+EcShFLjqPoBeYvnI+iJCllVTRUIEU0WkY6kWPvnp1sWLeGfE6hp6eP+roG
dm3fi9NtJxIJUt9YQamoUCopVFZWcOzYEAvnt9HX14Pf5yWdSuJxe7HZHOSUEj5fAJt9pivfajeJ
lofRR0uMjEwSCvvZv2s3oiji89s448QT+YXyM9qTPXiLBoLoRpZ0SlKGIS1JxBdCTLvYpKzkdn7O
g+7f4OisJmx6KKlpfHYLyxsXYXiCTIkFdCOBPZ3H5XJjla1oOQNJ1rE5AmSy05S8by4YfNtIPxh0
MjkxztRUjr6hvRSUEvV1FTy/YztNl17IoYOHaG1rIZ/LYrPaGewfpnluC6IgkoinqKgox25zoGkG
ra0Lcdhd9A8OMBlLE4mGMPQsFZXlVFfX0nXkCGNjY9TWVWKzudA0HdUATyBEX8cR3B4nVVUVgIHD
ZSMSDeJw2ohGI0QrNjE8PEAgVIZoCtTUVCEIUFVZhSgKmKaKLNsQSgpNTU001dcRDQdwWW20t3cw
d14rumDD5XGjayXi8SxpKUc2kyEcjmCxSOTyOXL5PKIkIegmpmBQUjUkafZm1I3JrUxEFzI/Mkn6
Iyu4uvU/eWHLqZx75yS69VZ+/NkOVj/7HfasvIrG3qdob7uQS++9iKH697Nj5cdYu/VbZD5+iIv4
Ic78FJ70KDvXXMNZj38SAZNFB+5m05YbALjzw89xrGEtm7bcQFlsRoPfn+zHohW599IHuPTei163
tkvuvZDW9le0ju+GF24wOfHFbzA5sYTdc67ktCc/x+E/k+298oR9pO8f5+ztH+DlJZfT8K8JWm75
Jj1NZ3DGGTMiZ/de+gALDt3D4YWXcc4frsKVn2SibAFbTrqR0coVNPY9jS7KjFSvIjc2+07XPyf8
V/FjruJjvPFi9U6Aj+TbvQQA7B6Z8YFxEikL3Vv2UMhbKavxs3XHLprraunu6aOhuQHVMLHaBAZ6
h5gzZw6rgNh0kqqqGuw2O5pm0jJ3AQ67g76BAeyOacqryjGMPNXVVUTLy+k+epTx8THKyoO4vb4Z
TSxVxePz037oZULhADW1NZiqjt1pI1IWwu6wUllZSbQ8wtDQEIGgD0cpx3eCadK2AgFTxsQJKEgW
BWedl8XrylgfXMd8oRXFOcp3Y/fw2eWfY05PA3KZn5gywXg+j5lXGMvlqHb68Di9pIsJEsU0TsGD
KKtIlhIgzki3vAm8bcbo42PTdHUMIuBAlvwMDUzx3HO7EAQXo7E4jc3zkC1uOjr6UVWBTDpPIZPH
Ybej6yqTsXEEdCKRMPFkipGxSVIpBbvVy1D/CEODxxBFEdPQiUQiLFu2nEJBRUcknc3j8vg4sG8v
ktVCOBpFM3WUUh5DV8jlMyhKgVKphCgKVFaWEw4HcbocVFVX4fd78Qe8aLqGxWLFZrNitxqccfqJ
GEYOtZTB5bawbsNqEDREi0ZJL6DqCpJFQDNKhMoClLQ82WIGSbbi9viw2hzIVidWqwsTC6U3cUE3
mio4/b+7ePaZM+nvm4PPl+Lc82YiuUxFHUJOYc3OW6k/M0nb0QeYiM6UNRovjlE9vI2CI8julZ8g
OnGQJ0+/hZ9+dA+7Vl9NPNiEIYg8dfqMKUrOGeHDd57El6+fkQ8W9ZmKo7qhlxitWM5pT33+DWt7
6rRvHX+cdUW5+r/mEA82Eel6GcXmw58aIBYMv25M/Pw5lB9+GoA5vX/krDM3ULQHsJWyx+eR1QKP
nvNjzn70Eyh2Lwl/A9HYYS699yI+9IuTOe/3VyIZGvuXXoHNNnsxu+IrUskJ/BgI3Mj13Mj1bzho
fSfBhvJ2LwGAqXia9vZ+EqkSoVA9g/1TbN26D0l0MTY+RVVNAx5fhK7uQQRspFM58uksFtmCKJqM
jQ5jGOqMN3Uqxej4NJnMjP3o8MAxxsbGULUSGBrl5VEWLFiApmkUlCKZXB6LzcHhAwewOZwEQ2FU
VUVVFXStRLGYo1jMoapFJAkqKqKEy6LMM+vxWhw8OfwcdreEbJUwkfFa7aRTMRZf3EpoGgQlT0uq
mQ/P/SC/Gv45Kd80llIOpw6aZcZkaZHTi1+XyCrajHuW24/Vasduc4BgQdVnClLeDN420s+mdDKZ
Iul0BkwVEYiGI1xy0aUEA2XEptN09fQTT+ZJJLJIohVVVcmkEiya38acpnpq66uwWAUkCURZorO7
hzvuvJumOfNYtXYtiUSC8bERBgYGMAwTm82OPxChqqqOfKHI0qXLUFWNYrFAMpUil8vT3t5BJBym
sbEJj9+HrusYhsHIyDA7dmzloYceYGp6Gq/Xi8NuwzQ1NL1IoZjmwoveRXlFGToabq8LXzCAZLPi
cNtwOGQCIT9enxeXx02ppDCntQmvz43b60WUZKw2Fx5PgGMjExQLOmNj8Vnvb0F2YHcU+MQnv8Nl
772LRV1H0AsmA017CE71kHVX8LUbdc7a/DBFl5+MZ0aIq6JxHF22UTf4Ah+861SC8V7Gqlew4cWb
+Py11/PAfz6HaBpceu+F/O68O3h+01e56bos//HlAgBzu15Tvqwc20sw3oshSOiihfsuvpe0p4pP
/tdrOu7u3ATBeC8/ueoABeWrHJl/CcF4L7r0+uqSKx6/lWC8F6uaJxifKfe0FxOcsO2W4/Nc8NCH
+NT3arntkz140qO4chMYgkjJ4sSdGaNkcXLTNxTWbfs2fzj7p7Pe2yOvuOsGSCK80sm2kl18kttm
PSfAD/jE337Tm8AtfAaAJRx4w2tv9R2KPktqsQpuYqPTJKfi5DNJMA1CwTAXXXAxoXAFsek0nV19
TE5nmZiIYyJh6CaKUmDxwoW0NDfS1FSHxSrMCGGJAkc7OvnZ/9xJy7w2Vq5ZQyw2xtjYCD29XQiC
gCjJlFdWU1ZWBojMm9cGCCilEtPxOLlcgfb2DsLhMhob5+B0edB1E0mSGR4a5Pnf/RFxW5FclUI2
aFLS4yCYaKpA0O2gtq6aigovVotErdjI6crZVNSHuU24m5GyQapEF/NDK3C460ibJaKLg8hlJm6f
H0G2YLE5MJFIxFMUiirHRt9cKvFtq95pP9BrWp1ODh85go6Aw+ZEU3UOHThAqZTnrLPPIJ/Lk00l
ODbQw6mnbsBmMxka6GHp4qXogoGq6Vg9fl56fjuS7CY2mcLjFFm1YjFqKUe0MkrnkcP43D48Hh8D
QwO4vG4qK6sYH4vRNK8FrVRgMjaC3W7FKlqZnkowcmycaLQCp9OBz+dGkkFyOhC1mQtAV083Nref
Cy+6DFWUUVUTq6mwc/s2svE446OjxCYncbp9JBJp9uzfTbSsAq/Li6bpyLJIRXkYWYJoNEI2W2A6
nkAp6bjcHjzuALLVztjoGOdcct6sLuvnrviIuXzvz7j9ym2U/H684wM0RQ5R/Xknuiax87MRBupP
YtXi52nYMEFk7ldwFqa58QaT61/pnh8rX4JhsXHX+5+kLHaE+vcVCH/q5wQSfdQOb6Nz7rswRBl3
ZpRnTv0mg/Ubj48drl5DzbE3Svnec9lDaJKN9//q7De8BrBr1Sf+4vi2AAAgAElEQVSYf+S33OL9
Ooy9dsh89ZePoP13O49t/iGD9TMyw15fkove/Wuqqo+h75okEWigaA9w5x0fo3p4++vm/fCVP+HO
2686/nvViil2XHXurPb2BkE4/k/zp1LJT3A6x6jmSu4AYJIwR2ljIy/M5mP+qfhTTX0Bg6/y9b/4
vu9zDe/nl4SZ/oc/YzbVO9+c+JZ5fvx8ujrHyJfi+Ly1FIwCnfv2Y+g6m885k9HRUTK5NGPD/Zxz
xik4rAYDPR0sXrYc3dQxBAHZ6WHbizsRJTfjsSQ+t8Ca1UsoFrKEI356ujrxujwEA2F6Bvqwu2w0
NDQzNHiMpqYmikqBfD6LIJrYBDuJ6TjDw8OUl5fjdDrx+XxIkoTVYcEsabS7j3L+8EdoKCym/SMv
4U2G0XUfMdcRnthxL6HJCMoIZLqnUCpC7HY9y69dj9Icq+bUkfVYxoOUvDKBegtWa4a6QAXqtMp4
KouRF/B4RVyeGkxLgXvKHuR7Lbe986p39h3Yg2Qxmb9oHoODfdTVB+nrGqKhOkBD8xoOHznM1MQk
J65bj10WiccTYObJ5XKkkmlKmoI/HKSn/ShtrXNRNJGa2noO7NlJbCJGWVmA7p5uImVh7FYHbk8A
60QMRVHJZQu8/PLL9Pb2sOaElVgsFgKhEEZBx+3SKS8Hvy/I4NAAilIgkYgzr20uuXwOU1dxOOwk
EwkssohS0pBFC5piZXgwxvixEXLZLHX1zcSTGTQ0Tt50NslEkrJIOUePtDN//kKCARdKIUM2k8Hv
D2Cx2skXS5RFypmaTpBKpMhmsrPeX/nDLXz//XHW//pLTC1cRsXhF/jdBXcRvH+Kxj/ei3jFHC7w
/oK9dzQx8lgdPV+YwlZMsWz5Tvas+CiNvU/R0XohaU8l197s45FzfkzhuzC2YiPaASfZhkbCkRhD
gw20tj/Ih+/cxJZN17N/6RUkzlxLbu0CwpechaPw+iqZVw9296z46MzfwdIr+eBdp2FRc3S3bKYs
dpjOlnPhz1oUHKqVn73ndySCc1i941aa9a38ct1v+fntH2fR4n2cseWzPL3qMwiP9vK+nWfQ3bKZ
Xas/yfU3CGw74d/5jyd/wfW3Czxyzo8BqNSzwLmz3t9X8ae19mfw5PHHf+QMzuSJfwrh72E5K9j7
ls1n/pWo/FPcOqs5B/6sGe7vHjfez6HO3bS0LCA2NUllpYOO3hFqqwM0Nraxe89u0qkM69evw+92
Mjk1iaDnyRUK5HN5coUswUiY7vYjzGttpqiKVNXWsmfbC4yMjFNdFaW3b4BQOILdYsfqcGGzOVFV
jUQiycFDh+jvH+SEE1ahaRrR8ihaXsPj8RKNRgkEgwwODlNUVJLxBHX1lShyDu+IE4I6Y2IRq0vF
TCiYpg2r1cJoLsXkfh3LZJ5Q8yrkRDcN00s4fWGc0WgSMRJCeW6KtXOW4SjzoKdLqGNZXGUecHjR
siYVNR4GB1OopRym+Q71yHXZbcxtraPjyG7mtjZSHbFhM6OkpvPU1PqoLFuIzxtkz+69lEpFcnkr
oJPKKXQNTtHQUM/ePd1kcxnQbYiCRDgcYU5D7YxDFRDyhxiPxcgVpgiGdDyBGpwOO/39nWzadDLp
1BTZVIrJiQlcFiembMFitxGyhdE0DdVQMQQByWqnt3sAl9OO02klMRnDarUxp6qcgf5jWKwSqgy9
3Udxu9zkS3k0oUS43E15bQCjUMIiGYhCiU2bVlMoZpEsCn6PFa8WRtdtuCUrFVEXSrGAlk0QdLuw
hmevpieYJut+/SW0H5yJ87O7WHzgbha5nuUJz2c49ekvIj82ozL5/L/sYKR6NWc+/xleXP45BMFk
37J/RTQ08s4Qhxa9D7uSorHvGdqO3s+zJ/8HhijR9sIv2b3yYyDAvZfcz7vvv4xNW25kpHIFXb2b
ufTmNWiSjaSvFn9q6A3rm4y0MRWex9KXf07WHaWv8TQ02UYi2MSelR/nnta1XHbp6VT70xxLevmD
fhKqxcUXwufx3Hs+QfwHnZz96Mdp6XyElzZ8kQOf/jf833sWAHd2grMev4azHp/p3F27/bus3f5d
Mu4K9q6Yifa9h78/670dpJY63vid/hRn8pddxN4KvJWE/+foopkWut/0PPUMzmqc3RGkpXk+HUcO
sGJlNSG/HUmsIuf3UV3jpyq6BK8vwJ5d+ylkM1hwYrWKJAsKR/tHqK2tZefuwxQKBURsiIJIOBxm
flszpmZQKpkEAtWMT06RzSUJBFX8wVpcDgf9vd1sWHsS+VyafDrLscF+/E4XJdECVp1wxI1qahQM
ERduLLLO2ECSYngCn6+NTWorv3eOUbOyBiGWwhAV8jaDA7EjrHOsJ2XTCNvHCZV7sAtWqpVzuLny
e+wr7eC9524mMGVDzFpwl4VJuyaQLFZMWcMbDJApjJHPpohUevG4Z1/gAW9jTt9qA5fTycknnUZ8
Mg2GhUgoTF19FfFEDJtVpru7E7/fR1tbK/NaW1m0aBGKUqJYKvLi1hfw+FxEoyFsTomu7gMg5JEF
jWw6Tio+zfbtW/F63FRXRDmwbxePPvp7Hrj/XqanJkkkprDb7UyMxVi4YCkjx2KMDI1w3333z8gz
eDzU1FSTSiXw+VyEo2V4/H6GRsdobmmhqCicfvLJWDCRdA0Mjb6eTpYuXciG9atQizny2TQTo8NM
TA5TXRNhcmoEUTbweO1EyiMzJZMiDA0PMDJ+jEwxi6LrVNTV4Q1HsLhnL8j1pHIV0fEDrF59Hj3N
M23/wrYRznzi3/nNe2Y0eH7wb+1kPJVcfvs6Vjx/Gx//4XxOct5J+EyBg5+8lpeXXE7l6F605bXo
16zid+ffyUD9Jg4tfB9T4bmM/eslrNz9Y87r+zy68kUGBn+M5eB78GRHKdp83HvZQ8cJf8vGr7Ln
yV+hVcy0kJ/1+DU09D2DoxAn7wyzavcPObDkQ6zddgtL993Op579AesahziW9AJQWzvAv902l8lv
xhjaGiI01Yn5vjbuu+Q+lhy5m6ODy5mILmbdwI8oWV2MVixHsXq444qXuOOKl9i16t9IBBq4/PZ1
XPmz1cgTsz8v+VuE/1aj6y942b5ZrDve1TCDh15p1norCP/NwBSzePxWNr/rbDraOzANnVDQTV19
mGRqAlmGnu4u/H4PS5YsYk5LM23z56MoKoWCzo4dewn4y4iWlWO12enq6sA0NARUMulpUokpdu7Y
StDvpawsyP69M7zw23t/zfj4KKpaeoUXxlm8aBlDQ6McG0/z6GPP4guFiHidNFSFSWRGkCMSwWiA
Gns5wwNH2ey/iAUWFXlBjnojSIhpiuks6WSCBa1zWbF8Kblckmx+5kA4O5znK7EvcjC+jz6tB9Hr
wtZsZ8R2hKyzxNDEEIPjw0xn4piywJx5c/EGgwjWNxerv22Rflf3AebNa0TJO2iqX8zhg91oep5I
mZeamnqSiQKxWIyVK0/A6XCgGSXcHieZTIbTzljC4FA/ixcvID4VAzTWnLAcf8BBwFOPYZoUlTyb
G05lKp6korYaQ1Po7x/CHwwxcmwIQTBJJpOYokQ2WySXK5HKplmyeBkH9x9kydKFBEN+7A4ZfzhI
Z0cPtbV1zGtro7P9CB6Hk40bNvCHBx4mlclikwVMTcFmhUJOoaI8iCBIjE/o1LbMYWx0HK/fi6ar
NNTW09FxlAVLFzMxMs6Rox0UiwpdvUOsXnMCDQ3NTMcTTOVmb4x+9ae+Tfy7RQTgijvWc/O1aU55
+ot0t2zmA788k6S/nkSgia98/TWpBkOyMFS5js1nbqRj3gV8sO+3qCULoqFj0QoMnvMT3n/36VjV
PKYocPbHzgTAvqePb1/3SQruEIKmszFzAw+8+zcMvWKF2NW8mZc2XIe+zcajH33v8bz/+q2vVfGY
wL/8zxoOLvoAdQPPc2T+JYx++ueIV7+We7aVMtQc28FHf7qCBy/8Jd4nRzm5/Uv8z4e2whBcf0c9
AM9c9CsuemBG90fYUMml7/kFECJbkyQyeZSS1U1ZpQi8JjXxj2A3K16nufPPxj+DiE/lGbay/vjv
4/z9Qnp/ip2swk6Rxbw1xjeZ3Bimp8jUxDSrlm/k6NFeimaKypCbyopm8jmdsbExVq1ei8vjRink
sFplikqJJYtXMDDQT1tbK/F4DFkWWL16BT6/h4DfiaZpZPNFTj/lRNKZLNGyCJY1SxgbG8ft9jA+
Nsbk5DgWWcZApKioZLMl0okUc1sXsW/3HpYtWkDU78Zmt+CpCDC4v4fGRYupsgURj+0kFYnRvGYx
8YrDKAMSFVUR8vEUjnoLKnnqaiqxFw1G0nla5jWQ7dC4uPZM7pJ+y5o5pzP4/FGaFrcihGWef+oF
4gUFrzzEqhMWMLd1GbHpIXLKO1Rl86STN9DR0YFN8jE9lcZqNVm9uo2R8U66utsZHppgxfI1jI8f
Q9N0RNFkdGwYl9vFvn0HGRsbRTREfD4XgqCDqdPTPcC8hQsY6+6morqa3u4eFFXFbpVx2S3Mb52D
0+cjEvaSSiaorKgiPp0iXyxRUFSCwRDhSIhoeQgw6O/vRtMVPH4nkWiY+x54gMsuuQSfL4ioaqDr
rF+3mqefeoZUUSE2PspgfzdzW+eRSqbo7O5n2bIVFEsgSWky6UkOHniWfL5IbW0Ne/e0U1FRzVln
XognEKC9o4cnn9lFNvcCgiSTzytsftcbdeD/HhxeM86+c37CaNVKABYduItVu3/EU6ffwvc/1U/K
X8/77j6TFzZcRwXdPH/W1xgtzuFLlqt5/MGnWLP2RQaXDVP/CgHP6XmcYLwbq5rntqu7uPq2Fr73
uWE2bbmelbt/zOe+PVP33jn3XOZ2/oGjrRey+ZGPYcoCkamjeMI5Gp/5Bef+4aPH1/itz0/x+W/N
lGb+6DOdlA0doKXzDyw+eDdb3v8dQt09tJZ/l+GEl5N2b+eOW3byns+uJhFooKXzYZKBBhr7n+Ga
7zdw66cHmYp/i0AggfBQK/3f+W8e/t6pfPDfT0H5d3jijO9y4ZiOIZ2HDKw8vG/Wf7v/KOEn8BP4
/6QO/k+xjL3se8XsxMvfZ9gTI3JcbA5gNbuOP1awMkkEFzm6Z3l3Mq96Lp27ekHxoBYTYNpZtn4B
k8c66Ovro693mDVr1jIxPoQ5ZmKaBiMjIwC8/PLLjI4OY5FMfD4XoGEaGtPT3bQuWsCxrg6qamoY
6OtBUWfsX1x2K031Nbg9bjwuO6Ig4XS4yWRyKKqJomgE7RZC5UECFfUomslE7yiiCkGHH38kxG9+
+BvOuPJyhNIEDjWIFA4x+QGZ8G0RCtlerKJMd+cRlp+wjrHxAcb7R6iZuwizDHL6KHUvN5Nd9CTv
PnApnz52FV3bkkSXV3D6Wedh9QTpPtjPc1te4KGH94GlROeGEaie1fYCb2N6x+GyEy0Pc7T9MC0t
TYSCAQx0Fi5eiGGozGmuJxT2YbFAVU0Ui1Vg9eplXHzxBUSjFTQ2NAECkmRFUwW8njBqSeLw/kMY
yKRTeWrqWlAVA1m2YbXIhMNhitksomBQWRnFYpEQJNi6Yzu6qeNy2fB6XezYvo3BgX6CwSBOp5Ns
Oo0oiixauIje7j4sFjsul4dsLsuHr/wwTq8dfyBItKICSZbo6mrH7rTT1tbGvn37eeH5neTzBtU1
TZx62tksWryUpUtXs3btSaTTBXZs3829v7qPXDqPz+XHUA0qyypRcoVZ76/PN3OAet1XvsyS/T/n
4OIP0tlyLl/6hpOMp4rle/6b6MRMdDYqzMV9sIOvfs2C1PQTVt30WX74X59j55pr6G4+m8MLL8Ou
pHHmJvnmF5Oc9oqOzYUPvA//n2jpAMzt/AOxyHzqBl/Anxqk84TL+K9r+jjjJ1ew6bmZqP3ma2c6
jT//rTBpz4x5ykmPXYcuWVh88G76Gk/B3jvM1f81h0d+/AiZ73yT51aupyu7ipuuyxJI9LPgyG/Z
v/QKbrzB5NFzfsKl95zP1NqttF+UoPKu+1DOfIyyNUUe/tLvGdt2I53zzufwocV0drRS/OMkCe//
nUn6/4+ED3Aujxx/nMb7d40pYxLjf6kTt1HiJdYTIDlr5yyH5sXt8vPy/iPU1jYSiVSgFHQWLF6B
acL8Ba2EynxYrFBTX4HdIbPmhJVcdtklhMt81NVXYgoqgmhiGBp+vxdd1zmwdz+maCWTKVJd14iI
gCiC3WohWlGOUsxjtUi4XE6cLjsGBs889ywIBmUu8HntvLhnH/3jSdzBciwuG5niBHh11i6YS7z7
KEIywsX2U+lV+1m68lQmotMEAgFMwcTjc9N5eD9er4u5rfPo7e3l6ce2o4wqlNfU8cXAl7GWiUxs
nmL5+QtIjylsf2kX9/zmPpSChs8TQBZk6qvryWZnzwvwdh7kOj3ExuK0zK3DYlfRU1nc3jry2RwL
FrZhc7jpONqB1x8gFHJTVhGgpGRRlAIer4DV7mJ0aBirzaSqsoqujk50XaeltZXRkVFUvUgioVBR
2cjUVBaBEqYhoZc03E4XiqZQKCpk81lOPnUj6UwWj9PC4GAvkUgQq83C0aNHaWpqJJstEIr4KQuG
6e3pR8JEFkU8LislU+XEUzbx8GMvYHO6cHk8WB0WVF0nnsoxODxCVVULTredYjGHoJeorovw1HMP
s2H9JtZvXEk2laGrq4vyiAOfu5LW5igej5d1K+bMen9TqZnc+U1f/xobU1/nIxOXUNH1B5K+uuMp
nfvffQ8rd/2QuqEXXzf2qPU0Nm65kec3Xc9l91yArZTmxhtMNj53Pb7UIPM6Hyb96bPQHpWY2/UI
WzZ+lRNf+AaiqdPeeiGt7Q8enyuhRrn+BoGB+o14suNs2XQD197s46EL7mLRgbto6nuavCPEZNl8
nPmZktHysX3M6/g9AJ/8+RUsV59j1VUjFB+88XgXcCzSxvwLh0netosznvh3dq98pcY9DqdUvsx3
3nMnK374TeYfvpc/lD3JwoO/JHVkjPRknhjVtGfH+NDuWW8vMGMraOXNtcS/3fhTff+/F1tZx4Y/
OxN4FZdxL/Bq3f+P/+H1aJKGLMOiJS1Y7SXi8TS+YJRMIknr/HnYHHa6O44QCHnw+awEw82UiipK
sYTbY2KzexgbGcVuF4mWldHb3Y2u6zTNnc/wyCg6ecxEhmCkgkxOAaOIYQioxRIelwtF1cnksqTS
STaetA5VVXHJBkOD3VT7y3CoIn0TXXgWWdkv92MpWYm0+kj1duPOLMZRdBBrGuWa8Ptpf+8e8r/I
IDhk7B4HNllG1UsU0wV6e/poqVyCy+WnlO2nKubkPfYLuW33bdQvruWElavQzEoOdPcSDTsJ+pto
ahDwhRzEamd3QX0VbxvpZ1I54vE4Z28+CyWfoW1RPbHRYzP5NMEEQaO+vgqbw4Uoy2AoiKKBKKnU
Nnqx2exUV7mwOzxIooXmuTV0tHfxwtZtJBI5vG4/HrcHXS3h89ppbKhhfDxGsZCnurYKu9NONj+N
zWFFM1UiZQHsFhOPpw5N0xBFCZ/PiyCKHD54mD07X2bThk2EvD7sDiculw2nQ6agpLjgoot45Mld
DB8bxeX1IlkEJmLT6LqFsspaEulJJhPDLFjQTFlFCJfLTslcQENjAEnUsVklFjlrcTnsGIYDrZBH
kiCTe3OiYPHgHL56w4zxPFtgomwh7uxMk5JVzfPu+y/7i+NeJdZXf9YNvsgZf/wURn2IWHQRR47e
zSO/2EzFl6d5+dHL6Wi9kE3Pf427P/Akzvwkre0PMli7nh0nfBpXbiYVUD/w/OvmvOChGTNw49Mr
KX12M9GT9zH/yL1kPBWc/OxXCCR6ue+S+zEFgR+u+B4P311g05Y7AehtPI3I5FEmf5JiuPE0bvlc
jEvuvRB3ZpyaY9tJnLqCj99XhVWdccxaefMXXpN9AAbqNzEVnvum9hZ4xxD+XxODW82uf5j0I3+S
3nmrUdLzxKaGOO20zZjaBHPb5jCZGkMyFEzRg4lObX0FFrsVUQTTKCDJEhabQP2cSmxWB5UVYTwe
PwISTU1z6Ojo4MVtu5icThIMBPC4HBRyWWqrK4lGwgwOjYJeorqmGrvDQSKVxOVxYAomgYgfm1On
KexDzEmIukS01uTOwv3cWvol1mw536i+Et0wSEs55ltOw158kMPebpyL/aTELFhl3EEvFhMm4zE8
hp2ySIRJdYjx2ACtdRVEyp00Od/FAk8blWUBgikds2Bh2cJ6XLITTShRhx9NyOCU35x39ttG+oae
57RT1iJZVJwuUItJSmoBhzuM0+XFNA1EWcYQRdBKiBYZWZKQ7U5MVFQlh8tjRSsVkC0y2VyGOc3N
rFweoKAodPR0URaN8tTTT2N115EuxkkVs7i9QTKFEkVFxW1xY3PayKSyKJkCbqeI3W4nmyuAKOEP
BikUM9i9dlbXLsbuNGld0IAoWTBFkWwqQSahcPevf8OiJYs42t5JOlnAH3DjsdpxOh3UVZURG5ug
qroC3ShQ0vIUc3mWLGwlny+hFHIUc3nKwmG0kkomm8HAIBT00dffw5sxTPzMLRXHO0YBXl56OWc8
8e+zmsteTLLknluZ7/0Znl/lefnCemp/9jjzfheg4zZmyi0DDTN6/czIMNQNvYTeEPqr8+Z/OkTy
kReY1z1Tbvm+X73mxXvxb99NIvlNstvKSeywc3j+pSw4ci9NfTPGL+c+/BGKDv/xDt1X4X369Tn3
Vwn/VZXQ+oEtRDfNXobhnYa/Jgb3db78D883j843s5y/CtPMsWnjCVhlDdnpQMkVKBRyhDw+HC4n
pqpitc2UMpsGiBYrkiEi2UQ0U6ekFPD4nSiFLC6Hm2w2RXNzM8u9QRS1RHtHO+Xl5Tz11FNEAh5K
bieFQpFQJEKmUEIqalhEiepQOYVcgVRmCodLxOF0UMyXsAkSiqKwJNBG3ZEwS+rXkS6VcEc83Ddw
J6Ks4hM8HB7ehbBzivnz5vH4PU+x/mun4XLaEfwqDgTEORbGzUnqbFVMUyBXShMUQmwMrEOZStNt
HeBH2Z/xLu9ZrNCWYDPsmCUQwg6KxdkLMcLbSPo+nxuLRSSfjuP0uEgkZ6QNbDYr6CbIFkbGBqmt
rUOQpJnyDkHCNFQwwdAMbHY7GCrIIpU11VhlJ4VUht27ttG2YD7+kJ/zzzsdv9fLSy9sIZkqYfcZ
bFi9gmIqhUU22ffyHiwuKwsXLsAo5ClmVfSSSU9vF83zWnD7nMyfNxdJFFFLOp093UTKyhk+Nkxl
RRXXfvmrXHftl8hkSzz79FM8+OB9zGmqZ82q5ciCTj4xxtTIKPlUglDET1Et4nC7kEyTqYkkpZLG
jhdfZPXq1TidTtxuN4qhMJ1Mo725HozjpievYraED7Dk5V8A4EsPc/MnUlx7sw9NsiKHSlRfuY5v
fLnIv3zkNnZcHQU4fjfxn+8Z5Lqb3K+b66brstQNPM9l95yPtZShrntGoriv4RQ6Ws/HFEQ2P/oJ
vvQd+Fp7B0tf2ssXfns9rYDOZ5DcMwYuNiXN/Rffw3D1Wr50k+v458qagi5ZMQWBe+/YT/hXf+T0
LZ/HWZxClywYgoTF8s6I0v+ZuIlr+QQ/JEiC/+FKjtLKNKH/NXXzj2DPLHP6TsmGy26jmMvjlg3i
8Thenx+HxYahqoiSxOjwKJGyKFbrjDY+ooChayBK6KaJRRKwO62YmNQ11aIrYKga+3fvoH5OPdGo
j4suOAO33c7ObdtJpkqkMirr160hl09htQjs2bcLu83KssWLSSdyZA0VBIn+nlECoSALF63juwtr
0dUMIcnO4cF2IpMS/aEsFENseW4/nzz3cgJrLIzsGOHbO26ibV4rKyoXYkVEkiyMq1Mk1FFCop8n
9z+B1ZBxyW5KKYUJawqh1sKEMoXFKiNJIlpJJJXKYxHeXJ3+2ybDMNS1zaysLEcQDQRhhuSL2QKS
aAVJQNd1rFYrhiBitVrQNY10Monb7UZAwzAMZKuEaLFjqAbJRI6x0RiiaSGXz9E6v4WB/m6iYT+l
TJLx4UGOxfIMTYssaJ1HQ30lnV2HWbZyEXktj4lGud1FJplDNwRGxiaZno7jdDtxe1xUVjeQSmfJ
ZjOIkkCxmKO1rRVBMJFlmUIhh6YqKMU8bpcDiygwPT1JNBpBUG2IlpnbUWSBkqIAMtNTCbLZHKKk
U1Ex4w2QSqUIhUKMjIxQKBRoW3X6m5JheCvx2L/dxbJHb+Wxk77PuQ//K0W7n5pjO/jRxw4yGV1I
KBxj5crttJ3yMR668G7Wb/8mlkL2DXIMt1+57Q1zX37HekaqVlFdPVMDr+5NYVVz/+ta+hpOobH/
mb+63tuv3EbF6F7Ofvzq1z3/8Lt+RuXonlmbqPypDMM7EXECBHlzqcO/B7ORYfjR1FfMKxwfBE1C
lDPIUohMKYMdAbCg6Ro2ux1DFLHK8nFecLnd6IKIrpew262IoogoWJgcnSQ+nUQwIZ/PUz+nlpHh
fqorIyRio6RiE4yMKxybsjCvdS619RV0dh1m+erFlNQ8hqERcHtIZNKYukx8MIueFsiU0vjn+DCi
Hiyyg8x4jDwJss4MNbXVVAthhKyKKBVI61myaoGQ24tLt1NKa+iGjYQtCS6Bjskujia7iJtpCrKC
JpqImkSzr45zq04neMyFYmaIhFromezhKc/jXBP9j3eeDIOuGwiijKYWsDqtlEoqpihjmCZaoYRs
s5DNZBgfH6e+vh7DMHC6ZqI5ERkDFdMUMHUNQZwRM3t2y/O0tS1iyapFgEZ9YwUOp4WsOs30WBeT
4yVERxO9/QNU1NQxOlVi7y8epb65jrnzmrHoJhU1c9BUA9lbiTw0QqmkMT4RZ/ue5wCBQMBNOOLD
bpdo7+ymp6eH0087hVC5Hy2XxdRtyNJMuikQCpHN59GKWURBxufzkk3n8Hi8FAp5olURInoI09Cw
2GzomoY/6EfHwGa3Ypj/XDemsfKlZN1Rmnv++Dff299wMgq3sJsAAB0ASURBVCtP3IPtF+NccceG
171mK2X54pe+iixrPPbIeez79l5c249SduBEMCFxhZMDExvYtOVGAK68fe1xGYaGhh62ffAb6P99
LZkXqxn440EezV5Nq/MhXjrxOi7+7cW0Hb3/Dev5W4T/6uf8JQSn394GpNngrZRe+L8g/NlCM3VE
BFTdxGK1oKoGoiCjqzMVOZIkkUwkSKfTVFRUvJ4XBAFBkjF0g5nUgEmwLMjW7VtpmzefRcsXYZgK
9U3V2O0iQslG54FeRo7lMexz6enro7y6lvFplZ/e/jD1TbW0zZ+LJOaoqI5QVFScNjdTQxmEtEmq
b4L2nZ3kctAYCFNd5cNtl9CmsrzQ0cnJJ52Gu9KFizCqUsRekiFr4BYdpA2TsoSJU7NR4Yqw2rUK
2eMiWczidnpRtDwWq45f8eCK+CgxgaAVsEgWRNP6V/fwb+Fti/QPbX/cjJaX4fO5KCp5ZFlGlB0z
LvU2CyVVQdd1bDYbpmlimiaSLJPLZpmMTVIWjeAL+UAUQJBQSzqy1YmulxAwEMQZU3JKObRilkNb
X+KlPV3orjmUDCseXxXZPBiCHRORdCpOQ72VhoY66urqefKJZ7BKdoLBME0NcxAEgUOHXiYeH+PE
DSuRJR1VKWC32chlMlRXeRAEgWJRoaauHgDDBEEQKBSy2Ox2dFUjlUrgdjmJx6ewWmWsNgcYMrph
EAiFKGSzOL1etGKR6USCqjlr/k8j/ZSvlq6Wzazc/fdXXrS3XkjjwfnI8mtG7k88fg6HDi7hs1/4
DwBGR6qo+v3DPP7YeRxYeyWnnPZHqo9tZ8+dzXS3nENb94Osv3AneXsI6ROP8csPPMGnvlfHs6d8
g/BkO4sP/pJHN/+QzY++NUqUb8Yu8e2I9H/Ne1jDDhrpf8Nrj3I2Czj8NzuFn+D01+kD/bMxm0j/
lthnzSvMD+CQvaj6NBhuDBvYdBPJ5kBTFQzDwGKxIAgChmEgSRK5XI7xyWmi0TD+kA8EY4Y3DAlB
kDBNEVEA0NDULKJeJJ9NcGTnDnbs60a31lFSZTzeSlTNhiHayJc0ioUcjZV2WloqqKwt47EnnkaW
PURDUeY11s6kgo/0kpuKs2xlK7gVMoKCxRUkFc8wt1pEF0yUfI7G6jpETEqiQMEqoecyOKx2VBWy
6Rw20YGSKWAXZCwWGyVJAF0iEAiR0PvwyVGSosn9hd9xVfnn3nmRvt1mQxYlUok0CAZFUyEc9oDV
Qjoex+myY3M4URUFQRDQVBXRBJ/Hi9vmRrbLIIoYWglBBMkiYaIjCAaSaMxEBpKFdE7BITqobl7M
uXVL2H3kGHv395LMCKi6C4/HCqaAWhRp7x7CFwpToZuousbU9BiJVIb+/mOoxTwXvftddLbvp7Gh
imQ8RryYJTY6zoply5EtCqYgUFbjIzudIp3J4XS5KZVUJuKTNDY14fQE8MkuZNGgNhJBLSaYmpjC
6wyTSCRIxeNMT09TZ7VSKpWYnpykavZVm7OCLzX0DxE+zETOE43j/PzKrZy48WlO3PQsZ5z1CGec
9VodeGXVCObHl9P8oz9yaP3lrFi5E1aKnLAhxeL8Q/zyZ5dzYORyrr3OAUBj39N87XqDa2/yHE/z
/CXCf+KM73DGE5/5i+s6VrWK6pFdpD2VeDOj3HpNH9fc+maOxt8+vJffADPk300LNQxxBT8HZqpp
drDmOOkXsfEYZ7OCPdQyzB1czhX8/P+U8GcLi2BDMkWSyTQIWTBEfC4/VlkkmUzhcTuR7DZURcEw
TXRdR7Ra8bq92B1urHb5lYuBDqKAIJmYpj5jEoeAqmmIspNkIoVd8lJRt5Bza5ey+/AA+/f3ks3L
YHqwuUJoBihFmUNHCpT53FQEvGh5G7FSnonkKP1DU8RLE5x38bvoevkgtSuaSI72ok+lSI73s2LJ
WiyiiCqBI+ohMzVJNpdG9DlJUEId02iqCeL0uLDJBWRJQ4yUQM2RGk/hlMuIZdKYps54bhR3mY+i
pJE2Zy/ECG8j6eeyBYJBE4fDgdUmo6oqR48cpbq6jmQygdUSxipbmJyI4Xa7yefzOBwOYrEpAoEg
gaCPXDKLPxIE0UQQRUqqSmxgmHC0nFQiA6IEppeSKTEYm2be3BYual2Hx7cV1XRid4XY9tI2nHY7
SmGKQMjH4b27cFsN3nvx2QiGQGIyRSGvMBlPcujgHsqjXvKZOIJRIhoK0FRZx9jwKC63RL5QJJnq
BsmCIFlx2E3iyRQKEh1dewGTdGKKpUvn0dpWh8PhpKKyDq1QorqhDgyDUFmYXDqNYWjYbG+tKcfN
16a59mYvitV93Hzk+Y1fYePzXz/eZfvqe/4aTEB95aBWsbqJTB7hP7+Y5NpvuJC+VuLm6zJINhMk
kc9fe+Pxcd+6+Xo+te9mPu0pw7jRRJZVbr8uTXC6GykkYBivBS+rdv2A835/JT+5aj9X/WQpN1/7
+jK1a2/2Hn9uxwkzB9Rf+PyX+d7Xv3B8/dUjM92i3lfM1q+5tXGmHmD2W/i241XyV7CiMHOb/zhn
czpP8Cvey/n8Dhd5zud3iK9Ubn2Au98x31s1SpRKKi67G7tDpKTY6DjaQX15BclkCptVxmWxEIvF
8Hg8ZLNZnE4nyWQKh8tDIOwjn8gQCPsRBAETE0SB0f5BwmVRpuJxBFHC0CxgczGdtVBZVcW7L1lD
ILAVXXdisfrYuXMXfp+LfHEMb20lew8/h8c+h8svO5U0FpI5jfxkmnh8jP49B2ltaWFweAiXZBIM
hamoDHBsdISAXSdVKjJ9JIdFkLGLduRMiVg6gVQK8OSho+iCTjIzzbJlLTTPqcDltOGv9KOoeSqj
1YiqiFcUMacMBCvoxpur8Hjb0js7n/q96XY78Pk9OJ027HY7+XwBwzAJBoIU8llM08DpdJLLFXC5
3KSSyVdu52SQBXxhH/FUHCSBcKQC3TAw0gpKUWEqkeHZ57dSWVWPKFjJpfKUtDxl5UHGYnEkqwcD
iZKqsnhhG7paZF5zFTaHje72w9TX1pKYThDwhohNTKHoFnLFAkfa97B+wwoqysJMjsQo5XV6e/qx
e52sXHkCiVSKnu4exsenECWZ3r4+vMEq7A4XxWKB0WNDFAoprrrqQ3jcEpgl/l979x5nR13ff/w1
M2fmzMy5n92z1+w9CUnIBRIgCm0hBAUUqWCUUrTay6NFBGm1tT5QS7HVyoP+1FKh+nvorz9FakVE
+ihVlCrYBh4iEiEESMhms7vZ27nfz9xn+seWlZRYNVaB7jz/O2d2Zs9jZvd9zpnv9/v5KCLYtk02
kwHBR5JlBGApn6d/4tUn9b968QXvDfatfzvv/LttP9N+1cwYqlFDM0983/fOq/6F37zz9fzd7Yu0
WgmMzvL91Kuv+QTSTJmHn3gN0weGeONld3Hv195CIMvU40Mr9Xb+q29c9DcUezZx0Teu56H3fpo9
xg2IN+2lkRjk73/n3/AkBcmzOe+hm9j25Beopkf51Hsm8X2Jd737FuLNJWS3w////DW846blQJSE
v2Jm+FfpzT+Jap14TvMr7fbOS+FWrjuuMcxN3EiOAtf8lIuuTub2zkcW/zC4fOH1pPRudM1Clrto
em0k1yOVztIxlj+saJpGrVYnnU7TqNfxXB8pIiNEAtJdSSr1EoIkku3qIvAFzLaBa0OpWuPBB/cy
0D+CrsSplKpYbofe/hzlUhNZTuG6AR2rw44ztmDYLdZsHCKr+Mwd+AEjQ8MUWw6ymqFdaRLxNYrV
Dj94ej8XXHAOvbkkxdlZ2m2b6Zk59LTI6a96NcVKk+nD05TnS0iSwnNHp9C6u9ASSUzD4djMMdrN
Ku+9/hrUiIfgtpBjFoYboSfWS0RpIrVlmnH4nPVl3pP9s5N+D3/JQv9737wvUJQIqhZlaKifAA9R
hFq9TC7Xx5HJKdatW0er1cbzPOLJJNVSBd8PkEWBWCpBJBalbbZIZ1J0Wg0q5RKDwyOUlopMHp4h
29XP2PA6po/OMzM9j++7xJMqnY6J6QToiQzH5pfo7hmgWCpw+Zu2oUoRasU6juGhqjGCQMTzA9qt
gEq5juE1sYM2ohiwYWI9C0fnyefL5FsdfNflggt20WrWWL9uLUuLcxD4tBstTNOh2WxjGhae57L7
dRfxxPe/RzqpgmcyNLSGZrOJEo2gaSqiKFAolRjadO5JXdzr37IruPXUByHwufEm6UXb77vk01xy
39XHPWeoaTTzJ5cM8AWRW95X4vzvfJAzH7udT137LOXuDYyOTVIu5egfmGfu2AjvvPbjxK68g2c/
9iH8Pfex+em7ADi44ddPeNxH3vcJcl97gH07fp/f/8x26slhvnzlvVz1ts/iujKta/dx/86b+eBf
ajQSgySb83zxrfcTby3RivcylJvkgL2bd922iX9+w2dwZB1biR/XnP15/5tC/3G2s4OTryX0i3JS
TVSKfxxc8NQ55BI95LICopTBVjzMVoNkpoepw4dYv2Ej9WodCNDjcRq1Jp7rIosCya4kgibQ6jRI
pVNYpkWlWGFgeJTyUpHDh6fIZHsZH1nL9PQ801OzeH5AMpHGND1cV0LXU8weO0ZPXzel0iKXvmE7
uq5RzJdptzskEmmCIMD3PVptn2K1helY2L6D79lsXr+W/MIc5WKZfNnBc23O33UezWaVtRNj5PNL
EHi0OnVsy6XZsDEMB9/32HXhuTz+6L+TTmloEY90LodkBshRC1/KIMYCPu18gff03PzKu6cfjSp0
dWXRdBVJkpAVhUqlRDqdpVKuMDIygmVZJDIZSktLuLZNMpXg6NGjjA0PU6qUyEhZ4vEEBAFqVKO3
pw88Cc8VOO30HQSexOLCPK5jEosr9A9O0JfrY3bmGFPTR9EjETJ6lIjTZuPoAKIT58jhaWaPzLBx
/QbalsXiYp5yrYqqJKlWG2RzWRYWy2SzKeRAZ934OgIXAiWGbRns/+E+2s06CS2CKAbUqxUM06G/
f5Dx8TEs06FWr3HoqScYnxhBVxUco0mxWFqemuoFyLJCEPg4tn3S53dqah1/dP8giebiCbe/MPD3
b7mKrU/dieQ53HnV17nqztdRyG2ip/jMCfcVA58/vTnLYv/pAGx+6kv4ksL5f7680Odzv7OXtdUf
oHe+xffe+VfMf8jljHaeA5uv4L5LPoMnyXzgIzEeOvfPeGbTHlqj4xhGjDd0/T25Sw+x4C0X0Npw
aLkUw513/B4Av3bDIGfzMH9bP8QV/3gZ+7b/LmuUZxGqVd547zsAGBk5l0+96xmuvW3Ti153W88R
6/ziVpO+VH7awPcQeYLTXpZvEM8zPI/MYC96NA1RC1FSabXLpNNpSrUqfWMjtGyLeE8XpUIBCR81
k2D66FFGhoeYr+RJ59Lo6RReRCKi6yRzEkEgYPsBW3ecQRAIzMwfw/Rs9LTKmqERersGee7wFEem
ZlHiURJdKnbQZmhiEF/UefbQMSaPHGHDho1UmyaLiwWq1SqqnqRSq5PqzjA3f4xsNoUgywyNj2O7
PgYGptlh34F9NJsVonEBNSpRrVVoWU0GB0YYnEjTaTu0Wh0OPHOAsQ3r0XUFo5GnYrSJ2CK67BKL
qVgYuOLPVzLtpSvD0KoTT+hkskk6nQ7NQp1sNoPn+ssj145HfmmRNUNDeL5Pu9NGURQ0XaPeqjM0
vAZBlvAFAVEU8H0X3/YpV8qoSoLJg5PE4wk8D4aH+9GKEZIxhWqpiCLDhokRDKPJqedsY3F+DkHy
eex7T5LQY0yMrkfXdErFIpoWpVvqQo5EUJSAI1NH8DyBRtCkViqTSats3DCOOl+j0agRjYoMbd+K
rEB+aQ4hcInHVUQxoN1ukM8XCAKo1koMrulFUSQkIYaqqVj28qB1xzARBLCsk19AVHnLBTT/5ocr
of/ozuvY+eiPvqq3Yr08ue23OOeRW6ilRwEQfZf+heVpgT8u8AECQeQLv/UAm5/6EqpR47zvfpgv
X/HVle2X3Hc1la51WPc/jb7uXryNlzE9eh753q287uvXov5nN63v7rqJodm9JA48jOwYPNJ1Cbt2
y/wKD/Kt1/41b//8bm78c4FnN17GXVfcw8znZc78/m2c/8xXaCQGEdal2TF7B+repwH48hVf5eDG
ywGopUdI145v5PHCwE+nX77TFn9R7mYPV3AXj3LWcdUxX04c28cxgYgMQcDc9BLda7oIDBddjOGZ
kC8VWTOoENgCVtNGFAViUZ12o8Oa/lFEVQQRBE/Ad3wiLlTmGsQjaWaeniaRTCLYPhODQxSVIilF
oF4+TCrmcPqpOTqmwWmbh5lbnEcSLR7bu49cdy8bx05FFTVqtRpxJUE0oyHJy21Wj05NIngWthjQ
KlVJxeOcMraeRKxGo1FHUUTWnL4FSfAoFBYhsEnrcaJiBK9jUpzL43kizWaN0YFhooFCPNWPYpmo
gUxAHc8McDwPUX3xN/efxUsW+uCTSMQpl8uAj67HqVZrKFEFWVaRozq5vgEe2/c4Y+OjdHfnCHyP
bCRLRABBU8D3EQUREJBEmbbRpFZuYBgFFEUhk0oRici0WzVsq0O95uA6Ps1mDUWOkOtK4XsVRkdT
NJptLLo5fOg5DjcrrJ0YRVYi9Pb3k+nuQcDBc13OOHMr7YaJH3gEnokg2rQNC1EESYJyucTRqYNc
eOFudF0jmYiTyfZQqTU5ePAQlXKNoaEhxsbGKBQKLC06xFQNWZaIxTRESUAUJTzPQxBP/vK8evGz
xBd+VI5g56N/yzcv/PjKqtx4O885j9zCre8+vNKoXPRdzn/wQ//tcUtdp3DbdQePu0f/lTffRb53
K54oc9u1y28W5z70YTSjyrb9X2Tb/i8CcM81X2N47ya+8ME3c//FnyRTmVyZ81/JjJO4e4FmchBF
sei3oyvH783vJ5MpMx85m9d+7Ano+wpLfds497M/WmH8yeunqGfGyFQmeesXL8IXIyz0byfeWloZ
yH2hWi3zM53PFzKJomL95B/8JftJi66uYPn22okCv06S1E9ZXvkXKao4xGI+jdYCXuDQleuiVp8n
EZGRZA0tkyAey/Dk/kcYHBwk291DAEiKhCAFyLqDL7gsN4EUkSICbbNOpVzEdz10LUo6CRFFo9Wc
xXObtBsxfFejXm8iRSS6ct14dsDo4BiGYeJ16kxPH6JSLbJhw1pAZHRsgnSmG8+zcT2bna+aoFmv
IAQ+ICJh4jouBMtd82qVElOHn+Lii3eTSKqkE1mSuRi1WoODz05SKbcZGhqhK5elXJmhVLBRVZ9A
VZDUFBHZRAiiiEGHqPBKrbIZ04hEBBzHQtd1PNdjzdha5o8exTTbRLUYzWabzZs3I4jQaNQQBJDl
CPFMksAxsT0fy3aIRhSeO3CQRrnKadvPpNFoMD8/j+86eN7yAqdoVEOWRfRElExPDFmUcBwLIiKe
KJHt7UXNphibGEH0TYxWlenpaZrtBlJUpm20yOWy1Gt5UrE4tm1TKJToGAaSoiFFUhyaPMQbf/1S
At+lWi+jKHGiagIvEKlWaywu5HEcj56efgrFeQyjQ09PjoHBARzHoVIp0dPTje/7qPEYYvHkm6io
zeVG1h97f4233fEaBucfY/e/vh9b1vHFCFGryYEtV64E/vNlE36cj96wPIB2w0fjyHZ75TGAo8T4
k5u78MXIyvGAF80Yufz2y+B2eDc3rOxvyzpCEJCtTgEcV0fn+Z/Zuv8OXrXtO/S/9RMMfHC54fn6
w1/HE2Ukf/nbkNin8hsX/V/y18/yzQs/znOnXEqiMcd7Pj50Mqfvv/VyDHz4+RZdvRwCH0ClC1no
xgosWkYNJZWiqydHYXoaWZMRXZdWs8PI2Onoukap0kBVo+ixPhQthuM6tM0Ogigg+hKHn52kVqhw
5pk7qdeqzC8sYDjLfWYDPCQpRkzPoEVVErkEkiTSsToQEXAFiKXS9Cga41vGKVUWUFWZyclJKkYB
URcpV0v09edodRpoCREBkcWFAh3TBxSqDYtisci5v3oO8ZhGobiwXDsoquO5aSrlBgvzJpYVsP30
CSqVCpVKhb6+PvoHumm6DtVyC10XiGtdJJPdCGb25zrHL9lA7r7v/lMwODiIY3vU63VGR0c5cuQI
PT19+IJIs9Om0aixbv0Etm2gajJB4CPLEloihud4iEoUu2PSqDZwDQdNVlB1DUEUiWoajmUBEp22
gW27tDotREUkGtUwbZe+/kFs12cpX6TRbFMqtak3iuhROGvH6ViGweHJGfLFOrV6k22nbWLLlnUY
1SUyqTSlUpOnnpmm1bZwRYuoEkWNRvEcl4Vjc2iazsT4OEND/RQKBVQ1hiJHKZdL//kHJxAEDoWl
PLZtce55v0Kmuxt8l067TaFQYGLbyQ3kvnBx1j2X38Hl97yNu/d8iT13X8n8wJm0Yz0cGz6b3d/+
wP/YNf3qm/6BN331N4977tiaV6FpBg9vvI7ipa9haXGA0YMPsOfuK/n27o/wg7PexWVv+hL7Ht7B
7r98O8BK2YabbvRBEND1FplsBXtfg1L3Rj5w04eoPKdz9P4sY3/xKUw1tfL7im+4gH/u/YuVx339
8wwNzbD+ug+z9siP+tb+bxrIfbk6mYHcm2f/OHiHdRWWI9K0FhgY2sQPDzzOuoFBAqIYZodqpcLE
2lE8z0JWJGQlQkSKEIkncBwTWYtitNo0Kg1whOVpklERKSKiaTqWZYIAhmFiGAa+60EAihrB9my6
u3pwPZFCoUK9ZlAo2zQaVaIabDhlHDUWZfK5GRYXS9SbLbZtOZVNp4zhWQZxTaPW6LD/wCRuINDq
LH9wSSeT+J7H7MwsMU1ndHSUtRMDFAqLqKpGRI5QLBRxXA9d03Fdh6WlaRqeza6zd9E1mICmjOe1
+H/S5/nD3EdeebN3Hn/o3gCg3W6T6+5FVTUQRORolJnZY5SrFU47bSuCIuF7Nvg2iipjuy6yvDwD
WRRlzI6JFEj4poui6gTYCH6AFwg4lo2sxRF8Ed91sV0Py/XJFyss5kuIskax3KBaN7BcB9s0iGsS
b71qD0tz08zOzOH7Ch0zQIqo+L7BYG8ULeqQiifoGBJPPHmMjukxtjHJtq3bWFrIs7SQx7Yc1o5N
0Ol0sM0G8XgcXYtjmjbJZALT7GDZJrFYFEEMkOUIlmXSaNTQYzqJdJJWq8UZZ7/+pC7u+X/wiWB7
5x4efPMtxD/5AInm/Mq2pfdfhdix6Ln1xeUNfl7bd3yfZzddztT4a5CdNpGkwK7dD3DmgX08tnk7
+3+txbZNeynlNvDozuuP23ff4zvJ5fJcvf9i9j1+Fos3/jYAg4PHmPqox+j0gyvPbbr1/xCNWnzu
jOXB3tffdzWFni30FJ560Wtas2aWublhpt53DXu+/Q7a7Rg/jF3Odz79R6+40J9mhBLdP3b786Ua
DnIKGzi0UvjsRCUcTrRtgX4GOPHg/0/j+R4DBXLcHhR+5vP7Wues4LXFXdQtl3gCHE8DKSAnJlho
F+lYHUYyQ0R8Ac+38SQbGRHfEwgiyxMgBAGswAYBRF9C92O4Qgdf9BAQCYIAIZAIEAjEAC9YLu1i
0qHaqSFGIpSKDWoNE9cRMV2HSFTg/FN3UhOKlNol2k0bkIlIGpbRQVN8snGdjJakabvMLVbo2A5a
Ck7pW0/b7VCslHAdj7GBcZpmi06tgRqViek6nu+S0ZMYnontOOiqjhg4+EQxBZu2ucCQtAkh0uZf
Ut/iG9G9r7zQD4VCodAv30vWLjEUCoVCv3xh6IdCodAqEoZ+KBQKrSJh6IdCodAqEoZ+KBQKrSJh
6IdCodAqEoZ+KBQKrSJh6IdCodAqEoZ+KBQKrSJh6IdCodAqEoZ+KBQKrSJh6IdCodAqEoZ+KBQK
rSJh6IdCodAqEoZ+KBQKrSJh6IdCodAqEoZ+KBQKrSJh6IdCodAqEoZ+KBQKrSJh6IdCodAq8h8Q
DZTUdeV0NQAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

</div>
</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
