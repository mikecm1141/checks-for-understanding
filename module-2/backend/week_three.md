## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
 - `rails new <app_name>`
2. What do Models generally inherit from in rails?
 - `ApplicationRecord`
3. What do Controllers generally inherit from in a rails project?
 - `ApplicationController`
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
 - `resources horses, only: [:show]`
5. What rake task is useful when looking at routes, and what information does it give you?
 - `rails routes` - it gives you the prefix helper, URI path, and the controller action it goes to.
6. What is an example of a route helper? When would you use them?
 - If you have a resource named cats and wanted to create a new one, the route helper would be `new_cat_path`. You use them in test files and links to navigate around your application.
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
 - `_path` returns the relative URI, i.e. `cats_path` = `/cats`, while `_url` returns the full URL, i.e. `cats_url` = `http://www.example.com/cats`
8. What are strong params and why are they necessary?
 - Strong params are params that use the built in require and permit methods. They make sure that only the information for that new row in our database is information we want it to have.
9. What role does `form_for` play in helping us create our forms?
 - It generates forms for us and assigns it to a particular object.
10. How does `form_for` know where to submit the user's input?
 - It uses the routing information we give in config.rb to know which controller and path to use to submit the information.
11. Create a form using a `form_for` helper to create a new `Horse`.
 ```ruby
 <%= form_for @horse do |f| %>
      <%= f.label      :name %>
      <%= f.text_field :name %>

      <%= f.label      :breed %>
      <%= f.text_field :breed %>

      <%= f.submit %>
  <% end %>
  ```

12. Why do we want to validate our models?
  - To make sure information being submitted is in the correct format, is present, or is unique.
13. What are the steps of the DNS lookup?
 - Query -> ISP -> Root Server -> Top Level Domain server -> Authoritative Name Server

### Review Questions
14. Within a feature test and given the following HTML, write the code necessary to target the following section and check the person's name?

  `<section id="personal-info">
    <h3><%= @person.name%></h3>
   </section>
  `

  ```ruby
  within("personal-info") do
      expect(page).to have_content(@person.name)
  end
  ```

15. How would you call the method `prance` from within the method `move` on a `Horse` instance?
``` ruby
def move
      prance
end
```
16. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```

What is the different between how you would return true vs returning 3?

`furniture[:table][:height]`

`furnture[:purchased]`
17. What is inheritance?
 - When a class has a parent class which receives its behavior and state from that parent class.

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
