# Little Esty Shop

## __Turing School of Software & Design Module 3 group project__

### Learning Goals for Little Esty Shop
* Writing migrations to create tables and relationships between tables
* Implementing CRUD functionality for a resource using forms, buttons, and links 
* Using MVC to organize code effectively 
* Using built-in ActiveRecord methods to join multiple tables of data, make calculations, and group data based on one or more attributes
* Writing model tests that fully cover the data logic of the application  
* Writing feature tests that fully cover the functionality of the application

### Contents
1. Setup
1. Project Structure
1. Application
1. Future Goals
1. Contributing
#

### Setup 

This Ruby on Rails application is an extension of the Little Esty Shop group project developed by the Turing School of software development. The purpose of this app is to allow merchants to create bulk discounts for their items. A bulk discount is a discount based on the quantity of items a customer is buying, for example, "20% off orders of 10 or more items." Merchants can create bulk discounts for their items, and the discounts are eligible for all items that the merchant sells.

#### Bulk Dicounts

Bulk discounts must have a percentage discount as well as a quantity threshold, and they should belong to a merchant. Bulk discounts are eligible for all items sold by the merchant, and multiple bulk discounts can be created for a single merchant. If an item meets the quantity threshold for multiple bulk discounts, only the one with the greatest percentage discount should be applied. Bulk discounts should apply on a per-item basis, and if the quantity of an item ordered meets or exceeds the quantity threshold, then the percentage discount should apply to that item only. Other items that did not meet the quantity threshold will not be affected. Quantities of items ordered cannot be added together to meet the quantity thresholds.
#

### Project Structure

#### Models
The `app/models` directory contains ActiveRecord model classes for the various database tables used by the app. These models define the relationships between tables and provide methods for performing complex database queries.

#### Controllers
The `app/controllers` directory contains controller classes for handling HTTP requests and rendering views. These controllers use the models to retrieve data from the database and pass it to the views.

#### Views
The `app/views` directory contains ERB templates for rendering HTML responses to HTTP requests. These templates are used by the controllers to generate the HTML that is sent back to the user's web browser.

#### Routes
The `config/routes.rb` file contains the routing configuration for the app. This file defines the URLs that can be accessed by users and maps them to specific controller actions.

#### Services
The `app/services` directory contains PORO classes that encapsulate business logic for the app. These classes are used to consume external APIs and perform other complex operations that don't fit neatly into the models or controllers.

#### Tests
The `spec` directory contains RSpec tests for the various components of the app. These tests ensure that the app is working as expected and catches bugs and errors before they can be deployed to production.
 
#### Schema
This diagram for the project shows the database tables and their relationships to one another:
![Screenshot 2023-03-08 at 10 47 52 AM](https://user-images.githubusercontent.com/116698937/223776396-a03f2eb3-3bda-44c3-aed0-411dd5d2b7a4.png)


#

### Application

You can visit this application hosted on [Heroku](https://littleestyshopbulkdiscount.herokuapp.com/)


To get started on your local machine, you'll need to have Ruby and PostgreSQL installed on your system. You can then follow these steps:

1. Clone the repo to your local machine using git clone
1. Install the necessary gems by running `bundle install`.
1. Create the PostgreSQL database by running `rails db:create`.
1. Run the database migrations by running `rails db:migrate`.
1. Seed the database with sample data by running `rails db:seed`.

You can then start the Rails server by running rails server and visiting http://localhost:3000 in your web browser.
#

### Future Goals

Project Status: _In Progress_

* #### _Invoice Protection_
To further protect invoice integrity, we can implement a feature that prevents merchants from deleting or editing bulk discounts that apply to any of their items on a pending invoice. This ensures that all applicable discounts are included in the final invoice amount.

* #### _Store Discount Percentage_
In order to keep track of the discount percentage applied to an invoice item when an admin marks an invoice as "completed", we can implement a feature that stores the discount percentage on the invoice item record. This allows us to reference the discount percentage later on if necessary.

* #### _Holiday Discounts_
We can extend the functionality of the app by allowing merchants to create holiday-specific discounts. When visiting the discounts index page, merchants can see a "create discount" button next to each of the 3 upcoming holidays. Clicking on the button will take the merchant to a new discount form with the fields auto-populated with the discount name, percentage discount, and quantity threshold for that specific holiday. Merchants can modify the information as needed before saving. Additionally, if a merchant has created a holiday discount for a specific holiday, they should not see the "create discount" button next to that holiday on the discount index page. Instead, they should see a "view discount" link that takes them to the discount show page for that holiday discount.
#
### Contributing
This application was developed by:
* [Harrison Ryan](https://github.com/hwryan12)

If you'd like to contribute to Little Esty Shop Bulk Discounts, you can fork the repo and make your changes in a new branch. Once you're happy with your changes, create a pull request to merge your changes back into the main branch.
#
### License 
By me.
