# projet_symfony


terminal :


Microsoft Windows [Version 10.0.19044.1566]
(c) Microsoft Corporation. All rights reserved.

C:\xampp\htdocs\projet_symfony>php bin/console make:controller home

 created: src/Controller/HomeController.php
 created: templates/home/index.html.twig


  Success!


 Next: Open your new controller class and add some pages!

C:\xampp\htdocs\projet_symfony>php bin/console doctrine:database:create

In ExceptionConverter.php line 103:

  An exception occurred in the driver: SQLSTATE[HY000] [2002] No connection could be  
   made because the target machine actively refused it.


In Exception.php line 30:

  SQLSTATE[HY000] [2002] No connection could be made because the target machine acti  
  vely refused it.


In Driver.php line 28:

  SQLSTATE[HY000] [2002] No connection could be made because the target machine acti  
  vely refused it.
                                                                                       

doctrine:database:create [-s|--shard SHARD] [-c|--connection [CONNECTION]] [--if-not-exists]


C:\xampp\htdocs\projet_symfony>php bin/console doctrine:database:create

In ExceptionConverter.php line 103:
                                                                                       
  An exception occurred in the driver: SQLSTATE[HY000] [1045] Access denied for user   
   'db_root'@'localhost' (using password: NO)                                          
                                                                                       

In Exception.php line 30:
                                                                                       
  SQLSTATE[HY000] [1045] Access denied for user 'db_root'@'localhost' (using passwor   
  d: NO)                                                                               
                                                                                       

In Driver.php line 28:
                                                                                       
  SQLSTATE[HY000] [1045] Access denied for user 'db_root'@'localhost' (using passwor   
  d: NO)                                                                               
                                                                                       

doctrine:database:create [-s|--shard SHARD] [-c|--connection [CONNECTION]] [--if-not-exists]


C:\xampp\htdocs\projet_symfony>php bin/console doctrine:database:create
Created database `db_test` for connection named default

C:\xampp\htdocs\projet_symfony>php bin/console make:user               

 The name of the security user class (e.g. User) [User]:
 >

 Do you want to store user data in the database (via Doctrine)? (yes/no) [yes]:        
 >

 Enter a property name that will be the unique "display" name for the user (e.g. email, username, uuid) [email]:
 >

 Will this app need to hash/check user passwords? Choose No if passwords are not needed or will be checked/hashed by some other system (e.g. a single sign-on server).        

 Does this app need to hash/check user passwords? (yes/no) [yes]:
 >

 created: src/Entity/User.php
 created: src/Repository/UserRepository.php
 updated: src/Entity/User.php
 updated: config/packages/security.yaml

 
  Success! 
 

 Next Steps:
   - Review your new App\Entity\User class.
   - Use make:entity to add more fields to your User entity and then run make:migration.
   - Create a way to authenticate! See https://symfony.com/doc/current/security.html   

C:\xampp\htdocs\projet_symfony>php bin/console make:migration


 
  Success! 
 

 Next: Review the new migration "migrations/Version20220305225000.php"
 Then: Run the migration with php bin/console doctrine:migrations:migrate
 See https://symfony.com/doc/current/bundles/DoctrineMigrationsBundle/index.html       

C:\xampp\htdocs\projet_symfony>php bin/console doctrine:migrations:migrate

 WARNING! You are about to execute a migration in database "db_test" that could result 
in schema changes and data loss. Are you sure you wish to continue? (yes/no) [yes]:    
 >

[notice] Migrating up to DoctrineMigrations\Version20220305225000
[notice] finished in 80.6ms, used 20M memory, 1 migrations executed, 1 sql queries     


C:\xampp\htdocs\projet_symfony>php bin/console make:auth                   

 What style of authentication do you want? [Empty authenticator]:
  [0] Empty authenticator
  [1] Login form authenticator
 > 1

 The class name of the authenticator to create (e.g. AppCustomAuthenticator):
 > AppCustomAuthenticator

 Choose a name for the controller class (e.g. SecurityController) [SecurityController]: >

 Do you want to generate a '/logout' URL? (yes/no) [yes]:
 >

 created: src/Security/AppCustomAuthenticator.php
 updated: config/packages/security.yaml
 created: src/Controller/SecurityController.php
 created: templates/security/login.html.twig

 
  Success! 
 

 Next:
 - Customize your new authenticator.
 - Finish the redirect "TODO" in the App\Security\AppCustomAuthenticator::onAuthenticationSuccess() method.
 - Review & adapt the login template: templates/security/login.html.twig.

C:\xampp\htdocs\projet_symfony>php bin/console make:entity

 Class name of the entity to create or update (e.g. AgreeablePopsicle):
 > User

 Your entity already exists! So let's add some new fields!

 New property name (press <return> to stop adding fields):
 > lastname

 Field type (enter ? to see all types) [string]:
 >

 Field length [255]:
 >

 Can this field be null in the database (nullable) (yes/no) [no]:
 >

 updated: src/Entity/User.php

 Add another property? Enter the property name (or press <return> to stop adding fields):
 >


 
  Success! 
 

 Next: When you're ready, create a migration with php bin/console make:migration       


C:\xampp\htdocs\projet_symfony>php bin/console doctrine:schema:update --force

 Updating database schema...

     1 query was executed

                                                                                       
 [OK] Database schema updated successfully!                                            
                                                                                       


C:\xampp\htdocs\projet_symfony>php bin/console make:registration             

 Creating a registration form for App\Entity\User

 Do you want to add a @UniqueEntity validation annotation on your User class to make sure duplicate accounts aren't created? (yes/no) [yes]:
 >

 Do you want to send an email to verify the user's email address after registration? (yes/no) [yes]:
 > no

 Do you want to automatically authenticate the user after registration? (yes/no) [yes]: >

 updated: src/Entity/User.php
 created: src/Form/RegistrationFormType.php
 created: src/Controller/RegistrationController.php
 created: templates/registration/register.html.twig

 
  Success! 
 

 Next:
 Make any changes you need to the form, controller & template.

 Then open your browser, go to "/register" and enjoy your new form!


C:\xampp\htdocs\projet_symfony>composer require easycorp/easyadmin-bundle
Using version ^3.5 for easycorp/easyadmin-bundle
./composer.json has been updated
Running composer update easycorp/easyadmin-bundle
Loading composer repositories with package information
Restricting packages listed in "symfony/symfony" to "5.4.*"
Updating dependencies
Lock file operations: 3 installs, 0 updates, 0 removals
  - Locking easycorp/easyadmin-bundle (v3.5.21)
  - Locking symfony/polyfill-uuid (v1.25.0)
  - Locking symfony/uid (v5.4.3)
Writing lock file
Installing dependencies from lock file (including require-dev)
Package operations: 3 installs, 0 updates, 0 removals
  - Downloading symfony/polyfill-uuid (v1.25.0)
  - Downloading symfony/uid (v5.4.3)
  - Downloading easycorp/easyadmin-bundle (v3.5.21)
  - Installing symfony/polyfill-uuid (v1.25.0): Extracting archive
  - Installing symfony/uid (v5.4.3): Extracting archive
  - Installing easycorp/easyadmin-bundle (v3.5.21): Extracting archive
Generating optimized autoload files
112 packages you are using are looking for funding.
Use the `composer fund` command to find out more!

Symfony operations: 1 recipe (e46a93ebb7c9afd7d06b00a149dc5af7)
  - Configuring easycorp/easyadmin-bundle (>=3.0): From github.com/symfony/recipes:master
Executing script cache:clear [OK]
Executing script assets:install public [OK]

 What's next? 


Some files have been created and/or updated to configure your new packages.
Please review, edit and commit them: these files are yours.


C:\xampp\htdocs\projet_symfony>
C:\xampp\htdocs\projet_symfony>php bib/console make:admin:dashboard
Could not open input file: bib/console

C:\xampp\htdocs\projet_symfony>php bin/console make:admin:dashboard 

 Which class name do you prefer for your Dashboard controller? [DashboardController]:
 >

 In which directory of your project do you want to generate "DashboardController"? [src/Controller/Admin/]:
 >



 [OK] Your dashboard class has been successfully generated.                            
                                                                                       

 Next steps:
 * Configure your Dashboard at "src/Controller/Admin/DashboardController.php"
 * Run "make:admin:crud" to generate CRUD controllers and link them from the Dashboard.

C:\xampp\htdocs\projet_symfony>php bin/console make:admin:crud

 Which Doctrine entity are you going to manage with this CRUD controller?:
  [0] App\Entity\User
 > 0

 Which directory do you want to generate the CRUD controller in? [src/Controller/Admin/]:
 >

 Namespace of the generated CRUD controller [App\Controller\Admin]:
 >


 [OK] Your CRUD controller class has been successfully generated.                      
                                                                                       

 Next steps:
 * Configure your controller at "src/Controller/Admin/UserCrudController.php"
 * Read EasyAdmin docs: https://symfony.com/doc/master/bundles/EasyAdminBundle/index.html


C:\xampp\htdocs\projet_symfony>php bin/console make:entity    

 Class name of the entity to create or update (e.g. TinyElephant):
 > User

 Your entity already exists! So let's add some new fields!

 New property name (press <return> to stop adding fields):
 > description

 Field type (enter ? to see all types) [string]:
 > text

 Can this field be null in the database (nullable) (yes/no) [no]:
 > yes

 updated: src/Entity/User.php

 Add another property? Enter the property name (or press <return> to stop adding fields):
 >  


 
  Success! 
 

 Next: When you're ready, create a migration with php bin/console make:migration       


C:\xampp\htdocs\projet_symfony>php bin/console doctrine:schema:update --force

 Updating database schema...

     1 query was executed


 [OK] Database schema updated successfully!


