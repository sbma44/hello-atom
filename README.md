# to-fix on-top

This is an adapted version of the basic Atom Shell wrapper to allow a copy of [`to-fix`](lab.github.io/to-fix) to run on top of JOSM in a corner of the window.

The only thing that makes this a pain is the need to move OAuth credentials over from your real browser to this one (the OSMAuth process does not work in Atom).

Steps:

- download this package
- navigate to `to-fix` in your normal browser. Be sure that you have already authenticated.
- run the following code in the developer console:<br/>
```
var obj=new Object(); Object.keys(localStorage).forEach(function(k){ if (k.match(/^(http|user)/)) { obj[k] = localStorage[k].replace(/\"/g,''); }}); document.write(JSON.stringify(obj,null,4));
```
- copy the resulting JSON and save it to a file called `osmauth.json` in the `to-fix-on-top` subdirectory (there is an example file in there)
- run `./run.sh` (or `run.cmd` in Windows?)
- (you might then need to click on the auth link in the sidebar once)
- fix some things!
