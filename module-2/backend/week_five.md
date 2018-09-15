### Week 5 Questions

Re-pull from this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?

 We first must put code into our application layout template that is something like the following:

 ```ruby
 <% flash.each do |type, msg| %>
     <%= content_tag :div, msg, class: type %>
 <% end %>
 ```

 In the controller, we can use the `flash` hash to send a message under a specific context:

 ```ruby
 flash[:notice] = 'Some notice message'
 flash[:success] = 'Some success message'
 flash[:failure] = 'Some failure message'
 ```

2. Where is cart information/temporary information usually stored?

In a session.

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?

A cart is usually a temporary state that a user will only need for one session. We may want to save that information if a user needs to build a cart over the course of a longer time period than one session using our application.

4. What is the purpose of the asset pipeline?

To handle things such as JavaScript, stylesheets, and images in a more efficient way. Things such as JavaScript and stylesheets can be minimized (whitespace removed, variables shortened in length) to make loading times faster for our client.

5. Why do we precompile our assets?

To increase load times for the client and stress on the server.

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
# Generates an html stylesheet link to application.css or some other type of stylesheet.
<%= javascript_include_tag "application" %>
# Generates an html javascript link to our application.js file.
<%= image_tag "rails.png" %>
# Generates an image html tag that links to a thumbprinted image file.
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?

A great README will have information necessary to get the code up and running locally, what dependencies are required to run that particular codebase, and what versions of those to install. The benefits of a README increase the ease of user by the end user, and can help us drive development by coming up with an idea of our application before we have began.

8. What are the top four accessibility issues that we as developers should be aware of?

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

It is an example of a callback. We will find that in our controller.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```

`scope: active, -> { where(active: true) }`

11. What is the difference between a scope and a class method?

To my understanding, scopes are a way to essentially create a class method in one line, sort of
how attr_readers and attr_writers create getter and setter methods for us. I am unsure if there are any
performance benefits from using a scope vs a class method.

### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
       `given[:cart]['48'] = 4`
  12b. How would you increase the quantity of item 29?
       `given[:cart]['29'] -= some_quantity`
  12c. How would you find out how many items your user is thinking about purchasing?
       ```ruby
       given[:cart].inject(0) do |sum, (id, quantity)|
         sum += quantity
       end
       ```

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?
  Polymormphism is the ability with OOP where you can redefine a method's behavior from the behavior it inherits
  from its parent class. My understanding with duck-typing is that our code won't mind if a method inherited from a
  parent class doesn't make absolute sense with that object, we can still treat that object as a 'duck' so to speak. We use
  this in one big way with Rails with inheriting a number of methods from our ApplicationRecord to give us ActiveRecord methods.
  The same scenario can play out in our controller with ApplicationController.
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
