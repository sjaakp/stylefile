jQuery Stylefile
================

File input HTML controls are notorious because they are almost impossible to style by means of CSS. Each browser implements the file input in it's own way. 

**Stylefile** is a jQuery widget that takes over the HTML file input control and allows it to be styled like the rest of the page. In addition, it gives the user more feedback on the selected file.

## Dependencies ##

**Stylefile** is a simple jQuery control. It's only dependency is jQuery.

## Usage ##

#### Load resources ####

At the end of the `body` part, load the jQuery library:
 
    <script src="http://code.jquery.com/jquery-2.1.1.min.js"></script>
    
And the **Stylefile** code:

    <script src="jquery.stylefile.js"></script>

#### Set-up ####

Stylefile is initialised like:

    $(<selector>).stylefile(<options>);

Preferably, this is done in the `document.ready` handler, like:

    <script>
        $(document).ready(function () {
            $("#fileInput").stylefile({
                ... Stylefile options ...
            });
        });
    </script>

To select all file inputs on a page, use something like:

    <script>
        $(document).ready(function () {
            $("[type=file]").stylefile({
				btnText: "Choose image to upload...",
                ... other Stylefile options ...
            });
        });
    </script>
 
## Options ##

#### btnClass ####

The classname(s) of the 'Browse' button. Default is: `"btn btn-default"` (consistent with Bootstrap CSS).

#### btnText ####

Text of the 'Browse' button. Default: `"Browse"`.

#### decimals ####

Number of decimals in the 'nice_nbytes' presentation of the filesize. Default: `3`.

#### infoClass ####

The classname(s) of the informative text. Default is `"text-muted"`, another Bootstrap classname.

#### infoTemplate ####

Template for the informative text. It is a fragment of HTML, in which the following subtexts are replaced by information about the selected file:

- `{filename}` the name of the selected file
- `{imgsize}`	the image size, in pixels (*w* x *h*)
- `{nbytes}` the file size in bytes
- `{nice_nbytes}` the file size in a more readable format.

Default: `'{filename}&emsp;<span class="imgsize">{imgsize}</span><br /><span class="filesize">{nice_nbytes} ({nbytes} bytes)</span>'`
