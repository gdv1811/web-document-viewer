# web-document-viewer
Atalasoft Web Document Viewer repository is for distribution on bower. 

### Installation
You can install this package locally either with bower.
```shell
# To get the latest stable version, use bower from the command line.
bower install web-document-viewer

# To get the specific 10.7.0 version use:
bower install web-document-viewer#10.7.0

# To save the bower settings for future use:
bower install web-document-viewer --save

# Later, you can use easily update with:
bower update
```
> Note that web-document-viewer requires jquery, jquery-ui, jquery.easing, raphael packages as dependencies.

### Licencing 

Web Document Viewer object cross browser client-side script. 
Copyright 2003-2016 Atalasoft Inc. All Rights Reserved.

This source code is property of Atalasoft, Inc. (http://www.atalasoft.com/)
Permission for usage and modification of this code is only permitted 
with the purchase of a source code license.

### Using web-document-viewer
Here is a sample on how to create client-side view for web-document-viewer.
All installed dependencies should be referenced in the head section.
```html
<head  runat="server">
    <meta charset="utf-8" />
    <title>Web Document Viewer Sample</title>
    <link href="bower_components/jquery-ui/themes/base/jquery-ui.css" rel="stylesheet" type="text/css" />
    <link href="bower_components/atalasoft-web-document-viewer/atalaWebDocumentViewer.css" rel="stylesheet" type="text/css" />

    <script src="bower_components/jquery/jquery.min.js" type="text/javascript"></script>
    <script src="bower_components/jquery-ui/jquery-ui.min.js" type="text/javascript"></script>
    <script src="bower_components/jquery.easing/jquery.easing.min.js" type="text/javascript"></script>
    <script src="bower_components/raphael/raphael.min.js" type="text/javascript"></script>

    <script src="bower_components/atalasoft-web-document-viewer/atalaWebDocumentViewer.js" type="text/javascript"></script>
    <style type="text/css">
		html, body, form
	    {	
			width:780px;
			margin:0px;
			padding:0px;
			font-family: sans-serif;
		}
		
		#atala-document-toolbar
		{
		    top:0;
		    left:0;
		    width: 768px;
		    background-color: #eee;
		}
		
		.atala-document-thumbs
		{
		    float:left;
		    display: inline-block;
		    width:150px;
		    height:600px;
		}	
		
		#atala-document-container
		{
			height:600px;
			width: 618px;
			display: inline-block;
		}
	</style>
</head>
<body>
<form id="atala-form" runat="server">
    <div>
        <div id="atala-document-toolbar" class="atala-document-toolbar"></div>
        <div>
            <div id="atala-document-thumbs" class="atala-document-thumbs"></div>
            <div id="atala-document-container" class="atala-document-container"></div>
        </div>
    </div>
</form>

<script>
    var _viewer;
    var _thumbs;

    (function() {
        _viewer = new Atalasoft.Controls.WebDocumentViewer({
            parent: $('#atala-document-container'),
            toolbarparent: $('#atala-document-toolbar'),
            serverurl: 'WDVHandler.ashx',
            savepath: 'Save/',
        });

        _thumbs = new Atalasoft.Controls.WebDocumentThumbnailer({
            parent: $('#atala-document-thumbs'),
            serverurl: 'WDVHandler.ashx',
            viewer: _viewer
        });
    })();
</script>
</body>
```

For demo on how to deploy server-side uning NuGet please see [here](http://atalasoft.github.io/2016/06/21/nuget-tutorial-wdv/)

