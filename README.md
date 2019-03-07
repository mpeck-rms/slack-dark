# slack-dark
Dark mode css and instructions for the Slack application on MacOS

To use this, append the following block to the end of /Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static/ssb-interop.js:

```
// from https://github.com/laCour/slack-night-mode/issues/73#issuecomment-287467332
document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'https://raw.githubusercontent.com/laCour/slack-night-mode/master/css/raw/black.css',
   // url: 'file:///Users/mpeck/Downloads/slack-black-laCour.css',
   success: function(css) {
     $("<style></style>").appendTo('head').html(css);
   }
 });
});
```

After that, restart Slack
