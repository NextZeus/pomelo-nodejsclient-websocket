# pomelo-nodejsclient-websocket

## useage

```
var Pomelo = require('pomelo-nodejsclient-websocket');

var pomelo = new Pomelo();



var async = require('async');

async.waterfall([
  function (cb) {
    var host = '127.0.0.1';
    var gatePort = 3014;// gate server client port
    var params = {host: host, port: gatePort};
    
    pomelo.init(params, function(err,resp){
      cb(err);
    });
  },
  function (cb) {
    var route = 'gate.gateHandler.queryEntry';
    var params = {uid : 'pomelo1'};
    
    pomelo.request(route, params, function(err, resp){
      //todo  ....
      cb();
    });
  }
],function(err){
  pomelo.disconnect();
});


```
