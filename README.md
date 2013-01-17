# Wistia Lab Tools

This file provides tools to manipulate and preview all Wistia embed
types in the Wistia app.

Check out [the annotated source](http://wistia.github.com/labtools).


## Usage

### Javascript Includes

LabTools requires jQuery and Wistia's E-v1 script.

    <script src="http://https://ajax.googleapis.com/ajax/libs/jquery/1.9.0/jquery.min.js"></script>
    <script src="http://fast.wistia.com/static/E-v1.js"></script>
    <script src="labtools.js"></script>


### Parse an embed code

Take an embed code and parse it so we can query or manipulate it.

    var embedCode = Wistia.EmbedCode.parse("[embed code string]");


### Check the type of embed code

If you're checking against a string:

    Wistia.EmbedCode.isIframe("[embed code string]");
    Wistia.EmbedCode.isPopover("[embed code string]");
    Wistia.EmbedCode.isApi("[embed code string]");

If you want to see what type was returned by
Wistia.EmbedCode.parse:

    embedCode instanceof Wistia.IframeEmbedCode
    embedCode instanceof Wistia.PopoverEmbedCode
    embedCode instanceof Wistia.ApiEmbedCode


### Set options on the embed code

    embedCode.setOption("plugin.my-awesome-plugin.on", true);
    embedCode.extendOption("plugin.my-awesome-plugin", {
      on: true,
      awesome: "yes"
    });
    embedCode.removeOption("plugin.my-awesome-plugin");


### Show the embed code in a text area

    $("textarea#embed_code").val(embedCode.toString());


### Preview the embed code in a div

 There should be a div with id="embed_code_preview"
 somewhere on the page.

    embedCode.previewInElem("embed_code_preview");


### More advanced stuff

For more advanced usage, please take a look at the
[annotated source](http://wistia.github.com/labtools).
