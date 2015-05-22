## Install as a git submodule ##

```
git submodule add git://github.com/timcharper/calendar_date_select.git vendor/plugins/calendar_date_select
```

## Not using rails 2.1? ##

```
git clone git://github.com/timcharper/calendar_date_select.git vendor/plugins/calendar_date_select && rm -rf vendor/plugins/calendar_date_select/.git
```

## Don't have git? ##

Packages exist for most OS's (including Windows and Mac OSX).  Go [here](http://git.or.cz/) find one.

## Don't want to install git? ##

You can download CDS from the Github [download](http://github.com/timcharper/calendar_date_select/downloads/) section.  Both tar and zip formats are available.

Just extract the package to your rails application, under `vendor/plugins`, so that the directory `vendor/plugins/calendar_date_select` exists.