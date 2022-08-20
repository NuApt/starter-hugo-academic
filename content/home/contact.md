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
  directions: [Click here](https://www.google.com/maps/dir//31.7814128,76.997962/@31.781408,76.9629425,13z/data=!4m5!4m4!1m0!1m1!4e1!3e0)
  office_hours:
    - 'Monday 10:00 to 13:00'
    - 'Wednesday 09:00 to 10:00'
  appointment_url: 'https://calendly.com'
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
