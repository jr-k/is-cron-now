# is-cron-now
Checks if cron string is right now

## cron support
This is a javascript cron parser so day of the week is 0 - 6 (1 is monday) and month of the year is 0 -11

this package supports the following cron formats.


```
* * * * * *
| | | | | |
| | | | | +-- Year              (range: 1900-3000 - OPTIONAL)
| | | | +---- Day of the Week   (range: 0-6, 1 standing for Monday)
| | | +------ Month of the Year (range: 0-11)
| | +-------- Day of the Month  (range: 1-31)
| +---------- Hour              (range: 0-23)
+------------ Minute            (range: 0-59)
```

**basic**
```
* * * * * *
```

**With list**
```
* * * * * 2015,2017,2019
```

**With range**
```
* * * * * 2015-2019
```

**With every**
```
* * * * * 2016/2
```

**With range and list**
```
* 0-6,16-23 * * * *
```

## Example

```javascript
isCronNow('* 1 */4 11 * 2016-2019')

isCronNow('24 3 17 11 * 1995')
```

## API

## isCronNow

Takes a cron string

### Syntax

```javascript
  isCronNow('* * * * * *')

  isCronNow('* * * * * 2019')
```

### Parameters

* string
  * cron formated string

### Return value
boolean: cron is now or not
