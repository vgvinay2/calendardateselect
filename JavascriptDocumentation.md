The most basic syntax for CalendarDateSelect is:
```
new CalendarDateSelect( "form_element_id" );
```

Options are passed as a hash, in the second parameter:
```
new CalendarDateSelect( $(this).previous(), {year_range:10} );
```

  * `year_range: 10 // Show +/- 10 years from the current year in the year selector `
  * `year_range: [1950,2005] // Show years 1950 through 2005 in the year selector `
  * `popup_by: "element_id" // Most useful when using hidden fields to store the date.  Specify an element where you want calendar select to appear next to. `
  * `month_year: "label" // Show a label instead of drop-downs for the month / year.  Defaults to "dropdowns" `
  * `close_on_click: false // don't auto-close the calendar when clicking a day.  This defaults to false when time is involved, and true when time is not involved. `
  * `minute_interval: 1 // Allow every minute to be selected.  The default is "5" `

## Callbacks ##

All callbacks are executed from the context of the target form element (meaning, `this.value` will get the value of the field).  A few useful things to know:


```
this.calendar_date_select; // Accesses the instance of the CalendarDateSelect control bound to this control
this.calendar_date_select.date; // A Date object representing the beginning of the current month viewed
this.calendar_date_select.selected_date; // A Date object representing the current date selected.  NULL when no date selected.
	
{
	onchange: function() { alert('changed'); },  // Tell calendar date select to execute code when the date value is changed.  By default, this inherits the onchange property set on the target form element.  If you're using an editable text box for a target form element, you'd be well to use the default. 
	after_navigate: function() { /* js code here */ } }, // Executed when the month is changed.  You could put an !AJAX hook here to update the calendar to highlight certain dates on the picker, or something. 
	before_show: function() { /* js code here */ } }, // You could use this to change the month / year / form value before calendar date select is shown.
	after_show: function() { /* js code here */ } },
	before_close: function() { /* js code here */ } },
	after_close: function() { /* js code here */ } }
}
```


Here are some examples how to do things with calendar\_date\_select.js, without using the rails helpers: