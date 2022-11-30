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
    postcode: '175005'
    country: India
    country_code: IN
  coordinates:
    latitude: '31.708401'
    longitude: '76.932198'
  directions: https://www.google.com/maps/@31.781604,76.9980351,19z

  contact_links:
    - icon: linkedin
      icon_pack: fab
      name: Connect with me on LinkedIn
      link: 'https://www.linkedin.com/in/nikhil-ujjwal-iit/'


design:
  columns: '2'
---
