---
description: >-
  Should take in URDF, show the drone in a 3D Env, apply real physics to it,
  useful for PID tuning, should simply then just apply the tune to the airframe.
  Autotuner can be monetized.
---

# Simulation

About URDF\
[https://chat.openai.com/share/22cbef87-4c72-483c-bfd9-f5ed9caae2bd](https://chat.openai.com/share/22cbef87-4c72-483c-bfd9-f5ed9caae2bd)

This is a link to a URDF loader for three.js\
[https://www.npmjs.com/package/urdf-loader](https://www.npmjs.com/package/urdf-loader)

```javascript
// PID Controller in pure Javascript. To be integrated with threlte
// I'm, sure it can be made to look a lot prettier. This is FUGLY.

function PID(p, i, d) {
  this.sampleTime = 100
  this.target = 0
  this.output = 0

  this.errorSum = 0
  this.lastInput = 0
  this.lastTime = Date.now() - this.sampleTime

  this.setTunings(p, i, d)  
}

PID.prototype.setTunings = function(p, i, d) {
  var ratio = this.sampleTime / 1000
  
  this.p = p
  this.i = i * ratio
  this.d = d / ratio
}

PID.prototype.setSampleTime = function(sampleTime) {
  var ratio = sampleTime / this.sampleTime
  
  this.i *= ratio
  this.d /= ratio
  this.sampleTime = sampleTime
}

PID.prototype.setOutputLimits = function(min, max) {
  this.min = min
  this.max = max
}

PID.prototype.setTarget = function(value) {
  this.target = value
}

PID.prototype.compute = function(input) {
  var now = Date.now(),
      timeDiff = now - this.lastTime
  
  if (timeDiff >= this.sampleTime) {
    var error = this.target - input,
        inputDiff = input - this.lastInput
    
    this.errorSum = Math.max(this.min, Math.min(this.max, this.errorSum + (this.i * error)))    
    this.output = Math.max(this.min, Math.min(this.max, (this.p * error) + this.errorSum - (this.d * inputDiff)))
    this.lastInput = input
    this.lastTime = now
  }
                                              
  return this.output
}
                                              
var pid = new PID(875, 0.5, 0.1)
pid.setSampleTime(1000)
pid.setOutputLimits(0, 10000)
pid.setTarget(60)

setInterval(function() {
  var output = pid.compute(50 + (Math.random() * 10))
  console.log(output)
}, 50)
```
