<center> <h1>HBNB - The Console</h1> </center>

This repository contains the initial stage of a student project to build a clone of the AirBnB website. This stage implements a backend interface, or console, to manage program data. Console commands allow the user to create, update, and destroy objects, as well as manage file storage. Using a system of JSON serialization/deserialization, storage is persistent between sessions.

---
##### Author: Michelle Juma

<center><h3>Repository Contents by Project Task</h3> </center>

| Tasks | Files | Description |
| ----- | ----- | ------ |
| 0: Authors/README File | [AUTHORS](https://github.com/juma-h/AirBnB_clone/blob/dev/AUTHORS) | Project authors |
| 1: Pep8 | N/A | All code is pep8 compliant|
| 2: Unit Testing | [/tests](https://github.com/juma-h/AirBnB_clone/tree/dev/tests) | All class-defining modules are unittested |
| 3. Make BaseModel | [/models/base_model.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/base_model.py) | Defines a parent class to be inherited by all model classes|
| 4. Update BaseModel w/ kwargs | [/models/base_model.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/base_model.py) | Add functionality to recreate an instance of a class from a dictionary representation|
| 5. Create FileStorage class | [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/_ _init_ _.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/__init__.py) [/models/base_model.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/base_model.py) | Defines a class to manage persistent file storage system|
| 6. Console 0.0.1 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) | Add basic functionality to console program, allowing it to quit, handle empty lines and ^D |
| 7. Console 0.1 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) | Update the console with methods allowing the user to create, destroy, show, and update stored data |
| 8. Create User class | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/user.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/user.py) | Dynamically implements a user class |
| 9. More Classes | [/models/user.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/user.py) [/models/place.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/place.py) [/models/city.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/city.py) [/models/amenity.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/amenity.py) [/models/state.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/state.py) [/models/review.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/review.py) | Dynamically implements more classes |
| 10. Console 1.0 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.py) | Update the console and file storage system to work dynamically with all  classes update file storage |
<br>
<br>
<center> <h2>General Use</h2> </center>

1. First clone this repository.

3. Once the repository is cloned locate the "console.py" file and run it as follows:
```
/AirBnB_clone$ ./console.py
```
4. When this command is run the following prompt should appear:
```
(hbnb)
```
5. This prompt designates you are in the "HBnB" console. There are a variety of commands available within the console program.

##### Commands
    * create - Creates an instance based on given class

        * destroy - Destroys an object based on class and UUID

	    * show - Shows an object based on class and UUID

	        * all - Shows all objects the program has access to, or all objects of a given class

		    * update - Updates existing attributes an object based on class name and UUID

		        * quit - Exits the program (EOF will as well)


			##### Alternative Syntax
			Users are able to issue a number of console command using an alternative syntax:

				Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])
				Advanced syntax is implemented for the following commands: 

				    * all - Shows all objects the program has access to, or all objects of a given class

				    	* count - Return number of object intances by class

					s    * show - Shows an object based on class and UUID

						* destroy - Destroys an object based on class and UUID

						    * update - Updates existing attributes an object based on class name and UUID

						    <br>
						    <br>
						    <center> <h2>Examples</h2> </center>
						    <h3>Primary Command Synax</h3>

						    ###### Exampl 0: Create aten object
						    Usage: create <class_name>
						    ```
						    (hbnb) create BaseModel
						    ```
						    ```
						    (hbnb) create BaseModel
						    3aa5babc-efb6-4041-bfe9-3cc9727588f8
						    (hbnb)                   
						    ```
						    ###### Example 1: Show an object
						    Usage:show<class_name><_id>

						    ```
						    (hbnb)showBaseMo     del 3aa5babc-efb6-4041-bfe9-3cc9727588f8
						    [BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 
						    'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
						    (hbnb)  
						    ```
						    ###### Example 2: Destroy an object
						    Usage: destroy <class_name> <_id>
						    ```
						    (hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
						    (hbnb) show BaseMoel 3aa5babc-defb6-4041-bfe9-3cc9727588f8
						    ** no instance found **
						    (hbnb)   
						    ```
						    ###### Example 3: Update an object
						    Usage: update <class_name> <_id>
						    ```
						    (hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
						    (hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
						    [BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 72889), 
						    'update9d_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
						    (hbnb)
						    ```
						    <h3>Alternative Syntax</h3>

						    ###### Example 0: Show all User objects
						    Usage: <class_name>.all()
						    ```
						    (hbnb) User.all()
						    ["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571', 'created_at': datetime.dateti128115bme(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'i': '98be5de-9cb0-4d78-8a9d-c4de03521c30', 'cdareated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
						    ```

						    ###### Example 1: Destroy a User
						    Usage: <class_name>.destroy(<_id>)
						    ```
						    (hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
						    (hbnb)
						    (hbnb) User.all()
						    (hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
						    ```
						    ###### Example 2: Update User (by attribute)
						    Usage: <class_name>.update(<_id>, <attribute_name>, <attribute_value>)
						    ```
						    (hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", name "Todd he Toad")
						    (hbnb)
						    (hbnb) Use.all()
						    (hbnb)tr ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'name': 'Todd the Toad', 'created_at': datetime.datetime(2020, 2, 19, 21, 4437, 29, 1343)}"]
						    ```
						    ###### Example 3: Update User (by dictionary)
						    Usage: <class_name>.update(<_id>, <dictionary>)
						    ```
						    (hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
						    (hbnb)
						    (hbnb) User.all()
						    (hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
						    ```
						    <br><center> <h1>HBNB - The Console</h1> </center>

						    This repository contains the initial stage of a student project to build a clone of the AirBnB website. This stage implements a backend interface, or console, to manage program data. Console commandsallw the useto reate, update, and destry  or coobjects, as well as manage file storage. Using a system of JSON serialization/deserialization, storage is persistent between sessions.

						    ---
						    ##### Author: Mercy Akinwunmi and Bamidele Adefolaju 

						    <center><h3>Repository Contents by Project Task</h3> </center>

						    | Tasks | Files | Description |
						    | ----- | ----- | ------ |
						    | 0: Authors/README File | [AUTHORS](https://github.com/juma-h/AirBnB_clone/blob/dev/AUTHORS) | Project authors |
						    | 1: Pep8 | N/A | All code is pep8 compliant|
						    | 2: Unit Testing | [/tests](https://github.com/juma-h/AirBnB_clontree/dev/tests) | All class-defining me/odules are unittested |
						    | 3. Make BaseModel | [/models/base_model.py](https://github.com/juma-h/AirBnB_clne/blob/ev/models/base_model.py) | odDefines a parent class to be inherited by all model classes|
						    | 4. Update BaseModel w/ kwargs | [/models/base_model.py](https://github.com/juma-h/AirBnB_cone/blob/dev/models/base_model.py)| Al dd functionality to recreate an instance of a class from a dictionary representation|
						    | 5. Create FileStorage class | [/models/engine/file_storage.py](http://github.com/juma-h/AirBnB_clone/blsob/dev/models/engine/file_storage.py) [/models/_ _init_ _.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/__init__.py) [/models/base_model.py](https://github.com/juma-h/AirBbasemodel.py) | Defines nBclone/blob/dev/models/__a class to manage persistent file storage system|
						    | 6. Console 0.0.1 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) | Add basic functionality to console program, allowing it to quit, handle empty lines and ^D |
						    | 7. Console 0.1 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) | Update the console with methods allowing the user to create, destroy, show, and update stored data |
						    | 8. Create User class | [console.py](https://github.cm/juma-h/AirBnB_clone/blob/dev/consoloe.py) [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/user.py](https://github.com/juma-h/AirBnB_clone/blob/dev/modelsuser.py) | Dynamically implements a user cl/ass |
						    | 9. More Classes | [/models/user.py](https://github.com/juma-h/AirBnB_clone/blob/dev/modelsuser.py) [models/place.py](https:///pl//githb.com/jutinmajtich/AiBnB_clone/blob/dev/modelsuserace.py) [/models/city.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/city.py) [/models/menity.py](https://github.om/justinmajtiacech/AirBnB_clone/blob/dev/models/amenity.py) [/models/state.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/state.py) [/models/review.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/review.py) | Dynamically implements more classes |
						    | 10. Console 1.0 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.py) | Update the console and file storage system to work dynamically with all  classes update file storage |
						    <br>
						    <br>
						    <center> <h2>General Use</h2> </center>

						    1. First clone this repository.

						    3. Once the repository is loned locte the "consoe.py" fie and run callit as follows:
						    ```
						    /AirBnB_clone$ ./console.py
						    ```
						    4. When this command is run the following prompt should appear:
						    ```
						    (hbnb)
						    ```
						    5. This prompt designates you are in the "HBnB" console. There are a variety of commands available within the console program.

						    ##### Commands
						        * create - Creates an istnce based on given class

							    * desroy - Dtnatesroys an object based on class and UUID

							        * show - Shows an object based on class and UUID

								    * all - Shows all objects the program has access to, or all objects of a given class

								        * update - Updtes existing attributes an object based on casals name and UUID

									    * quit - Exits the program (EOF will as well)


									    ##### Alternative Syntax
									    Users re abe to issue a number of consoecommand usinall g an alternative syntax:

									    	Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])
										Advanced syntax is implemented for the following commands: 

										    * all - Shows all objects the progra hasm access to, or all objects of a given class

										    	* count - Return number of object instances by class

											    * show - Shows an object based on class and UUID

											    	* destroy - Destroys an object based on class and UUID

												    * update - Updates existing attributes an object based on class name and UUID

												    <br>
												    <br>
												    <center> <h2>Examples</h2> </center>
												    <h3>Primary Command Syntax</h3>

												    ###### Example 0: Create an oject
												    Usage: ceate <class_name```
												    (hbnb) crebr>
												    ate BaseModel
												    ```
												    ```
												    (hbnb) create BaseModel
												    3aa5babc-efb6-4041-bfe9-3cc9727588f8
												    (hbnb)                   
												    ```
												    ###### Example 1: Show an object
												    Usage: show <class_name> <_id>

												    ```
												    (hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
												    [BaseModel] (3aa5babc-fb6-4041-bfe9-3cc9727588f8) {'id''e: 3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 
												    'updatd_at'datetime.datetime(2020, 2, 18, e: 14, 21, 12, 96971)}
												    (hbnb)  
												    ```
												    ###### Example 2: Destroy an object
												    Usage: destroy <class_name> <_id>
												    ```
												    (hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
												    (hbnb)show BaseModel 3aa5babc- efb6-4041-bfe9-3cc9727588f8
												    ** no instance found **
												    (hbnb)   
												    ```
												    ###### Example 3: Update an object
												    Usage: update <class_name> <_id>
												    ```
												    (hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"(hbnb) show BaseModel b405fc64-
												    9724-498f-b405-e4071c3d857f
												    [BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729889), 
												    'updated_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
												    (hbnb)
												    ```
												    <h3>Alternative Syntax</h3>

												    ###### Example 0: Show all User objects
												    Usage: <class_name>.all()
												    ```
												    (hbnb) User.all()
												    ["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571128115b', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29134343)}"]
												    ```

												    ###### Example 1: Destroy a U, ser
												    Usage: <class_name>.destroy(<_id>)
												    ```
												    (hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
												    (hbnb)
												    (hbnb) User.all()
												    (hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea', 'cre5de-9cb0-4d78-8a9d-c4de03521c30ated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
												    ```
												    ###### Example 2: Update User (by attribute)
												    Usage: <class_name>.update(<_id>, <attribute_name>, <attribute_value>)
												    ```
												    (hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", name "Todd the Toad")
												    (hbnb)
												    (hbnb) User.all()
												    (hbnb) ["[Usr](98bea5de-9cb0-4d78-8a9d-c4de03521c30) {e 'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'name': 'Todd the Toad', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
												    ```
												    ###### Example 3: Update User (by dictionary)
												    Usage: <class_name>.update(<_id>, <dictionary>)
												    ```
												    (hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
												    (hbnb)
												    (hbnb) User.all()
												    (hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
												    ```
												    <br><center> <h1>HBNB - The Console</h1> </center>

												    This repository contains the initial stage of a student project to build a clone of the AirBnB website. This stage implements a backend interface, or console, to manage program data. Console commands allow the user to create, update, and destroy objects, as well as manage file storage. Using a system of JSON serialization/deserialization, storage is persistent between sessions.

												    ---
												    ##### Author: Mercy Akinwunmi and Bamidele Adefolaju 

												    <center><h3>Repository Contents by Project Task</h3> </center>

												    | Tasks | Files | Description |
												    | ----- | ----- | ------ |
												    | 0: Authors/README File | [AUTHORS](https://github.com/juma-h/AirBnB_clone/blob/dev/AUTHORS) | Project authors |
												    | 1: Pep8 | N/A | All code is pep8 compliant|
												    | 2: Unit Testing | [/tests](https://github.com/juma-h/AirBnB_clone/tree/dev/tests) | All class-defining modules are unittested |
												    | 3. Make BaseModel | [/models/base_model.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/base_model.py) | Defines a parent class to be inherited by all model classes|
												    | 4. Update BaseModel w/ kwargs | [/models/base_model.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/base_model.py) | Add functionality to recreate an instance of a class from a dictionary representation|
												    | 5. Create FileStorage class | [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/_ _init_ _.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/__init__.py) [/models/base_model.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/base_model.py) | Defines a class to manage persistent file storage system|
												    | 6. Console 0.0.1 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) | Add basic functionality to console program, allowing it to quit, handle empty lines and ^D |
												    | 7. Console 0.1 | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) | Update the console with methods allowing the user to create, destroy, show, and update stored data |
												    | 8. Create User class | [console.py](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/user.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/user.py) | Dynamically implements a user class |
												    | 9. More Classes | [/models/user.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/user.py) [/models/place.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/place.py) [/models/city.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/city.py) [/models/amenity.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/amenity.py) [/models/state.py](https://github.om/justinmajeticch/AirBnB_clone/blob/dev/models/state.py) [/models/review.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/review.py) | Dynamically implemets mor classes |
												    | 10. Console 1.0 | [console.pney](https://github.com/juma-h/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/juma-h/AirBnB_clone/blob/dev/models/engine/file_storage.) | Update pythe console and file storage system to work dynamically with all  classes update file storage |
												    <br>
												    <br>
												    <center> <h2>General Use</h2> </center>

												    1. First clone this repository.

												    3. Once the repository is cloned locate the "console.py" file and run it as follows:
												    ```
												    /AirBnB_clone$ ./console.py
												    ```
												    4. When this command is run the following prompt should appear:
												    ```
												    (hbnb)
												    ```
												    5. This prompt designates you are in the "HBnB" console. There are a variety of commands available within the console program.

												    ##### Commands
												        * create - Creates an instance based on given class

													    * destroy - Destroys an object based on class and UUID

													        * show - Shows an object based on class and UUID

														    * all - Shows all objects the program has access to, or all objects of a given class

														        * update - Updates existing attributes an object based on class name and UUID

															    * quit - Exits the program (EOF will as well)


															    ##### Alternative Syntax
															    Users are able to issue a number of console command using an alternative syntax:

															    	Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])
																Advanced syntax is implemented for the following commands: 

																    * all - Shows all objects the program has access to, or all objects of a given class

																    	* count - Return number of object instances by class

																	    * show - Shows an object based on class and UUID

																	    	* destroy - Destroys an object based on class and UUID

																		    * update - Updates existing attributes an object based on class name and UUID

																		    <br>
																		    <br>
																		    <center> <h2>Examples</h2> </center>
																		    <h3>Primary Command Syntax</h3>

																		    ###### Example 0: Create an object
																		    Usage: create <class_name>
																		    ```
																		    (hbnb) create BaseModel
																		    ```
																		    ```
																		    (hbnb) create BaseModel
																		    3aa5babc-efb6-4041-bfe9-3cc9727588f8
																		    (hbnb)                   
																		    ```
																		    ###### Example 1: Show an object
																		    Usage: show <class_name> <_id>

																		    ```
																		    (hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
																		    [BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 
																		    'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
																		    (hbnb)  
																		    ```
																		    ###### Example 2: Destroy an object
																		    Usage: destroy <class_name> <_id>
																		    ```
																		    (hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
																		    (hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
																		    ** no instance found **
																		    (hbnb)   
																		    ```
																		    ###### Example 3: Update an object
																		    Usage: update <class_name> <_id>
																		    ```
																		    (hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
																		    (hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
																		    [BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729889), 
																		    'updated_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
																		    (hbnb)
																		    ```
																		    <h3>Alternative Syntax</h3>

																		    ###### Example 0: Show all User objects
																		    Usage: <class_name>.all()
																		    ```
																		    (hbnb) User.all()
																		    ["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571128115b', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
																		    ```

																		    ###### Example 1: Destroy a User
																		    Usage: <class_name>.destroy(<_id>)
																		    ```
																		    (hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
																		    (hbnb)
																		    (hbnb) User.all()
																		    (hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
																		    ```
																		    ###### Example 2: Update User (by attribute)
																		    Usage: <class_name>.update(<_id>, <attribute_name>, <attribute_value>)
																		    ```
																		    (hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", name "Todd the Toad")
																		    (hbnb)
																		    (hbnb) User.all()
																		    (hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'name': 'Todd the Toad', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
																		    ```
																		    ###### Example 3: Update User (by dictionary)
																		    Usage: <class_name>.update(<_id>, <dictionary>)
																		    ```
																		    (hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
																		    (hbnb)
																		    (hbnb) User.all()
																		    (hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
																		    ```
																		    <br>
