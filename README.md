# CISPAPA-GROUP2-ANIMALS
- Remember to `npm i dotenv`
  - This will create a secret environment within the codespace
- Once installed type `touch .env`
  - This will create the environment
- Ethan is the only one with access to URI password
  - If you guys can figure out how to change that, wondeful :)

# Connect your DB to this code
1) Clone this repo onto local environment
2) Change DataBase and Collections names within the code to match personal MongoDB

`` javascript
  app.get('/update', async (req, res) => {

  //get data from the form 

  console.log("in get to slash update:", req.query.ejsFormName); 
  animal_input = req.query.ejsFormName; 

  //update in the database. 
  client.connect; 
  const collection = client.db("***YOURDBNAME***").collection("***YOURCOLLECTIONNAME***");
  await collection.insertOne({ 
    animal: animal_input
  })

  })
``
