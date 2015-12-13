# HistoryManager.js
Manage an history.

---
Because entries are add depending on the timestamp, don't use intensively like this :
```javascript
for(var i = 0; i < 10; i++) {
	historic.addEntry(i, 'add entry '+i);
}
//to many entries at the same timestamp.
//They will erase each other.
```
---

#HowTo

##Init :
```javascript
var historic = new historyManager();
```

##addEntry(data, message):
Each entries are store in a the historic with the timestamp of creation.
```javascript
historic.addEntry({data: 'foo'}, 'My first entry');
historic.addEntry({data: 'bar'}, 'My second entry');
```

##getAllEntries():
```javascript
var entries = historic.getAllEntries();
//{
//	actual:  {
//		1450042106464: {data: 'bar', message: 'My second entry'}
//	},
//	next:  {},
//	past:  {
//		1450042106460: {data: 'foo', message: 'My first entry'}
//		1450042106458: {data: 'toto', message: ''}
//		1450042106456: {data: 'tata', message: ''}
//		1450042106454: {data: 'titi', message: ''}
//	}
//}
```