# story-builder-api
Data service for Mapseed story builder

## TODO
* model permissions
* Mapbox Studio integration (?)
* Model basic styles, possibly allowing for overrides (?)
* etc...

# Data models
Still very WIP...

## User
* username
* email
* password
* affiliated_flavors (one-to-many with Flavor)

## Flavor
* allowed_origins (one-to-many with Origin)

## Origin
* origin_url
* permissions (TODO)

## Story
* chapters (one-to-many with Chapter)
* action_text
* action (somehow this will model different built-in actions, such as email signup, donations, etc.)

## Chapter
* order
* module (one-to-one with ChapterModule)

## ChapterModule
* type
* style
  * arbitrary CSS override styles

## MapLayer
* id (should be descriptive, not just the PK integer)
* source
  * slippy URL to statically hosted vector tiles, or raster tiles, or geojson source
* style_rules

## FilterRule
* layer_id
* filter
  * raw text of filter

## StyleRule - this one will be tricky
* layer_id
* type
  * one of: paint or layout

