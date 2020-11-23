# Database Modeling

### Data Modelling
![](https://github.com/shamy1st/database-modeling/blob/main/images/data-modeling.png)

### Conceptual Model
represents the entities and their relationships.

![](https://github.com/shamy1st/database-modeling/blob/main/images/conceptual-model-erd.png)

### Logical Model
detailed ERD with data types (abstract) and more relation details.

![](https://github.com/shamy1st/database-modeling/blob/main/images/logical-model-erd.png)

### Physical Model
the implementation of the logical model

![](https://github.com/shamy1st/database-modeling/blob/main/images/physical-model-erd.png)

### Normalization

Normalization is the process of organizing the data in the database.

Normalization is used to minimize the redundancy from a relation or set of relations.

### 1NF- First Normal Form
Each cell should have a single value and we cannot have repeated columns.

**tags** in table courses violate 1NF rule.

![](https://github.com/shamy1st/database-modeling/blob/main/images/1nf-erd.png)

### 2NF- Second Normal Form
Every table should describe one entity, and every column in that table should describe that entity.

**instructor** in table courses violate 2NF rule.

![](https://github.com/shamy1st/database-modeling/blob/main/images/2nf-erd.png)

### 3NF- Third Normal Form
A column in a table should not be derived from another columns.

in the following example balance in invoices table can be calculated from (invoice_total - payment_total), then it should be deleted from this table.

![](https://github.com/shamy1st/database-modeling/blob/main/images/3nf-example1.png)
![](https://github.com/shamy1st/database-modeling/blob/main/images/3nf-example2.png)

* Project- Flight Booking System
* Solution- Conceptual Model
* Solution- Logical Model
* Project - Video Rental Application
* Solution- Conceptual Model
* Solution- Logical Model
* Creating and Dropping Databases
* Creating Tables
* Altering Tables
* Creating Relationships
* Altering Primary and Foreign Key Constraints
* Character Sets and Collations
* Storage Engines
