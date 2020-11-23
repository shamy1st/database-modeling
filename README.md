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

### Create/Drop Database

    DROP DATABASE IF EXISTS sql_store;
    CREATE DATABASE IF NOT EXISTS sql_store;

### Create/Drop Table

    DROP TABLE IF EXISTS customers;
    CREATE TABLE IF NOT EXISTS customers (
        customer_id INT PRIMARY KEY AUTO_INCREMENT,
        first_name  VARCHAR(50) NOT NULL,
        birth_date  DATE DEFAULT NULL,
        points      INT(11) NOT NULL DEFAULT '0'
    );

### Alter Table

    ALTER TABLE customers
    ADD last_name VARCHAR(50) NOT NULL AFTER first_name,
    MODIFY COLUMN first_name VARCHAR(55) DEFAULT '',
    DROP COLUMN points;

### Create Relationships

    DROP TABLE IF EXISTS orders;
    CREATE TABLE IF NOT EXISTS orders (
        order_id    INT PRIMARY KEY AUTO_INCREMENT,
        customer_id INT NOT NULL,
        FOREIGN KEY fk_orders_customers (customer_id)
            REFERENCES customers(customer_id)
            ON UPDATE CASCADE
            ON DELETE NO ACTION
    );

### Alter Primary and Foreign Key Constraints

    ALTER TABLE orders
    DROP PRIMARY KEY,
    ADD PRIMARY KEY (order_id);

    ALTER TABLE orders
    DROP FOREIGN KEY fk_orders_customers,
    ADD FOREIGN KEY fk_orders_customers (customer_id)
        REFERENCES customers(customer_id)
        ON UPDATE CASCADE
        ON DELETE NO ACTION;

### Character Sets and Collations

* **database level**

      CREATE DATABASE IF NOT EXISTS sql_store CHARACTER SET latin1; -- 1 char -> 1 byte  (support latin languages)
      CREATE DATABASE IF NOT EXISTS sql_store CHARACTER SET utf8;   -- 1 char -> 3 bytes (support most languages including asian)

* **table level**

      CREATE TABLE IF NOT EXISTS customers (
      )
      CHARACTER SET latin1;

* **column level**

      CREATE TABLE IF NOT EXISTS customers (
          ...
          first_name  CHARACTER SET latin1 VARCHAR(50) NOT NULL,
          ...
      );

### Storage Engines
