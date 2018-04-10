# imgspect
The imgspect project is the home of two closesly related jQuery plug-ins, the eponymous imgspect and its friendly helper, imgbit.

## imgspect
**imgspect** builds an application for captioning / transcribing select areas of large images.

## imgbit
**imgbit** is the plugin used to display areas you highlight with imgspect as if you cropped them with Photoshop and saved them as new files.

# Use imgspect for...
* Serious research
* Art critiques
* Amusing your friends

## Requirements
* jQuery ( http://jquery.com )
* jQuery UI Draggable ( http://jqueryui.com/draggable )
	* I have experienced problems with jQuery UI 1.10.3 hosted by Google version 1.10.2 is stabler.
		* http://ajax.googleapis.com/ajax/libs/jqueryui/1.10.2/jquery-ui.min.js
		
* menumucil ( https://github.com/caesarfeta/menumucil )
* jslib ( https://github.com/caesarfeta/jslib )
* plopup ( https://github.com/caesarfeta/plopup )

## Install
### Clone the repository and submodules
	cd {% js-dir %}
	git clone https://github.com/PerseusDL/imgspect.git imgspect
	cd imgspect
	git submodule update --init

## Include the necessary files
### imgspect
	<!-- CSS -->
	<link rel="stylesheet" href="{% js-dir %}/imgspect/third_party/menumucil/css/menumucil.css">
	<link rel="stylesheet" href="{% js-dir %}/imgspect/css/imgspect.css">
	<link rel="stylesheet" href="{% js-dir %}/imgspect/css/imgbit.css">
	
	<!-- JS -->
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
	<script src="http://ajax.googleapis.com/ajax/libs/jqueryui/1.10.2/jquery-ui.min.js"></script>
	<script src="{% js-dir %}/imgspect/imgspect.js"></script>
	
	<!-- HTML -->
	<img id="imgspect" src="{% url-to-some-image %}" />
	
	<!-- Start imgspect once image has loaded -->
	<script type="text/javascript">
		$(window).load( function(){
			$( '#imgspect' ).imgspect();
		});
	</script>

### imgbit
	<!-- CSS -->
	<link rel="stylesheet" href="{% js-dir %}/imgspect/css/imgbit.css">
	
	<!-- JS -->
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
	<script src="{% js-dir %}/imgspect/imgbit.js"></script>
	
	<!-- HTML -->
	<a class="imgbit" href="{$ url-to-image %}?x1=0&y1=0&x2=100&y2=100">{% caption %}</a>
	<a class="imgbit" href="{$ url-to-different-image %}?x1=0&y1=0&x2=100&y2=100">{% caption %}</a>
	
	<!-- Start imgbit -->
	<script type="text/javascript">
		$(document).ready( function(){
			$( '.imgbit' ).imgbit();
		});
	</script>

## For further documentation browse the examples

View the examples [here](http://perseids-project.github.io/imgspect/).

### imgspect
	...	see ./examples/imgspect

### imgbit
	... see ./examples/imgbit
