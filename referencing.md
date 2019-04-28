# Referencing in CRUD Mongoose

## Single ObjectId reference
### Reference other models by id
Sub docs are difficult when it comes to updating, because all duplicates must be updated. But we can reference by ID to get around this.


Add this to your Fruits model
```javascript
    const mongoose = require('mongoose');
    const Schema = mongoose.Schema;
    mongoose.connect('mongodb://localhost:27017/farm');

    const fruitSchema = new Schema({
      name: { type: String, required: true },
      color: { type: String, required: true },
      readyToEat: String,
      farm: { type: Schema.Types.ObjectId, ref: 'Farm' } //the farm property is just an id of another object
    });
    
    const Fruit = mongoose.model('Fruit', fruitSchema);
    modules.export = Fruit;
```

Create a Farm Model and add this farm model

```javascript
    const farmSchema = new Schema({
      name: { type: String }
    });

    
    const Farm = mongoose.model('Farm', farmSchema);
    modules.export = Farm
```


```javascript
  
    const Farm = require('./model/farm'); //in model folder farm.js
    
    const farm = new Farm({name: 'Misk Farm'});
    
    farm.save(()=>{
      const fruit = new Fruit({title:'Awesome Title', farm: farm._id});
      fruit.save(()=>{
        showAll();
      });
    });

    const showAll = () => {
      Fruit.find({})
      .populate('farm') //add farm information to fruits
      .exec((error, fruits) => { //dynamically switch out any ids with the objects they reference
        console.log(fruits);
        
      })
    };
```
