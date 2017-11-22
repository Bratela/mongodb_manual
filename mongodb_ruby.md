### MongoDB with Ruby

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
Let's sea what is that meaning.

```require 'mongo' ``` 

Load MongoDB driver for Ruby

``` client = Mongo::Client.new('mongodb://127.0.0.1:27017/test') ``` 

Create and connect to database "test" 

``` collection = client[:people]```

Add  and use collection "people"

```ruby
docs = [ { _id: 1, name: 'Steve', hobbies: [ 'hiking', 'tennis', 'fly fishing' ] },
{ _id: 2, name: 'Sally', hobbies: ['skiing', 'stamp collecting' ] } ] 
```
Add data to collection "people"

`puts collection.find( { name: 'Sally' } ).first`


Get data from collection wit query.
