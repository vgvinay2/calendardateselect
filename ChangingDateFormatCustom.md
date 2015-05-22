## One ##

in environment.rb, add the following lines:

```

CalendarDateSelect::FORMATS[:my_custom] = {
# Here's the code to pass to Date#strftime
  :date => "%Y-%m-%d",
  :time => " %I:%M %p",  # notice the space before time.  If you want date and time to be seperated with a space, put the leading space here.

  :javascript_include => "format_my_custom"
}

```

## Two ##

Now, create the following javascript file:

/public/javascripts/calendar\_date\_select/format\_my\_custom.js

```
Date.prototype.toFormattedString = function(include_time)
{
  // Implement me
}

Date.parseFormattedString = function(string) 
{
  // Implement me
}

```

See this file for an example of what to implement

[/public/javascripts/calendar\_date\_select/format\_hyphen\_ampm.js](http://calendardateselect.googlecode.com/svn/tags/calendar_date_select/public/javascripts/calendar_date_select/format_hyphen_ampm.js)

## Three ##

Don't forget to also include:

```
CalendarDateSelect.format = :my_custom
```

in your environment.rb file.  If you set this up properly, and include your javascripts using <%= calendar\_date\_select\_includes %>, all your javascripts will be properly loaded.

## Conclusion ##

If you make your own custom date format, and want to be super cool and contribute it, post it to the google groups mailing list:

http://groups.google.com/group/calendar_date_select