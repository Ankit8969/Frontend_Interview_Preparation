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
