# {Yotaka Khaowkomol} MongoDB inlämning

## steg 1 : Skapa en databas

```js
use recept
db.createCollection("recepts")
```

## steg 2 : Lägg till dokument

```js
db.recepts.insertOne({
    name: "Pancakes",
    Ingredienser: ["Flour", "Milk", "Eggs", "Butter", "Sugar", "Baking powder", "Salt"],
    Tillagningstid: 20,
    Tillagningsteg: [
        "Mix flour, sugar, baking powder and salt in a bowl.",
        "In a separate bowl, mix milk, eggs and melted butter.",
        "Combine wet and dry ingredients and mix until smooth.",
        "Heat a pan and pour in pancake batter.",
        "Cook until bubbles form, then flip and cook until golden brown."
    ]
})
```

## steg 3 : Visa alla recept

```js
db.recepts.find()
```

## steg 4 : Uppdatera information för ett specifikt recept

```js
db.recepts.updateOne({name:"Pancakes"},{$set:{Ingredienser:["Flour", "Milk", "Eggs", "Butter", "Sugar", "Baking powder", "Salt","Love"]}})
```

## steg 5 : Ta bort ett recept

```js
db.recepts.deleteOne({name:"Pancakes"})
```

## steg 6 : Lägg till exact 3 recept

```js
db.recepts.insertMany([
    {
        name: "Cheeseburger",
        Ingredienser: ["Nötfärs", "Hamburgerbröd", "Cheddarost", "Lök", "Tomat", "Salat", "Ketchup", "Senap"],
        Tillagningstid: 30,
        Tillagningsteg: [
            "Forma nötfärsen till biffar och krydda med salt och peppar.",
            "Grilla eller stek biffarna i ca 4-5 minuter per sida.",
            "Lägg en skiva cheddarost på biffen och låt smälta.",
            "Montera hamburgarna med bröd, biff, lök, tomat, salat och såser."
        ]
    },
    {
        name: "Macaroni and Cheese",
        Ingredienser: ["Makaroner", "Cheddarost", "Mjölk", "Smör", "Mjöl", "Salt", "Peppar"],
        Tillagningstid: 30,
        Tillagningsteg: [
            "Koka makaronerna enligt anvisningarna.",
            "Smält smöret i en kastrull och vispa i mjölet för att göra en roux.",
            "Tillsätt mjölken och rör tills såsen tjocknar.",
            "Blanda i den rivna osten tills den smälter.",
            "Blanda makaronerna med ostsåsen och gratinera i ugnen om så önskas."
        ]
    },
    {
        name: "Apple Pie",
        Ingredienser: ["Äpplen", "Socker", "sKanel", "Mjöl", "Smör", "Pajdeg"],
        Tillagningstid: 60,
        Tillagningsteg: [
            "Sätt ugnen på 220°C.",
            "Skala och skär äpplena i skivor.",
            "Blanda äpplen med socker och kanel.",
            "Kavla ut pajdegen och lägg i en pajform.",
            "Fyll med äppelmix och täck med mer pajdeg.",
            "Grädda i 45-50 minuter tills gyllene."
        ]
    }
])
```

## steg 7 : Visa alla recept

```js
db.recepts.find()
```

## steg 8 :  visa bara namn och ingredienser

```js
db.recepts.deleteMany({$and:[{Ingredienser: "Sugar"},{Ingredienser: "Salt"}]})
```

## steg 9 : Uppdatera information för många recept

```js
db.recepts.updateMany({},{$set:{Tillagningstid: 45}})
```

## steg 10 : Ta bort många recept

```js
db.recepts.deleteMany({$and:[{Ingredienser: "Sugar"},{Ingredienser: "Salt"}]})
```

## steg 11 : Ta bort alla recept med "wildcard"

```js
db.recepts.deleteMany({name:{$regex:/[a-z]/i}})
```
