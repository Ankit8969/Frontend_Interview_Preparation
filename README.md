# Frontend_Interview_Preparation

## call(), apply() and bind()

## call() in js
- The call() allows for a function/method belonging to one object to be assigned and called for a different object.
```

function give_Full_name(first, last){
  this.fname=first;
  this.lname = last;
}

function give_address(fname,lname,city, state){
  give_Full_name.call(this,fname,lname);
  this.city = city;
  this.state = state;
}

let Ankit =new give_address("Ankit","kumar","Bhagalpur","Bihar");

console.log(Ankit);
```


```
```

## sessionStorage()
- sessionStorage is similar to localStorage
- If you print console.log(this) and console.log(window) and console.log(this.wondow) all they print the same
- the difference is that while data in localStorage doesn't expire, data in sessionStorage is cleared when the page session ends.
- Opening multiple tabs/windows with the same URL creates sessionStorage for each tab/window.
- Duplicating a tab copies the tab's sessionStorage into the new tab.
- Closing a tab/window ends the session and clears objects in sessionStorage.

```
this.sessionStorage.setItem('Name', "Ankit");
this.sessionStorage.setItem('Name', "Sonu");
this.sessionStorage.setItem("Roll" , 35);

console.log(this.sessionStorage.getItem('Name'));

this.sessionStorage.removeItem('Name');
console.log(this.sessionStorage);
console.log(this.sessionStorage.length);

sessionStorage.clear();
console.log(this.sessionStorage);

console.log(typeof this.sessionStorage.getItem('Roll'));
```

> SessionStorage is used for storing data on the client side.
> Maximum limit of data saving in SessionStorage is about 5 MB.
> Data in the SessionStorage exist till the current tab is open if we close the current tab then our data will also erase automatically from the SessionStorage.


## localStorage()
***localStorage data for a document loaded in a "private browsing" or "incognito" session is cleared when the last "private" tab is closed.***

- In localStorage we also have all the same function like ***sessionStorage*** 
- window.localStorage.getItem('name')
- window.localStorage.setItem('name','Ankit')
- window.localStorage.removeItem('name')
- window.localStorage.clear()







































