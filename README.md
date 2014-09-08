Barebone Scaffold
===

[`init`](init)
---

### Initial repository state
![Initial State](http://yuml.me/diagram/plain/class/[Scaffold]-[Workflow|init;release;clean;],[Workflow]-[Templates|base;development;])

### Flow
![init flow](http://yuml.me/diagram/plain/activity/(start)->(check args)-><a>,<a>->(check clean)-><b>,<a>->(check exists)-><c>,<b>->(init defaults)->(end),<b>->(abort)->(end),<c>->(init branch)->(end),<c>->(abort))

### Post-Init repository state
![Post-Init state](http://yuml.me/diagram/plain;dir:LR/class/[Scaffold]-[Workflow|init;release;clean],[Workflow]-[Templates|base;development;{bg:orange}],[Scaffold]-[Base|.gitattributes;{bg:green}],[Scaffold]-[Development|.gitattributes;{bg:green}],[Templates]->[Development],[Templates]->[Base])

[`release`](release)
---

### Flow
![release flow](http://yuml.me/diagram/plain/activity/(start)->(check args)-><a>,<a>->(checkout default base)-><b>,<a>->(checkout base)-><b>,<b>->(merge from deault development)-><c>,<b>->(merge from development)-><c>,<c>->(merge into default release)->(end),
<c>->(merge into release)->(end))

### Post-Release repository state
![Post-Release state](http://yuml.me/diagram/plain;dir:LR/class/[Scaffold]-[Workflow|init;release;clean],[Workflow]-[Templates|base;development],[Scaffold]-[Base|.gitattributes;{bg:orange}],[Scaffold]-[Development|.gitattributes;{bg:orange}],[Scaffold]-[Release{bg:green}],[Release]<-[Development],[Release]<-[Base])

[`clean`](clean)
---

### Flow
![clean flow](http://yuml.me/diagram/plain/activity/(start)->(keep workflow)->(remove branches)->(remove tags)->(end))

### Post-Clean repository state
![Post-Clean State](http://yuml.me/diagram/plain/class/[Scaffold]-[Workflow|init;release;clean;],[Workflow]-[Templates|base;development;])

License
---
[MIT](LICENSE)
