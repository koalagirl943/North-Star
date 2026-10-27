North Star is a web app designed to help people get home safely at night by guiding them along the brightest-lit streets, pointing them toward nearby safe places, and connecting them to a trusted friend who will know if they don't make it home.


Features
Feature	What it does
Safe spots	Finds real police stations, fire stations, hospitals, and 24-hour businesses near you, and marks the closest one as "Your North Star."
Brightest route	Compares several walking routes against real street lamp data and picks the best-lit one, then tells you how much of the walk passes street lights.
Check-in timer	Set how long your walk should take. If you don't tap "I'm home safe" in time, the app prepares a text with your last location for a trusted contact, plus a button to call 911.
Street lights	Shows real street lamps and lit roads on the map.
Broken light reports	Mark streetlights that are out, and North Star writes a letter to your city listing every location.
Spoken alerts	Reads routes and warnings out loud, for when your phone is in your pocket.
How the brightest route works

Most navigation apps choose the shortest path. North Star chooses the best-lit one:

The app asks the OSRM walking router for up to 3 alternative routes to the nearest safe spot.
Each route is sampled every 20 meters.
A sample point counts as lit if a street lamp is within 35 m, or a road tagged lit=yes in OpenStreetMap is within 15 m.
The app picks the route with the highest lit percentage that is no more than 30% longer than the shortest route.
The chosen route glows on the map, alternatives are shown as dashed lines, and the app explains its choice.
Reliability

Free public map servers can be slow or overloaded, so North Star is built to keep working when they are:

Safe spots load from two sources at the same time: a fast search service for emergency services, and a fuller query for 24-hour businesses.
Requests to the OpenStreetMap Overpass API go through a queue (one at a time), with failover across three servers and automatic retries.
If the map tiles fail, the app switches to a backup map automatically.
Privacy and security
No accounts and no backend. North Star has no database of user information.
Saved settings (your check-in contact and reports) stay only in your own browser.
Alerts are never sent automatically. Your own texting app opens with the message ready, so you stay in control.
Text from outside data sources is sanitized before display to prevent cross-site scripting (XSS).
Served over HTTPS on GitHub Pages, with the map library hosted inside the project.

To find nearby places and routes, your general location is sent to the public OpenStreetMap services listed below. It isn't linked to a name or account.
