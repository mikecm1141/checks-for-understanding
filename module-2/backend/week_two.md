## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
 * ActiveRecord is an object relational mapper. It interacts with a database for us
 and gives us Ruby objects in return. It allows us to fully interact with our data
 by adapting to our database environment and dealing with queries through a more
 Ruby like method interface.
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

* .all
* .find
* .find_by
* .order
* .select
* .group
* .join
* .pluck
* .offset
* .destroy
* .update
* .limit
* .update
* .not
* .create
* .count
* average
* maximum
* minimum

We have access through to them through inheritance from ActiveRecord.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

`Team.find(4).name`

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

6. Define foreign key, primary key, and schema.
 * Foreign key: A primary key's column in another table.
 * Primary key: A unique, usually incrementing key in a table that uniquely identifies that row of information.
 * Schema: The layout, design, implementation, etc. of a database, with its tables and their columns and attributes.
7. Describe the relationship between a foreign key on one table and a primary key on another table.
 * A foreign key on a table will reference the primary key of another table. This enables you to powerfully connect different tables and relate them to one another.
8. What are the parts of an HTTP response? Status code, response header, and a body.


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources

Choose One:
* I feel comfortable with the content presented this week
