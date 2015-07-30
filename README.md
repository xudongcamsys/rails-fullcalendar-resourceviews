#Rails-fullcalendar-resourceviews 
[![Gem Version](https://badge.fury.io/rb/rails-fullcalendar-resourceviews.svg)](http://badge.fury.io/rb/rails-fullcalendar-resourceviews) [![Dependency Status](https://gemnasium.com/peterthecoon/rails-fullcalendar-resourceviews.svg)](https://gemnasium.com/peterthecoon/rails-fullcalendar-resourceviews)

##Installation
Add rails-fullcalendar-resourceviews to your Gemfile:

``` 
gem 'rails-fullcalendar-resourceviews', github: 'xudongcamsys/rails-fullcalendar-resourceviews'
```

Run 

``` 
bundle install
```

Include in application.js

```
//= require fullcalendar
```

Include in application.css.scss

```
*= require fullcalendar
```

##Usage

This fork customized resourceDay view so each day is a horizontal resource, while each column represent a time point, e.g.

| Day                 | 9am           | 10am           |
| ------------------- | ------------- | ------------- |
| 08/01/2015, Sunday  |               |               |
| 08/02/2015, Monday  |               |               |

```javascript
  var resources = [{
    "id":"2015-08-01",  //using date as resource id
    "name":"08/01/2015, Sunday", // resource label text
    "isDate":true //must be true if you specify day as resource, otherwise, fullCalendar will treat all resources within current date
  }, {
    "id":"2015-08-02",
    "name":"08/02/2015, Monday",
    "isDate":true
  }];
  var events = [{
    "id":1,
    "start":"2015-08-01T09:00:00-06:00",
    "end":"2015-08-01T09:30:00-06:00",
    "title":"Grocery shopping",
    "resource":"2015-08-01" // must match resource id
  }, {
    "id":2,
    "start":"2015-08-02T09:30:00-06:00",
    "end":"2015-08-02T10:00:00-06:00",
    "title":"Barber appointment",
    "resource":"2015-08-02"
  }];

  $(document).ready(function() {    
    var calendar = $('#calendar').fullCalendar({
      header: false,
      defaultView: 'resourceDay',
      minTime: 5,
      slotMinutes: 60,
      maxTime:18,
      columnFormat: 'h(:mm)tt',
      resources: resources,
      events: events
    });
  });
```


See the website of the original project for the usage
https://github.com/jarnokurlin/fullcalendar
