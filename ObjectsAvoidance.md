# Introduction #

The easiest way to avoid obstacles is use switches on arms and legs.


# Details #

I added the following code to the basic Arduino firmware, into the loop():
```
  if(digitalRead(7))
  {
    delay(500);  
    RSSendCommand(RSStop);
    delay(300);  
    RSSendCommand(RSWalkBackward);
    delay(2000);        
    RSSendCommand(RSStop);
    delay(300);  
    RSSendCommand(RSTurnLeft);
    delay(1000);
    RSSendCommand(RSStop);
    delay(300); 
    RSSendCommand(RSWalkForward);
    delay(500);    
  }
```
for the left side switches which we have on pin 7,
and almost the same code for the right side.

Note that on bumping into the object robot says "Eh" - it's a preprogrammed action. So I added many delays. In other case, robot won't execute such command as he will be busy "Eh"-ing.