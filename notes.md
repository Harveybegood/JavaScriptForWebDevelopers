### Chapter13 - Events
##### Cross-Browser Event Object
- Method of addHandler() is attached to an object called EventUtil.
- EventUtil is object that will be to aid in handling cross-browser differences.
```javascript
  var EventUtil = {
    addHandler: function(element, type, handler){
    // element -> the element that is passed in, type -> the type of the element such as click, false -> indicate the bubbling phase
      if(element.addEventListener){
        element.addEventHandler(type, handler, false);
      }else if(element.attachEvent){
        element.attachEvent("on" + type, handler);
      }else{
        element("on" + type) = handler;
      }
    },
    removeHandler: function(element, type, handler){
      if(element.removeEventListener){
        element.removeEventListener(type, handler, false);
      }else if(element.detachEvent){
        element.detachEvent("on" + type, handler);
      }else{
        element("on" + type) = null;
      }
    }
  };
```
- above version can be augmented with methods that equalize the differences:
```javascript
  var EventUtil = {
    addHandler: function(element, type, handler){
      // code removed for printing
    },
    getEvent: function(event){
      return event ? event : window.event;
    },
    getTarget: function(event){
      return event.target || event.srcElement;
    },
    preventDefault: function(event){
      if(event.preventDefault){
        event.preventDefault();
      }else{
        event.returnVFalue = false;
      }
    },
    removeHandler: function(element, type, handler){
      //code removed for printing
    },
    stopPropagation: function(event){
      if(event.stopPropagation){
        event.stopPropagation();
      }else{
        event.cancelBubble = true;
      }
    }
  };
