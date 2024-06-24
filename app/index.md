---
layout: collection
title: "Manage a workforce design history"
description: "A record of how this service has developed over time."
pagination:
  data: collections.all
  reverse: true
  size: 50
posts:
  title: Posts
eleventyComputed:
  eleventyNavigation:
    key: home
    title: "{{ title }}"
related:
  items:
    - text: Prototype
      href: https://manage-a-workforce-main.apps.live.cloud-platform.service.justice.gov.uk/
      description: |
        Username: `manage`
        Password: `workforce`
    - text: Prototype repository
      href: https://github.com/ministryofjustice/manage-a-workforce
    - text: Design history repository
      href: https://github.com/ministryofjustice/manage-a-workforce-design-history
---
