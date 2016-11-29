# Blockly Colour Gradient

Serves a JS class that can add a vertical or horizontal colour gradient to Google Blockly's blocks (see https://github.com/google/blockly.git). Google Blockly (https://developers.google.com/blockly/) is required for this Addon.

The `setVerticalGradient(block, colours, heights)` function takes a block of Blockly, an object with the keys start and stop which get HTML colours as Hex (e.g #000000) and an object with the keys start and stop which get the height in pixels.

The `setHorizontalGradient(block)` function takes a block and builds a colour gradient with colours of the parent and the current block.

## Sample Usage
```javascript 
Blockly.Blocks['example'] = {
	init: function() {
		this.setHelpUrl("https://www.spe-systemhaus.de/");
		this.setColour("#74A55B");
		this.gradient = new ColourGradient();	/* Creating ColourGradient Object */
		this.appendDummyInput("bla");
		this.setOutput(true, "blubb");
		this.setTooltip("See the colour gradient");
	}, onchange : function() {
		/* Adding a vertical gradient to the example block */
        this.gradient.setVerticalGradient(
            this, { 
                "start" : "#5BA58C",
                "stop" : this.getColour() 
            }, {
                "start" : this.getInput("bla").renderHeight,
                "stop" : this.getHeightWidth().height - this.getInput("bla").renderHeight 
            }
        );
	}
};
```

# Install with Bower

```
bower install --save blockly-colour-gradient
```

# Add to HTML

Add `colour-gradient.js` to your `index.html` *after* all the other blockly scripts.

```
<script src="bower_components/blockly-colour-gradient/colour-gradient.js"></script>
```
