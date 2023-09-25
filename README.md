# Magento Demo

This project aims to demonstrate advanced development skills in Magento 2.4, with a focus on creating a responsive layout and using all the tools available, including LESS, XML, Knockout.js, jQuery, PHP, among others.

## Main Features

- Responsive Layout: The project was developed with a fully responsive design, providing a consistent user experience across different devices and screen sizes.

- Theme Customization**: Theme customizations were applied using LESS to style the elements of the store, ensuring a unique and attractive appearance.

- Home Page Configuration**: We used XML to configure the structure of the homepage, including static blocks, sliders and featured categories.

- Interactivity with Knockout.js and jQuery**: We incorporate interactivity into the page using Knockout.js to manipulate dynamic data and jQuery to enhance the user experience.

- Custom Module Integration**: We develop custom modules in PHP to add specific functionalities, such as integration with third-party services or customization of checkout processes.

## Project Structure

The structure of the project follows the best practices of Magento 2.4:

- `app/code`: Contains the custom modules developed for the project.
- `app/design`: Stores the layout, template and style files for the custom theme.
- `pub/static`: Contains the static files (CSS, JS, images) after compilation.
- `var`: Directory for temporary files, such as logs and cache.
- `view/frontend/web`: Contains the JavaScript, CSS and image files specific to the front-end.

# Installation and Configuration

## 1. Clone the repository:

```bash
git clone https://github.com/seu-usuario/seu-projeto.git
```
### Importing a Database into MySQL or MySQL Workbench

This guide explains how to import a database into MySQL using the MySQL Command Line Client or MySQL Workbench.

#### Using MySQL Command Line Client

1. **Open Command Prompt or Terminal**:

   - On Windows, search for "cmd" or "Command Prompt" in the Start menu.
   - On macOS or Linux, open the Terminal.

2. **Access MySQL**:

   - Type the following command and press Enter. If necessary, replace `your_user` with the MySQL username and `your_password` with the MySQL password.

   ```bash
   mysql -u your_user -p
   ```
Create a New Database (optional):

If you want to import the database into a new database, create it with the following command:
   ```bash
  CREATE DATABASE new_database;
   ```
Select the Database:

If you want to import into an existing database, select it:
   ```bash
    USE existing_database_name;
   ```
Import the Database:

Make sure the SQL file is in the same directory where you are in the command prompt. Then, execute the command:
   ```bash
    SOURCE file_name.sql;
   ```
Replace file_name.sql with the name of the SQL file you want to import.

Check if the Data is Imported:

You can check if the data has been imported by using SQL queries in the MySQL Command Line Client.


### Using MySQL Workbench

1. **Open MySQL Workbench**:

   - Launch MySQL Workbench and connect to your MySQL server.

2. **In the left navigation pane, right-click your connection and choose "Open SQL Script"**:

   - Navigate to the SQL file you want to import and select it.

3. **Execute the Script**:

   - Click the execute icon in the toolbar or press `Ctrl + Shift + Enter` (Windows) or `Cmd + Shift + Enter` (macOS).

4. **Wait for the Execution to Finish**:

   - MySQL Workbench will run the script and display the progress in the output panel.

5. **Check the Results**:

   - After completion, you can check if the data was imported by running queries in MySQL Workbench.


## 2. Configure the database and access data in the .env file

### Description

The `.env` file in Magento 2 is a configuration file used to store environment-specific settings, such as database connection details, base URLs, and encryption keys. This file allows for easy management of environment-specific configurations without modifying core files.

### Configuration Steps

1. **Create the `.env` File**:

   - Navigate to your Magento 2 root directory and create a new file named `.env`.

2. **Define Environment Variables**:

   - Open the `.env` file and add the following environment variables with their respective values:

   ```dotenv
   # Database Configuration
   DB_HOST=localhost
   DB_NAME=your_database_name
   DB_USER=your_database_user
   DB_PASSWORD=your_database_password

   # Base URLs
   BASE_URL=http://localhost/
   SECURE_BASE_URL=https://localhost/

   # Encryption Key
   ENCRYPTION_KEY=your_encryption_key
    ```
Replace **your_database_name**, **your_database_user**, **your_database_password**, and **your_encryption_key** with your specific values.

3. **Load Environment Variables (Optional)**:

If your project uses a package like Dotenv, it can automatically load the .env file. Otherwise, you may need to manually load the variables in your application.

4. **Configure Magento 2:**

Run the following commands to apply the configuration changes:
```bash
php bin/magento setup:upgrade
php bin/magento setup:static-content:deploy -f
php bin/magento cache:clean
```
### **Note**
Ensure that the `.env` file is kept secure and not exposed publicly, as it may contain sensitive information.
This `.env` file provides a convenient way to manage environment-specific configurations in Magento 2 without directly modifying core files.

## 3. Install the Magento dependencies and custom modules:

```bash
composer install
```

## 4. Update and compile Magento:
   
 ```bash
bin/magento setup:upgrade
```  

 ```bash
bin/magento setup:di:compile
```  
## 5. Clear the cache:
   
 ```bash
bin/magento cache:clean
```
