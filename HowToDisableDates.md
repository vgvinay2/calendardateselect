As documented in the [Demo](InstallTheDemo.md) and CalendarDateSelectParameters:

This disables all dates after the beginning of today:
```
<%= calendar_date_select_tag "birth_day", "", :valid_date_check => "date < (new Date()).stripTime()" %>
```

This disables all dates before the beginning of today:
```
<%= calendar_date_select_tag "birth_day", "", :valid_date_check => "date.stripTime() > (new Date()).stripTime()" %>
```

Use can use this to disable weekends, holidays, anything, really.  Be creative :)