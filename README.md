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


Then you can call the date time picker like this

```javascript
<script type="text/javascript">
	$(document).ready(function() {
	$('#datetimepicker1').datetimepicker({
	  language: 'pt-BR',
	  forbiddenDates:[
		'12/03/2013',
		'14/03/2013',
		'15/03/2013'
	  ],
	  pickTime:false
	});
	});
	</script>
```

You can refer the [demo](https://github.com/wanxsb/bootstrap-datetimepicker/blob/master/demo/demo1.html) in this project.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
