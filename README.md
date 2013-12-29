# Ruby Todos 1 0 Core Features 
 
##Learning Competencies 

##Summary 

 This is the first of several iterations towards building a single-user command-line TODO application.  Each iteration will involve addinging new commands and features.

From the user's perspective, we want to build something that works like this:

```text
$ ruby todo.rb add Bake a delicious blueberry-glazed cheesecake
$ ruby todo.rb list
$ ruby todo.rb delete <task_id>
$ ruby todo.rb complete <task_id>
```

Your text file (an example is included in the Original gist) will be simple.  Just task descriptions each on their own line.  Keep in mind that you will eventually have more information included, this is why we want you to use the CSV format.

Example:  

```text  
Bake a delicious blueberry-glazed cheesecake  
Go play miniature golf with Mike Tyson  
Become a World-Class Developer  
````

### Learning Goals

This application has all the moving parts of an MVC application: user input, display code, and data persistence.  It's important to think about what *responsibilities* this application has to fulfill.

Keep things like the [single responsibility principle](http://en.wikipedia.org/wiki/Single_responsibility_principle) and [separation of concerns](http://en.wikipedia.org/wiki/Separation_of_concerns) in mind as you decide what objects and classes belong in your application.

As you work through the iterations, pay close attention to how *change* impacts your application.  When a new feature is added how many files do you have to change?  How frustrating is it to make those changes?
 
## Objectives

### Enumerate the responsibilities

Start by enumerating the responsibilities of your TODO application.  These aren't just the user-facing commands like "add", "delete", etc.  They're also back-end responsibilities like reading and writing from the `todo.csv` file, parsing command-line arguments, and printing the "interface" to the console.

Each responsibility should map to a concrete unit of Ruby code.  For example,

<table class="table table-striped table-bordered">
  <tr>
    <th>Responsibility</th>
    <th>Code world</th>
  </tr>
  <tr>
    <td>Initialize an empty TODO list</td>
    <td>
      <code>list = List.new</code>
    </td>
  </tr>
  <tr>
    <td>Add a task to a TODO list</td>
    <td>
      <code>list.add(Task.new("walk the dog"))</code>
    </td>
  </tr>
  <tr>
    <td>Get all the tasks on a TODO list</td>
    <td>
      <code>tasks = list.tasks</code>
    </td>
  </tr>
  <tr>
    <td>Delete a particular task from a TODO list</td>
    <td><code>???</code></td>
  </tr>
  <tr>
    <td>Complete a particular task on a TODO list</td>
    <td><code>???</code></td>
  </tr>

  <tr>
    <td>Parse the command-line arguments and take the appropriate action</td>
    <td><code>???</code></td>
  </tr>
  <tr>
    <td>Parse the <code>todo.csv</code> file and wrap each entry in easier-to-manipulate Ruby objects</td>
    <td><code>???</code></td>
  </tr>
  <tr>
    <td>There are other responsibilities.  What are they?</td>
    <td></td>
  </tr>
</table>

### Implement the list command

When you run

```text
$ ruby todo.rb list
```

your application should print out a list of all the TODOs. For example:

```text
$ ruby todo.rb list
1. Bake a delicious blueberry-glazed cheesecake
2. Write up that memo and fax it out
3. Conquer the world
```

You'll have to design and build basic controller and model code to make this work.  For example, how does your program know the user wants to "add" a task to their list?

### Implement the add command

Requirements:

- A user can add (append) a task to their TODO list

It should work like this

```text
$ ruby todo.rb add Walk the dog
Appended "Walk the dog" to your TODO list...
$
```

### Implement the delete command

Requirements:

- A user can delete a specific task from their TODO list

It should work like this

```text
$ ruby todo.rb list
1. Bake a delicious blueberry-glazed cheesecake
2. Write up that memo and fax it out
3. Conquer the world

$ ruby todo.rb delete 3
Deleted "Conquer the world" from your TODO list...

$ ruby todo.rb list
1. Bake a delicious blueberry-glazed cheesecake
2. Write up that memo and fax it out

$
```

### Implement completeness

Requirements:

- A user can complete a specific task from their TODO list
- A completed TODO task will be identified as such when a user uses the `list` command

**Note**: This will require changing the format of `todo.csv` and the code that parses it.

### Extra Credit: Human Readable File

Here's the deal:  Google just LOVES your new command line todo app.  And they're ready to buy you out for millions if only you can change the CSV file to a human readable file, so that it can be printed out easily.  They also want the app to be able to handle commas in the task description - something a CSV file doesn't accommodate very easily.

Here's the way the file should be saved:

```text
1. [ ]  Bake a delicious blueberry-glazed cheesecake
2. [X]  Write up that memo and fax it out
3. [ ]  Conquer the world
```

*(the brackets indicate whether the task has been completed or not)*

What factors do you need to take into account to save this data correctly?  How does this change the parsing (besides not being able to use the CSV class)?  

Update your app to accommodate this new feature!
 

##Releases
###Release 0 

##Optimize Your Learning 

##Resources