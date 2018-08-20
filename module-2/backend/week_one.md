## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
POST
GET
PUT
DELETE
PATCH
2. What is Sinatra?
 - A framework written in Ruby on top of a lower level framework called Rack. Used to easily deploy MVC applications.

3. What is MVC?
 - Model, view, controller. A design pattern used to separate application logic to follow single responsibility protocols.

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
 - To ensure we are following a RESTful design pattern

5. What types of variables are accessible in our view templates without explicitly passing them?
 - Instance variables.

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

```ruby
get '/horses' do
  count = 1
  erb :index, :locals => { :index => count }
end
```

8. What's the purpose of ERB?
 - Allows us to create html in ruby files, short for embedded ruby.

9. Why do I need a development AND test database?
 - A test database uses made up data to test method and overall application functionality, by allowing us to create data as we need it and then clean it out later. Development databases allow us to simulate a production environment with our actual data.

10. What is CRUD and why is it important?
 - Create, Read, Update, and Delete. It is important because they are the major actions that are used to create modern web applications.

11. What does HTTP stand for?
 - Hypertext Transfer Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
 - `<% %>` - This executes ruby code but does not render the result.
 - `<%= %>` - This also executes ruby code but does render the result.

13. What's an ORM? What does it do?
 - Object relational mapper. Allows us to work with objects from database data, by making each row an instance of an object, with column headers as that object's attributes.

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?
 - ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
 - GET '/restaurants' - Get a view of all restaurants from index.erb
 - GET '/restaurants/new' - Get a view of the create restaurant file new.erb
 - POST '/restaurants/new' - Creates a new restaurant and saves to a database
 - GET '/restaurants/:id' - Get a view of a specific restaurant in the show.erb page
 - GET '/restaurants/:id/edit' - Get a view of the edit page for a specific restaurant edit.erb
 - PUT '/restaurants/:id' - Updates a resaurant with new/changed data
 - DELETE '/restaurants/:id' - Deletes a specific restaurant from the database

16. What's a migration?
 - A process that builds a database table based on certain column criteria

17. When you create a migration, does it automatically modify your database?
 - No, you must specify the features and attributes of the table you are creating first.

18. How does a model relate to a database?
 - A model interacts with a database with each model class being tied to a table. The model represents one row in our table and the table's columns become the object's attributes.

19. What is the difference between `#new` and `#create`?
 - New initializes a new instance of an object and create takes user given attributes and adds a new row to a table.

20. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
    `

 - `SELECT * FROM animals;`
21. Using the same table, What is the SQL query that will return only the animals that has 4 legs?
 - `SELECT * FROM animals WHERE number_of_legs=4;`
### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
```ruby
CSV.foreach('films.csv', headers: true, header_converter: :symbol) do |r|
  Film.create(
    id: r[:id],
    title: r[:title],
    description: r[:description]
  )
end
```

23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?
 - `activities[:hiking][:supplies] << 'granola bar'`

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.
 - Encapsulation - Keeping objects only knowing a little about each other, and what can be accessed/manipulated to them only.
 - Abstraction - The principle of breaking down a problem to something simple and easy to understand in a real world example, like needing to create software that tracks a classroom, you would abstract that problem to include something like a Student class, a Teacher class, etc.
  - Inheritance - The way objects can relate to one another, usually by thinking in a way that a 'class Dog' *is a* 'class Mammal'. Dogs share a lot of the same qualities as mammals, but distinct enough to be abstracted into their own class while inheriting common traits with its parent class Mammal.
  - Polymorphism - Related to inheritance in a way, its the idea that while objects can inherit state and behavior from a parent class, sometimes it is necessary to override that behavior/state at the 'lower level.'


### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
