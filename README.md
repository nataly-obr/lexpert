# lexpert
Unfortunately, our application doesn’t have an interface because of time shortage. To create a database I just run the file named «import_manager.py» for every act I wanted to load.
<br>
<br>**Preparatory steps before running import_manager.py:**
<br> 1. Save attached json file in some folder and to specify the path to this file in the line 18 of predict.py
<br> 2. Open a regulation on «eur-lex» like this one https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX%3A32013R0153
<br> 3. Press «Document information» button (like in the screenshot) and save as an html file ![file](https://user-images.githubusercontent.com/59837137/104319219-9fd01d80-54f1-11eb-85b9-0458169c3760.png)  
<br> 4. Specify the path to the html file in the line 486 of import_manager.py 
<br> 5. Make sure that predict.py and db.py are located together with import_manager.py so import_manager.py can call them
<br> 6. Run import_manager.py
<br> 
<br>**Description:**
<br>import_manager.py calls the file «predict.py» to predict whether text comprises legal terms or other labels. predict.py calls the text entity extraction model deployed on the Google AI Platform. import_manager.py calls the file «db» for modeling database nodes and relationships into Python classes.
<br>data_migration.py is a stand alone file used to transfer data from the local database to the database deployed in the cloud since the cloud database expires every 10 days. So originally import_manager.py writes data to the local db, but to alleviate testing I change path directly to the cloud database (line 83 import_manager.py)
<br> 
<br>If there will be any problems with running files, please let me know.
<br>Best regards, Nataly (Hammurabi AI)
