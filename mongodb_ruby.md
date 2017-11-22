# MongoDB with Ruby

## How to connect Ruby and MongoDB.

Let's create file connect.rb

```ruby

#connect.rb
require 'mongo'
client = Mongo::Client.new('mongodb://127.0.0.1:27017/test')

collection = client[:people]

docs = [ { _id: 1, name: 'Steve', hobbies: [ 'hiking', 'tennis', 'fly fishing' ] },
{ _id: 2, name: 'Sally', hobbies: ['skiing', 'stamp collecting' ] } ]

puts collection.find( { name: 'Sally' } ).first

```
Let's see what is that meaning.

Load MongoDB driver for Ruby

```require 'mongo' ``` 

Create and connect to database "test" 

``` client = Mongo::Client.new('mongodb://127.0.0.1:27017/test') ``` 

Add and use collection "people"

``` collection = client[:people]```

Add data to collection "people"

```ruby
docs = [ { _id: 1, name: 'Steve', hobbies: [ 'hiking', 'tennis', 'fly fishing' ] },
{ _id: 2, name: 'Sally', hobbies: ['skiing', 'stamp collecting' ] } ] 
```

Get data from collection with query.

`puts collection.find( { name: 'Sally' } ).first`

Update data.

`result = collection.update_one( { 'name' => 'Sally' }, { '$set' => { 'phone_number' => "555-555-5555" } } )`



