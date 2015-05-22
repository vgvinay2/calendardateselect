The localization scripts provided with CalendarDateSelect will automatically do this.  However, here's how to do it properly:

```
// Make Saturday the first day of the week:

Date.weekdays = $w("S S M T W T F");
Date.first_day_of_week = 6;

// Make Monday the first day of the week:
Date.weekdays = $w("M T W T F S S");
Date.first_day_of_week = 1;
```