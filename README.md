0x02. AirBnB clone - MySQL

- The console
-> The AirBnB project is a clone web application development.This stage implements a backend interface, or console, to manage program data.

-> The console The console is a command interpreter which reads, interprets and executes commands through a command line interpreter. It uses a base class for command processes.

- Enviroment variables for this project
->HBNB_ENV: running environment. It can be “dev” or “test” for the moment (“production” soon!)
->HBNB_MYSQL_USER: the username of your MySQL
->HBNB_MYSQL_PWD: the password of your MySQL
->HBNB_MYSQL_HOST: the hostname of your MySQL
->HBNB_MYSQL_DB: the database name of your MySQL
->HBNB_TYPE_STORAGE: the type of storage used. It can be “file” (using FileStorage) or db (using DBStorage)

-Console commands

The console can be used to (commands):

* Create new instances of a given class
  $ create <class>

  (hbnb) create BaseModel
  49faff9a-6318-451f-87b6-910505c55907
  (hbnb) all BaseModel

* Destroy a class instance (based on a class ID)
  $ destroy <class><id>

  (hbnb) destroy BaseModel 49faff9a-6318-451f-87b6-910505c55907
  (hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
  ** no instance found **
  (hbnb)
* Print the string representation of a class instance (based on class id)
  $ show <class><id>

  (hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
  [BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293),
  'id': '49faff9a-6318-451f-87b6-910505c55907', 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}

* Print the string representation of all classes
  $ all <class>

  (hbnb) all BaseModel
  ["[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293),
  'id': '49faff9a-6318-451f-87b6-910505c55907', 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}"]

  * Counts the number of instances of a given class
  $ count <class>

  (hbnb) User.count()                                                                                                                                                                                              2
  (hbnb) User.destroy("246c227a-d5c1-403d-9bc7-6a47bb9f0f68")
  (hbnb) User.count()
  1
  (hbnb) User.destroy("Bar")
  ** no instance found **
  (hbnb)

* Updates the class instance of a given ID
  $update <class><id><attribute name>"<attribute value>"

  (hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
  [User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'first_name': 'Betty', 'last_name': 'Bar',
  'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848291),
  'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
  (hbnb)
  (hbnb) User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", "first_name", "John")
  (hbnb) User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", "age", 89)
  (hbnb)
  (hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
  [User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'age': 89, 'first_name': 'John', 'last_name': 'Bar',
  'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 15, 32, 299055),
  'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
  (hbnb)

-Style of SQL files:
$ cat my_script.sql
-- first 3 students in the Batch ID=3
-- because Batch 3 is the best!
SELECT id, name FROM students WHERE batch_id = 3 ORDER BY created_at DESC LIMIT 3;
$
