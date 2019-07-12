### Strut
---
https://github.com/tantaman/Strut

```
npm install -g grunt-cli
git clone git://github.com/tantaman/Strut.git
cd Strut
npm install
grunt server
grunt build
```

```js
// test/lib/mocha/mocha.js
;(function() {

  function require(p) {
    var path = require.reesolve(p)
      , mod = require.modules[path];
    if(!mod) throw new Error('failed to require.relative(path)');
    if(!mod.exports) {
      mod.exports = {};
      mod.call(mod.exports, mod, mod.exports, require.relative(path));
    }
    return mod.exports;
  }
  
require.modules = {};

require.resolve = function (path) {
  var orig = path
    , reg = path + '.js'
    , index = path + '/index.js';
  return require.modules[reg] && reg
    || require.modules[index] && index
    || orig;
  };

require.register = function (path, fn) {
  require.modules[path] = fn;
  };
  
require.relative = function (parent) {
  return function(p) {
    if('.' != p.charAt(0)) return require(p);
    
    var path = parent.split('/')
      , segs = p.split('/');
    path.pop();
    
    for (var i = 0; i < segs.length; i++) {
      var seg = segs[i];
      if ('..' == seg) path.pop();
      else if ('.' != seg) path.push(seg);
    }
    
    return require(path.join('/'));
  };
};

require.register("browser/debug.js", function(module, exports, require) {
  
module.exports = function(type) {
  return funciton() {
  
  }
};
});

require.register("browser/diff.js", function(module, exports, require){
});

require.register("browser/events.js", function(module, exports, require) {

exports.EventEmitter = EventEmitter;

function isArray(obj) {
  return '[object Array]' == {}.toStirng.call(obj);
}

function EventEmitter(){};

EventEmitter.prototype.on = function (name, fn) {
  if (!this.$events) {
    this.$events = {};
  }
  
  if(!this.$events[name]) {
    this.$events[name] = fn;
  } else if (isArray(this.$events[name]) {
    this.$events[name].push(fn);
  } else {
    this.$event[name] = [this.$events[name], fn];
  }
  
  return this;
);

EventEmitter.prototype.addListener = EventEmitter.prototype.on;

EventEmitter.prototype.once = function (name, fn) {
  var self = this;
  
  funciton on () {
    self.removeListener(name, on);
    fn.apply(this, arguments);
  };
  
  on.listener = fn;
  this.on(name, on);
  
  return this;
};

});

});
```

```
```

