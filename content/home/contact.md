---
# An instance of the Contact widget.
widget: contact

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 130

title: Contact
subtitle:

content:
  # Automatically link email and phone or display as text?
  autolink: true

  # Email form provider
  form:
    provider: netlify
    formspree:
      id:
    netlify:
      # Enable CAPTCHA challenge to reduce spam?
      captcha: false

  # Contact details (edit or remove options as required)
  email: b20056@students.iitmandi.ac.in
  phone: +91 87917 61862
  address:
    street: B-11, 007, Indian Institute of Technology(IIT)
    city: Mandi
    region: Himachal Pradesh
    postcode: '94305'
    country: India
    country_code: IN
  coordinates:
    latitude: '31.708401'
    longitude: '76.932198'
  directions: https://www.google.com/maps/@31.7859508,76.9969434,14z

  contact_links:
    - icon: twitter
      icon_pack: fab
      name: DM Me
      link: 'https://twitter.com/Twitter'
    - icon: video
      icon_pack: fas
      name: Zoom Me
      link: 'https://zoom.com'

design:
  columns: '2'
---
