How to localize

# Introduction #

Localization is now possible in CalendarDateSelect.  However, since there are so many different approaches to localization, I didn't want to get in the way of any particular system.  Therefore, there are certain extensible points of calendar date select that will let you integrate the plug-in with whatever localization system you choose to use.

# Details #

Here is one way to localize.  Somewhere in your page, before displaying your calendars, put code in like this:

## Manual translation ##
```
<script type="text/javascript">
  _translations = {
    "OK": "OK",
    "Now": "Ahora",
    "Today": "Hoy"
  }

  Date.weekdays = $w("D L Ma Mi J V S");

  Date.months = $w("Enero Febrero Marzo Abril Mayo Junio Julio Agosto Septiembre Octubre Noviembre Deciembre" );
  
</script>

<%= calendar_date_select_tag "my_field", nil %>
```

## Translation using gettext ##

If you're using gettext, you can do the following:

```
<script type="text/javascript">
  _translations = {
    "OK": "<%=_("OK")%>",
    "Now": "<%=_("Ahora")%>",
    "Today": "<%=_("Hoy")%>"
  }

  Date.weekdays = $w("<%=_("D L Ma Mi J V S")%>");

  Date.months = $w("<%=_("Enero Febrero Marzo Abril Mayo Junio Julio Agosto Septiembre Octubre Noviembre Deciembre")%>");
  
</script>

<%= calendar_date_select_tag "my_field", nil %>
```