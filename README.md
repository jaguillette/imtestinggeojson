imtestinggeojson
================

This is how I got the togeojson script working to process many kml files and convert them to geojson. I am on Ubuntu, but Mac is unix-based so it shouldn't be too different. Heaven help you if you're using Windows.

Used script from here: https://github.com/mapbox/togeojson
`git clone https://github.com/mapbox/togeojson` in a terminal on a machine with git

Had to install node.js and npm, followed directions here: https://ariejan.net/2011/10/24/installing-node-js-and-npm-on-ubuntu-debian/
Version on this site is out of date, so just don't pick one. Takes a while, and I had to move the node folder to /usr/local/lib, which was indicated in the error messages I got when I tried it the way the site said.

Finally, don't forget to do this:
`npm install -g togeojson`
I had to sudo it to get it to work.

Then, you can use a line like this one to convert batches of kmls to geojson:
`for f in *.kml; do togeojson $f > ${f%%.*}.geojson; done`
That'll take every kml file in the current directory and convert it to a geojson in the same directory.
