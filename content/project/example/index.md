---
title: Mercari’s Large Scale System Design Hackathon
summary: A Hospital management system | InterIIT Tech Meet 10.0 IIT Kharagpur
tags:
  - Hackathon
date: '2022-04-29T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: https://techmeet.iitmandi.co.in/

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links:
  - icon: twitter
    icon_pack: fab
    name: GitHub
    url: https://github.com/divyashk/tech-meet
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---


Application Features

The application has roles for users (Patient, Doctor and Hospital). Based on the role the user
can login/signup into the app. For a patient as a user, the home screen will show a dashboard
allowing the user to book an appointment and check previous appointments.In the book an
appointment tab the user can select available hospitals and doctors available in that given
hospital to book his/her appointment for diagnosis at an available time slot. Check previous
appointments tab is used to keep track of all the previous appointments for that given user.
For the doctor as a user, the home screen will show a dashboard allowing the user to check
appointments. From the appointment tab the doctor can directly go to the diagnosis of the
patient. In the diagnosis page the doctor can add the prescription for the patient along with the
medicine's quantity and finally conclude the diagnosis with a close appointment button.
For the hospital as a user, the home screen will show a dashboard allowing the user to check
inventory, room information, doctor details. In the inventory tab they can check for the available
medicines in the inventory of the hospital along with their quantity and price. In the room
information tab, they can check for the availability of the rooms in the hospital along with the
number of the available rooms. In the doctor details tab, they can check the profile of doctors in
the hospital.

Here we will be making use of docker containers to host multiple scalable instances of different
services.
The 4 basic services that we have implemented are -
-Appointment management (to manage appointments between doctors and patients)
-Inventory management (to keep an account of drugs, equipments etc)
-Infrastructure management (alot beds/rooms)
-User authentication (login/signup)
In our implementation we can scale the frontend servers that handle requests from the client
side directly to any n instances depending on the number of users that use the application.
Since these instances are all connected through a single nginx container , this nginx container is
responsible for distributing the requests in a round robin fashion.
In this implementation it is very simple to scale up the frontend servers by simply changing the
input to the docker-compose file and then adding the address of the newly created instance the
nginx conf file.


Design Decisions -

Backend Framework - We chose to use the Flask framework because it comes stripped
of unnecessary modules that we don’t need. Also, Flask is highly scalable and is used by
companies like Pinterest to manage about 12 billion requests per day.

Database ( NoSQL vs SQL ) -
We believe that vertical scalability offered in SQL databases by increasing the
hardware capacity of the same server ( adding ram, cpus etc ) has a limit as there is a
capped amount of hardware accessories that can be added to a single server ( like
storage slots etc ) .
But NoSql databases offer horizontal scalability, therefore we can simply increase the
capacity of the database by adding more servers into the mix. Therefore, there is no
limit in terms of scalability.
Hence, we chose to go with a NoSQL database ( Firestore ).

Load Balancing - We used Nginx as a load balancer because a software-based load
balancer is much less expensive than hardware-based solutions with similar capabilities.
Nginx also offers more capabilities in NGINX plus.

UI look and feel - We decided to use the Materialize UI library( HTML/CSS) to design all
the frontend components like buttons, inputs etc. Because we believe they offer a very
clean look to the website and give the site a comforting feel which is very much required
from a hospital management perspective.

User Experience - To ensure that the user experience remains smooth throughout the
app, we have added certain features in the webapp. For example, we have made the
login/register process very smooth. You do not need to navigate to multiple pages for
login and signup. There is just a single page which asks for your username for login. If
you already have an account, then it asks for your password and logs you in. Otherwise,
it asks for other details and then creates a new account for you.
Similarly, we have reduced the process of registering as a patient, doctor, and hospital
into a single page where you enter the role you wish to pick, and depending on that, your
account gets created.

Security considerations - For storage of password, we have used sha256_crypt hash
function for hashing passwords before storing them in the database. This prevents
storing any passwords in the plaintext, and is an important security aspect for our users.
In the frontend, we have not exposed any security keys or credentials for database
access. All the database reads are made through the backend and the microservices
and their credentials are protected through .gitignore file and environment variables.
