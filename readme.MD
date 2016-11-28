# Blockly Colour Gradient

Serves a JS class that can add a vertical or horizontal colour gradient to Google Blockly's blocks.

## Sample Usage
`Blockly.Blocks['example'] = {
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
};`