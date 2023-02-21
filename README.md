# CISPAPA-GROUP2-ANIMALS
# Connect your DB to this code
1) Clone this repo onto local environment
2) Remember to `npm i dotenv`
- This will create a secret environment within the codespace
- Once installed type `touch .env`
  - Ethan is the only one with access to URI password
  - If you guys can figure out how to change that, `wonderful`:sunglasses: 
3) Change DataBase and Collections names within the code to match personal MongoDB
```javascript
try{
    client.connect; 
    const collection = client.db("***YOURDBNAME***").collection("***YOURCOLLECTIONNAME***");
    // const collection = client.db("papa").collection("dev-profiles");
    const result = await collection.find().toArray();
    //const result = await collection.findOne(); 
    console.log("cxnDB result: ", result);
    return result; 
  }
  catch(e){
      console.log(e)
  }
  finally{
    client.close; 
  }
```
```javascript
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
```
4) Run on `Localhost:3000`
- test code, put in an animal, and click submit
- Check console log for name submitted
  - should look like:
```diff
$ node app.js
in the node console
Example app listening on port 3000
in get to slash update: Cow
```
5) Check MongoDB for "Cow"
- If Cow is in your DB, then you have succesfully C & R'd
