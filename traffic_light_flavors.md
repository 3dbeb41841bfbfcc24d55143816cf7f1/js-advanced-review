# Traffic Light Flavors

## Object Literal

```javascript
var trafficLight = {
  name     : 'Peachtree and North Ave',
  state    : 'red',
  getName  : function() { return this.name;      },
  getState : function() { return this.state;     },
  goGreen  : function() { this.state = 'green';  },
  goYellow : function() { this.state = 'yellow'; },
  goRed    : function() { this.state = 'red';    },
  toString : function() { return this.getName() + ' is ' + this.getState() }
};
```

## Constructor Function:

```javascript
function TrafficLight(name) {
  this.name = name;
  this.state = 'red';
}

TrafficLight.prototype.getName   = function() { return this.name; };
TrafficLight.prototype.getState  = function() { return this.state; };
TrafficLight.prototype.goGreen   = function() { this.state = 'green'; };
TrafficLight.prototype.goYellow  = function() { this.state = 'yellow'; };
TrafficLight.prototype.goRed     = function() { this.state = 'red'; };
TrafficLight.prototype.toString  = function() { return this.getName() + ' is ' + this.getState() };

var trafficLight = new TrafficLight('Peachtree and North Ave');
```

## IIFE

```javascript
var trafficLight = (function() {
  var state = 'red';
  var name  = 'Peachtree and North Ave';
  return {
    getName  : function() { return name;      },
    getState : function() { return state;     },
    goGreen  : function() { state = 'green';  },
    goYellow : function() { state = 'yellow'; },
    goRed    : function() { state = 'red';    }
  };
}());

// or

var trafficLight = (function(theName) {
  var state = 'red';
  var name  = theName;
  return {
    getName  : function() { return name;      },
    getState : function() { return state;     },
    goGreen  : function() { state = 'green';  },
    goYellow : function() { state = 'yellow'; },
    goRed    : function() { state = 'red';    }
  };
}('Peachtree and North Ave'));

// or

function buildTrafficLight(theName) {
  var state = 'red';
  var name  = theName;
  return {
    getName  : function() { return name;      },
    getState : function() { return state;     },
    goGreen  : function() { state = 'green';  },
    goYellow : function() { state = 'yellow'; },
    goRed    : function() { state = 'red';    }
  };
}

var trafficLight = buildTrafficLight('Peachtree and North Ave');
```
