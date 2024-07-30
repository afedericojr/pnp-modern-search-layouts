
# Tags display options #

This is a few options for displaying tags in a list layout.

Out of the box the tags looks like this:

![Outofthebox](/Results/Handlebars/List%20Tag%20options/asserts/OutOfTheBox_tags.png)

## Simple layout ##
The List Tags Simple option looks like this by adding a div and a class handle the CSS:


![Simple](/Results/Handlebars/List%20Tag%20options/asserts/simple_tags.png)


## Advanced layout ##
The List Tags Advanced option looks like this by adding a div and a class handle the CSS:

The List Tags Advanced option looks like this using the same css class as the simple option and making it a link, as shown below.
As of July 30, 2024, the trim helper function no longer appears to be part of the PnP Modern Search solution. 
Instead, use the {{split}} handlebars function.

```html
{{#each (split (slot item @root.slots.Tags) ';') as |tag|}}
    {{#with (split tag '|')}}
    <div class="tagstest">
        <i class="ms-Icon ms-Icon--MapPin" aria-hidden="true"></i>
        <a href="?q=Tags:'{{[2]}}'" data-interception="off">           
                {{[2]}}
        </a>
    </div>
    {{/with}}
{{/each}}
```

![Advanced](/Results/Handlebars/List%20Tag%20options/asserts/advanced_tags.png)

