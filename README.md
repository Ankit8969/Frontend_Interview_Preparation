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






## Prototye inheritance and Prototype chaining

- Writing the code in this way is not efficient.

```
let obj1 = {
  fname:"Ankit",
  lname:"Kumar",
  fun1:function(){
    console.log(this.fname + " " + this.lname);
  }
}

let obj2 = {
  home:"Forbesganj",
  state:"Bihar",
  fun2:function(){
    console.log(this.home + " " + this.state);
  }
}

obj2.__proto__ = obj1;

let obj3 = {
  college:"MAKAUT",
  branch:"Information Technology",
  fun3:function(){
    console.log(this.college + " " + this.branch);
  }
}

obj3.__proto__ = obj2;

obj3.fun1();
```

## Function.proptotype

- ***In the code If you write like this then, all the function can use the mybind() method
```
Function.prototype.mybind = function (){
  console.log("ANkit Kumar");
}

function fun(){
  console.log("check");
};

fun.__proto__.mybind()
```


## Debouncing
- It is technique which is used to increase the performance of our webpage
- ***eg: In searchbar, we want to trigger someting when user scroll***
- ***Function calls when the time gap b/w to key stroke is more than certan amount of time lik 300ms***

```
<body>
  <input type="text" name="search" id="search" onkeyup="betterFunction()" >
  <script src="index.js"></script>
</body>
```

```
let t = 0;
function getData(){
  // It calls the api and getting the api
  console.log("Counter " + t++);
}

const debounce = function(fn, delay){
  let timer ;
  return function(){
    clearTimeout(timer);
    timer = setTimeout(()=>{
      fn.call(getData);
    }, delay)
  }
}

const betterFunction = debounce(getData, 300);
```


























