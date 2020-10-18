# Query and Projection Operators

- Comparison

  - $eq	Matches values that are equal to a specified value.

  - $gt	Matches values that are greater than a specified value.

  - $gte	Matches values that are greater than or equal to a specified value.

  - $in	Matches any of the values specified in an array.

  - $lt	Matches values that are less than a specified value.

  - $lte	Matches values that are less than or equal to a specified value.

  - $ne	Matches all values that are not equal to a specified value.

  - $nin	Matches none of the values specified in an array.
  
- Logical
  
  - $and	Joins query clauses with a logical AND returns all documents that match the conditions of both clauses.
  
  - $not	Inverts the effect of a query expression and returns documents that do not match the query expression.
  
  - $nor	Joins query clauses with a logical NOR returns all documents that fail to match both clauses.
  
  - $or	Joins query clauses with a logical OR returns all documents that match the conditions of either clause.
  
Reference: https://docs.mongodb.com/manual/reference/operator/query/

<br/>

## $eq

Syntax: {field: {$eq: value} }

The $eq operator matches documents where the value of a field equals the specified value.

```
db.inventory.find( { qty: { $eq: 20 } } )
```

- https://docs.mongodb.com/manual/reference/operator/query/eq/

<br/>

## $ne

Syntax: {field: {$ne: value} }

$ne selects the documents where the value of the field is not equal to the specified value. This includes documents that do not contain the field.

```
db.inventory.find( { qty: { $ne: 20 } } )
```

- https://docs.mongodb.com/manual/reference/operator/query/ne/

<br/>

## $in

Syntax: { field: { $in: [<value1>, <value2>, ... <valueN> ] } }

The $in operator selects the documents where the value of a field equals any value in the specified array.

```
db.inventory.find( { qty: { $in: [ 5, 15 ] } } )
```

- https://docs.mongodb.com/manual/reference/operator/query/in/

<br/>

