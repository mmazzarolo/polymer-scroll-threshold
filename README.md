# polymer-scroll-threshold

This element is a port of `core-scroll-threshold` to polymer 1.0.  
You can learn more about it <a href="https://www.polymer-project.org/0.5/docs/elements/core-scroll-threshold.html">here</a>.

### Info
`polymer-scroll-threshold` is an utility element that listens for scroll events from a scrollable region and fires events to indicate when the scroller has reached a pre-defined limit, specified in pixels from the upper and lower bounds of the scrollable region.  
  
This element may wrap a scrollable region and will listen for scroll events bubbling through it from its children. In this case, care should be taken that only one scrollable region with the same orientation as this element is contained within. Alternatively, the `scroll-target` property can be set/bound to a non-child scrollable region, from which it will listen for events.

Once a threshold has been reached, a `lower-trigger` or `upper-trigger` event will be fired, at which point the user may perform actions such as lazily-loading more data to be displayed. After any work is done, the user must then clear the threshold by calling the `clearUpper` or `clearLower` methods on this element, after which it will begin listening again for the scroll position to reach the threshold again assuming the content in the scrollable region has grown. If the user no longer wishes to receive events (e.g. all data has been exhausted), the threshold property in question (e.g. `lower-threshold`) may be set to a falsy value to disable events and clear the associated triggered property.

### Install  
- Install it with bower:   
`bower install mazzaaaaa/polymer-scroll-threshold`
  
- Import the element:  
`<link rel="import" href="../bower_components/polymer-scroll-threshold/polymer-scroll-threshold.html">`
  
- Add it to your template:    
`<polymer-scroll-threshold id="threshold" lower-threshold="10" on-lower-trigger="_loadMore" fit></polymer-scroll-threshold>` 
  
- Set the interested node:   
`this.$.threshold.scrollTarget = this.$.scrollableDiv;` 
  
- Handle the the triggered event (`on-lower-trigger` or `on-upper-trigger`) and call `clearLower()`:   
`_loadMore: function() {doSomething(); this.$.threshold.clearLower();}` 
  
  
  
> **Note:**
> The interested node must have a defined witdth and height.  
> You can set scoll-threshold to a paper-header-panel in this way:  
> - `this.$.threshold.scrollTarget = this.$.paperHeaderPanel.$.mainContainer;`  

### Demo
<a href="http://mazzarolomatteo.com/polymer/poly-reddit/">(Look at the bottom of the page)</a>
