SpeckBilling
=======
Version 0.0.1 Created by Yanick Rochon

Introduction
------------

SpeckBilling contains all features to generate and store invoice and billing information.

Requirements
------------

* [Zend Framework 2](https://github.com/zendframework/zf2) (latest master)
* [ZfcBase](https://github.com/ZF-Commons/ZfcBase) (latest master).
* [SpeckAddress](https://github.com/speckcommerce/SpeckAddress.git) (latest master).
* [ZfcUser](https://github.com/ZF-Commons/ZfcUser) *(optional)* (latest master).


Features / Goals
----------------

* configurable recurring billing
* send email invoices / notifications (ZfcMail?)
* generate downloadable (ex: PDF) invoices and reports


Installation
------------

### Main Setup

1. Install the required modules by cloning them into `./vendor/` and enabling them
   in your `application.config.php` file.
2. Clone this project into your `./vendor/` directory and enable it in your
   `application.config.php` file.
3. Import the SQL schema located in `./vendor/SpeckBilling/data/schema.sql`.

### Post-Install: Zend\Db

1. If you do not already have a valid Zend\Db\Adapter\Adapter in your service
   manager configuration, put the following in `./config/autoload/database.local.php`:

        <?php

        $dbParams = array(
            'database'  => 'changeme',
            'username'  => 'changeme',
            'password'  => 'changeme',
            'hostname'  => 'changeme',
        );

        return array(
            'service_manager' => array(
                'factories' => array(
                    'Zend\Db\Adapter\Adapter' => function ($sm) use ($dbParams) {
                        return new Zend\Db\Adapter\Adapter(array(
                            'driver'    => 'pdo',
                            'dsn'       => 'mysql:dbname='.$dbParams['database'].';host='.$dbParams['hostname'],
                            'database'  => $dbParams['database'],
                            'username'  => $dbParams['username'],
                            'password'  => $dbParams['password'],
                            'hostname'  => $dbParams['hostname'],
                        ));
                    },
                ),
            ),
        );

Options
-------

Coming soon.
