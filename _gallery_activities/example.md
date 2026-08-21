---
# EXAMPLE / TEMPLATE — copy this file to add a new activity, then either
# delete this one or leave `published: false` so it never appears live.
#
# 1. Put the activity's photos under assets/img/gallery/<some-slug>/
#    (resize to ~1200-1600px wide JPGs first — no need for full-res originals)
# 2. Copy this file to _gallery_activities/<some-slug>.md
# 3. Fill in title/date/location/photos below and remove `published: false`
#
# The permalink is auto-generated as /gallery/<filename-without-.md>/
# (see the `gallery_activities` defaults in _config.yml), so the filename
# itself becomes the URL slug.
#
# `date` is the start date (also used for sorting and the index card).
# `end_date` is optional — only add it for multi-day activities; the
# detail page will then show it as a date range instead of a single date.
title: "Example Activity"
date: 2026-01-01
# end_date: 2026-01-03
location: "Jeju ICC"
published: false
photos:
  - src: /assets/img/gallery/example/01.jpg
  - src: /assets/img/gallery/example/02.jpg
  - src: /assets/img/gallery/example/03.jpg
---

{% include gallery-activity-meta.html %}
{% include gallery-photos.html photos=page.photos %}
