# Must See Movies: Graphical User Interface (GUI)

## Walkthrough video

[Here is a walkthrough video for this project.](https://share.descript.com/view/aGvwjU9hVXx)

[You can see the Git commits I made during the video here.](https://github.com/demostudent24/msm-gui/commits/main)

## Objective

In this project, you will continue your work on Must See Movies (MSM). This time, you will add a Graphical User Interface (GUI) allowing users to **c**reate, **r**ead, **u**pdate, and **d**elete into your database tables.

Here is your target: [msm-gui.matchthetarget.com](https://msm-gui.matchthetarget.com/)

This project includes automated tests, so click on this button to get started:

LTI{Load MSM GUI assignment}(https://grades.firstdraft.com/launch)[S9ymPy6WCsn18gLbByVbZQ7k]{vfdtzJb5bLYqYwuqgeRKpc5d}(10)[MSM GUI Project]

Then, fork the repository and create your Codespace.

Be sure to run `rake sample_data` at a bash prompt to hydrate your development database with some sample data. Remember, you can use `rails console` and the live app preview route `/rails/db` to explore your database tables whenever you need to. 

Review the [lesson on MSM Queries](https://learn.firstdraft.com/lessons/126-msm-queries) if you get stuck. The [lesson on forms](https://learn.firstdraft.com/lessons/102-query-strings-and-forms) may also be useful, since this project involves a lot of form building. You can also "View source" on the target to copy and paste some starter code to build out your forms.

When you `bin/dev` and have a look around live app preview, you will find that it is a solution to MSM Queries. Try and run `rake grade` and you will see that all the specs from that project are contained here, and they are already passing! However, there are still a number of failing specs, waiting for you to match the target by building out the CRUD GUI.

## A few hints

### Redirecting

Rather than `render`ing a view template at the end of a controller action, you can instead redirect the user to another route you've defined in your `config/routes.rb` with the `redirect_to` method:

```ruby
def delete_this
  the_id = params.fetch("path_id")
  contact = Contact.where({ :id => the_id })

  contact.destroy

  redirect_to("/contacts")
end
```

### Prepopulating forms

You can prepopulate a form input using the `value=""` attribute:

```html
<form action="">

  <label for="image_field">Image</label>
  <input id="image_field" type="text" name="query_image" value="e.g. https://example.com/some_image.jpg">

  <button>Click here</button>	
</form>
```

Here is the rendered form:

<form action="">

  <label for="image_field">Image</label>
  <input id="image_field" type="text" name="query_image" value="e.g. https://example.com/some_image.jpg">

  <button>Click here</button>	
</form>


---

- Approximately how long (in minutes) did this lesson take you to complete?
{: .free_text_number #time_taken title="Time taken" points="1" answer="any" }
	
---
