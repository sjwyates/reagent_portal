# Reagent Portal

## Overview

The Reagent Portal is a consumable inventory management system (CIMS) designed to be used in labs that perform mostly routine testing, such as quality control (QC). Its essential function is to uniquely identify and track each individual unit of a reagent - for instance, a bottle of methanol - throughout its lifecycle, from receipt to disposal. It also allows user to:

- Print Zebra labels with QR codes and GHS warning symbols
- Upload and view vendor certificates of analysis as PDFs
- Configure business logic for each reagent, such as qualification and open expiry
- Receive push notifications when inventory falls below 5S safety stock
- View expired/expiring reagents and data visualizations in the user dashboard
- Perform routine maintenance as a super user, such as adding new reagent templates
- Manage users as an admin user in a separate dashboard
- View audit trail and set up routine system backups

By design, the application is modular, flexible and scaleable. For instance, if your lab doesn't have a Zebra printer and instead would like to generate a Word file, that functionality can be added without duplicating or disturbing any part of the ZPL2 module.

---

## Stack

The application is built in 3 separate Docker containers: the frontend (what the user sees), the backend (the server the user is communicating with), and the database.

---

### Backend

The API is built in Django, a mature open-source Python framework, for a number of reasons, primarily to utilize its object-relational mapper (ORM):

- It abstracts and streamlines the process of declaring database tables, fields and relationships, such as many-to-many and many-to-one
- It's totally agnostic of whatever database you use, so switching between them requires changing the config, not the code itself
- It performs your migrations for you and keeps track of them in a Git-like history that you can roll back and forward.
- It provides an admin interface for managing objects in the database.
  
All of this comes straight out of the box, so most Django projects look pretty similar to one another, meaning any Django developer can come in and maintain it.

---

### Frontend

Vue 3

---

### Docker

Containers