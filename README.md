# polymer-scroll-threshold

This element is a port of `core-scroll-threshold` to polymer 1.0.  
You can learn more of it <a href="https://www.polymer-project.org/0.5/docs/elements/core-scroll-threshold.html">here</a>.

### Info
`polymer-scroll-threshold` is an utility element that listens for scroll events from a scrollable region and fires events to indicate when the scroller has reached a pre-defined limit, specified in pixels from the upper and lower bounds of the scrollable region.  
  
This element may wrap a scrollable region and will listen for scroll events bubbling through it from its children. In this case, care should be taken that only one scrollable region with the same orientation as this element is contained within. Alternatively, the `scroll-target` property can be set/bound to a non-child scrollable region, from which it will listen for events.

Once a threshold has been reached, a `lower-trigger` or `upper-trigger` event will be fired, at which point the user may perform actions such as lazily-loading more data to be displayed. After any work is done, the user must then clear the threshold by calling the `clearUpper` or `clearLower` methods on this element, after which it will begin listening again for the scroll position to reach the threshold again assuming the content in the scrollable region has grown. If the user no longer wishes to receive events (e.g. all data has been exhausted), the threshold property in question (e.g. `lower-threshold`) may be set to a falsy value to disable events and clear the associated triggered property.

### Install  
To-do  

### Demo
To-do

### Contacts
Email: Mazzarolomatteo@gmail.com
