As of CalendarDateSelect 1.2.1, you can specify default options that will be passed to every calendar\_date\_select control.

In environment.rb:

```
  CalendarDateSelect.default_options.update(:popup => 'force')
```