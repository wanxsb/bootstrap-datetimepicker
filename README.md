# bootstrap-datetimepicker

This package is forked from the project:[bootstrap-datetimepicker-rails](https://github.com/lubieniebieski/bootstrap-datetimepicker-rails)
	
However, this package has extends the bootstrap-datetimepicker-rails library by add support to set forbidden dates. 

It means that you can set some of the dates which is forbidden to choose by users.

## Installation

The installation is very simple. 

Firstly, you need add these lines to your page header as other bootstrap libraries:

    <script src="../assets/javascripts/bootstrap-datetimepicker.js"></script>
	<link href="../assets/stylesheets/bootstrap-datetimepicker.css" rel="stylesheet">


## Usage

e.g. you can call the date time picker like this simple demo

```javascript
<script type="text/javascript">
	$(document).ready(function() {
		$('#datetimepicker1').datetimepicker({
			language: 'en',
		  disableDateMode:'allow',
			disableDates:[
			'12/03/2013',
			'14/03/2013',
			'15/03/2013'
			],
			pickTime:false,
		  isAllowToShow:function(d, parseDateFn){
		    return (d.valueOf() !== parseDateFn('17/03/2013').valueOf());
		  }
		});
	});
	</script>
```

You can refer the [demo](https://github.com/wanxsb/bootstrap-datetimepicker/blob/master/demo/demo1.html) in this project.


##API

disableDateMode: The option to define the forbidden mode, it can be valued to 'forbidden', 'allow' or 'none'(default value), if it is valued 'forbidden',
disableDates will be used to forbidden part of dates whereas disableDates will be used to allow part of dates if the disableDateMode valued 'allow'. So 
this value will be used together with disableDates

disableDates: define the date array to be forbidden or allowed. this must have the same form of data-format(what is this data-format means? please refer to the demo), or it will not be compiled successfully. Caution: if the data-format has some detail format about hour,minutes,second, please use zero value instead. e.g. if the data-format is 'dd/MM/yyyy hh:mm:ss', please use
'17/03/2013 00:00:00' for the date, or it will mark as wrong.

_isAllowToShow_:Besides, you can also define the function isAllowToShow to check each date by your self. the isAllowToShow should have the following form: function isAllowToShow(date, parseDateFn). when it return true, it means that the date is allowed to show, while false means that it is forbidden to show. If isAllowToShow and disableDateMode are both defined and disableDateMode is not valued 'none', then both option will take effect. however, disableDates will have high priority.
d: the time which is checked selectable. Caustion, this time is corresponding to zero time of each day. 
for the day 2013-03-13, the value of d is correspoding to '13/03/2013 00:00:00'
parseDateFn:a valueable function to parse the data string according to the given data-format .


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
