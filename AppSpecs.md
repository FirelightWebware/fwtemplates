# [Project Name]

## Overview

**Primary purpose of application:** [describe primary user benefit]  
**Secondary purpose of application:** [describe secondary user benefit or primary admin benefit]

### Glossary of Terms

Terms used in this document, within the context of the application.

* **The Application (or System):** the [project name] website [or web application] and it's admin interface
* **Super Admin:** an agent of [client] or Firelight who can view, create, or change any data in the system
* **Admin:** depending on context, a section of the site for updating site content or a person who has permission to access that section

### Process

#### Where Data Comes From

[explain whether INITIAL data will be imported from a third-party, manually entered by client, or manually entered by Firelight]

#### Primary Function

[describe the flow of data... e.g., admin enters blah blah blah, user can do such and such with it]

### [primary data model]

[describe objects]

[objects] will have the following properties:

* list properties

#### [another data model ...]

[as above, as many sections as necessary]

## Users & Permissions

#### Superadmins

* Can manage all application data

#### [special] Admins

[describe admin group]

* Can create, edit, delete [objects]
* [etc]

#### Users

* Can view [pages]
* Can create, edit, delete [objects]
* Can manage user preferences

#### Public

Public includes legitimate users who have not yet logged in.

* Can view [pages]
* Can view contact info and submit contact form
* Can submit forgot password form (with valid user email address)

### Creating Users

#### Admins

Admins will be created by [Firelight].

#### Users

Users will be [imported? invited? manual entry?]

## Information Architecture

Navigation, page content and behavior. Pages are in bold. Everything else defines content and behavior for the page. Pages prefixed with **~** are in navigation, otherwise the page is linked to from another part of the application, such as an object list view or a link in an email. _Note that nested pages marked as in navigation are only in the navigation on the page they are under._

### Public Pages

* **~Home**
    * Intro 
    * [Social icons/widgets]
* **~Contact**
    * name, email, subject choice, message, captcha
    * on submit --
        * Email [specific admin] and save submission in 
          database

### Adminland Pages

* **~Home**/**Login** -- after login admin sees dashboard
* **~Dashboard**
    * Links to other admin pages
    * Link to google analytics
    * [Information on how to log in to gmail and google 
      analytics]
* **~List of [objects]**
    * [list display fields]
    * **~Single [object]**
        * [list readonly fields]
        * [list editable fields]
    * **~New [object]**
        * Same fields as Single [object] above

## Email

* Password reset email
* Contact form email

## Background Processes

[stuff that happens asynchronously that needs to be programmed to happen "behind the scenes"]

## Documents

* [list any documents the application must generate, i.e.,
   PDFs, CSVs, Images (for export), Excel docs]

## Calculations

[describe any complex programming logic that needs to look like magic to the user/admin]

## Integrations

* [list third-party integration requirements -- explain how
  data will get in/out]

## Domain

[who will register or has registered the domain? who will manage the domain? who will handle the DNS records? what is the domain going to be? what provider is it registered with?]

The proper host records will need to be added to the domain in order to ensure email from the domain does get flagged as spam.

## Security

One-way encrypted passwords. Users and admins will use a "forgot password" screen to request a reset.

#### Password Reset

When a user or admin submits a password reset request, the application will email them a secure link to reset their password.

## Platform

Python/Django. PostgreSQL. Nginx or Apache. Hosted on a Linux server. Javascript, cookies, and a modern browser will be required. Mail will be sent through a [Mandrill] account.