Most of the parameters here are shown on the [demo](http://electronicholas.com/calendar) page.

## :embedded ##

Put the calendar straight into the form, rather than using a popup type of form.

```
  <%= calendar_date_select_tag "name", "2007-01-01", :embedded => true %>
```

## :hidden ##

Use a hidden element instead of a text box for a pop up calendar.  Not compatible with :embedded => true.  You'll probably want to use an onchange callback to do something with the value.

```
<span id='cds_value' /> 
<%= calendar_date_select_tag "hidden_date_selector", "", :hidden => "true", :onchange => "$('cds_value').update($F(this));" %>
```

## :image ##

Specify an alternative icon to use for the date picker.

To use /images/groovy.png:

<%= calendar\_date\_select\_tag "altered\_image", "", :image => "groovy.png" %>

## :minute\_interval ##

Specifies the minute interval used in the hour/minute selector.  Default is 5.

```
<%= calendar_date_select_tag "month_year_selector_label", "", :minute_interval => 15 %>
```


## :month\_year ##

Customize the month and year selectors at the top of the control.

Valid options:
  * "dropdowns" (default) - Use a separate dropdown control for both the month and year
  * "label" - Use static text to show the month and the year.

```
 <%= calendar_date_select_tag "month_year_selector_label", "", :month_year => "label" %>
```

## :popup => 'force' ##

Forces the user to use the popup calendar by making it's text-box read-only and causing calendar\_date\_select to override it's default behavior of not allowing selection of a date on a target element that is read-only.

```
  <%= calendar_date_select_tag "name", "2007-01-01", :popup => "force" %>
  <%= calendar_date_select_tag "month_year_selector_label", "", :popup => :force %>
```

## :time ##

Show time in the controls.  There's three options:

  * `true` - show an hour/minute selector.
  * `false` - don't show an hour/minute selector.
  * `"mixed"` - Show an hour/minute selector, but include a "all day" option - allowing them to choose whether or not to specify a time.

## :default\_time ##

Specify default time using JavaScript Date object or Ruby Time object.

```
  <%= calendar_date_select_tag "p_date_and_time", nil, :time => true, :default_time => "new Date('Feb 18, 2007 5:45 pm')" %>
  <%= calendar_date_select_tag "p_date_and_time", nil, :default_time => Time.parse("January 2, 2007 5:00 PM") %>
  <%= calendar_date_select_tag "e_date_and_time", nil, :embedded => true, :default_time => Date.parse("January 2, 2007") %>
```

## :year\_range ##

Limit the year range.  You can pass in an array or range of ruby Date/Time objects or FixNum's.

```
<%= calendar_date_select_tag "e_date", nil, :year_range => 10.years.ago..0.years.from_now %>
<%= calendar_date_select_tag "e_date", nil, :year_range => [0.years.ago, 10.years.from_now] %>
<%= calendar_date_select_tag "e_date", nil, :year_range => 2000..2007 %>
<%= calendar_date_select_tag "e_date", nil, :year_range => [2000, 2007] %>

```

## :valid\_date\_check ##

Documented in [HowToDisableDates](HowToDisableDates.md).

## CALLBACKS ##

The following callbacks are available:

  * before\_show / after\_show
  * before\_close / after\_close
  * after\_navigate - Called when navigating to a different month. Passes first parameter as a date object refering to the current month viewed
  * onchange - Called when the form input value changes

```
<%= calendar_date_select_tag "event_demo", "", 
  :before_show => "log('Calendar Showing');" ,
  :after_show => "log('Calendar Shown');" ,
  :before_close => "log('Calendar closing');" ,
  :after_close => "log('Calendar closed');",
  :after_navigate => "log('Current month is ' + (param.getMonth()+1) + '/' + (param.getFullYear()));",
  :onchange => "log('value changed to - ' + $F(this));"
%>

```

All callbacks are executed within the context of the target input element.  If you'd like to access the CalendarDateSelect object itself, you can access it via "this.calendar\_date\_select".

For example:

```

<%= calendar_date_select_tag "event_demo", "", :after_navigate => "alert('The current selected month is ' + this.calendar_date_select.selected_date.getMonth());" ,

```