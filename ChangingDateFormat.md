## Some of the available date formats ##

| **Name** | **Format** |
|:---------|:-----------|
| :natural | January 2, 2007 5:30 pm |
| :hyphen\_ampm | 2007-01-31 5:30 pm |
| :iso\_date | 2008-31-01 17:30 |
| :finnish | 31.1.2008 17:30 |
| :american | 1/31/2008 5:30 pm |

... for more formats, look at the top of lib/calendar\_date\_select.rb

( note - this only works when you are using using **<%= calendar\_date\_select\_includes %>** in your layout )

## Implementing your own date formats ##

ChangingDateFormatCustom