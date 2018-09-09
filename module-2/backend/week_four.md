## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
 * A small file 4KB in size that can store information about a user between HTTP sessions.
2. What’s the difference between a session and a cookie?
 * A cookie is stored on the client side while a session is stored server side. This enables it to be much more secure than a cookie.
3. What’s a flash and when do you want to use flashes?
 * A flash is a message in Rails. You can give the user information about something like a message saying they were successfully logged in or out, or have made changes to something in the database.
4. Why do people say “HTTP is stateless”?
 * Because without something like a cookie or session, it does not remember anything about the client's interaction with the server otherwise.
5. What’s authentication? Explain.
 * Authentication is the process of who or what a user is, and whether they have the right credentials to log in.
6. What’s the difference between authentication and authorization?
 * Authorization deals with what a user is allowed and not allowed to do once logged in, while authentication establishes first that a user has an account and has given the right information for that account.
7. What’s a before filter?
 * Methods you can call before another controller method is ran, useful for things like authentication and authorization.
8. How do we keep track of a user once they’ve logged in?
 * With a session
9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
 * You namespace a resource when you want to have a different controller and view for that resource, like in the case of an admin namespace over some CRUD functionality that a regular user would not have access to. Nesting resources are useful when you have one resource that depends on another.
10. At a high level, what tools can you use to implement authorization? How would you use them?
 * You can use bcrypt, which provides you with several methods such as a SHA256 encryption and an authenticate method that allows you to verify a user's credentials.
11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
 * An enum makes integer values for things like roles be easier for a human to read. The data type in the database should be an integer. You declare enums in the model file for that table.
12. What are some strategies you can use to keep your views DRY?
 * Keeping appropriate logic out of the view. Using helper methods to help organize repeated code into one location for easy adjustments and debugging.


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```  

```ruby
holidays = []
given.each do |element|
  holidays << element[:holiday].fetch_values(:name)
  holidays.flatten!.sort!
end
holidays.each do |holiday|
  puts holiday
end
```
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?

"$300".gsub(/\D\./,'').to_i
=> 300

"300.00".gsub(/\D\./,'').to_i
=> 300


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources

Choose One:
* I feel confident about the content presented this week
