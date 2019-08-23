# Session 2 - HTML Forms

## Use forms

So far we've created a page that a user can view, but a lot of the time we want to collect information from the user. This is where *forms* come in!
Sometimes developers get carried away and start managing inputs with JavaScript instead, but really you should use a form! There is so much built in goodness, its going to be faster and means less code = less bugs!

However as a user there is a time and place for a form. For example if you're signing up for a website, don't create a sign up form with lots of inputs and data you want to collect, _just collect the data you absolutely need, when you need it_, because large forms will cause users to abandon your site.

## Use the right input

I'm going to cheat again and link out [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form_%3Cinput%3E_types), which lists all the types of inputs you can have.
I'm going to shout out a few fan favourites:

#### number
Can be used for any number inputs, but also pricing/currency. You can use the min/max attributes to control how small or large the value can get. You can also use a step attribute to define how big the step between numbers are, for example if you wanted two decimal place numbers you'd use a step of 0.01.

#### file
Great one to use if you need to grab a file from the user and upload it, be helpful to your uses and configure it for the file types you want!
```<input placeholder="Select a Photo" name="image" type="file" accept="image/*"/>```
This for example allows you to only upload images, which is really handy as on mobile it will give you the photo reel and camera options, if you didn't have the accept tag it would just bring up the file explorer view which wouldn't be as easy for your users.

#### password
Use this on sign up and login forms and any time you need a password! *Do not use a text input.*

### datalist
This *isn't* an input type but you can use this alongside an input to provide an autocomplete experience that you can control.
You create a `<datalist id="completeme">` with an id you specify in this example completeme. You can then add this to an input with a `list="completeme"` attribute, which references the datalist id. Here's some more [info here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist)!

### Gotcha's
When choosing a input type ensure that it works in all the browsers you are targeting for example `Date type` inputs will not work in *Safari*, just something to watch out for.

## Validation
You can validate what the user input is on your web page, but assuming you are sending this data off somewhere, make sure you validate it on the backend too! Otherwise people will get around your form and start hitting your systems with data trying to break it.

Use the validation methods the form gives you, for example add `required` on the inputs you need.
You can use `min` and `max` on date and number to limit the range of numbers.
You can use `pattern` to specify a text pattern (regex) that the text must match.
Here's [some more info](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Custom_error_messages) on how to include more custom validation

## Other Form elements
There are also your classic dropdown `<select>` [element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) and a `<textarea>` [element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) to include larger blocks of text. These can also be used inside a form alongside the `<input>` elements inside a form.

## Submit/Reset Actions
We now need to do something with the data we've collected in our form, the `<form>` element has a number of [attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) you can set to control how and where your data is sent. (You can also use JavaScript to get the information in a JSON object but we'll cover that in a later session).

These actions can be triggered by a button with `type="submit"` inside the form, when clicked this will trigger all the validation of the form and if its valid submit the form data as you specified in the form attributes.
A button with `type="reset"` when clicked will reset the form back to its initial state which again is awesome, because then you don't have to handle any state.
