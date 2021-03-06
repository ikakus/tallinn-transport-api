# Tallinn public transport API

The API that powers https://viimane.info to help people quickly
view their last available transit times in Tallinn.

~Imports GTFS only in production environment. If `NODE_ENV` equals other
than production, call the import script manually.~
Data import is now available under `/api/data/update`.

Ask in the issues or make a PR to add your domain to the CORS list.

Feel free to fork or deploy to Heroku:

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/andreasvirkus/tallinn-transport-api)

## TODO:
- ~Create REST API for our GTFS mongo collection~
- ~Expose handful of GET endpoints (stop, stops, route, routes)~
- Filter/parse GTFS data better (zone_name should contain `Harju*`, etc.)
- Design query flow for FE
  - Get vehicle type (to filter out agency names like Elron maybe)
  - Get user's position and query stops by geo + radius
  - Get stop times by stop_id
  - Get route times by route_id (?)
- ~Configure start script to run index.js (maybe rename to import.js) and then run server.js~
- Check mongoose collections and if empty, call /api/data/update
- Generate UI for API docs (/ -> /docs)
  - ~https://github.com/sourcey/spectacle or ReDoc~
  - ~api/swagger.yaml~
- Have a cup of tea