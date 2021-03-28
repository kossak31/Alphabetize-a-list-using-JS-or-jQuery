# Alphabetize-a-list-using-JS-or-jQuery
Alphabetize a list using JS or jQuery

## jQuery
```javascript
var mylist = $('#subcategories');
var listitems = mylist.children('option').get();
listitems.sort(function(a, b) {
  return $(a).text().toUpperCase().localeCompare($(b).text().toUpperCase());
})
$.each(listitems, function(idx, itm) {
  mylist.append(itm);
});

var parent = document.getElementById("subcategories"),
// take items (parent.children) into array
itemsArray = Array.prototype.slice.call(parent.children);
```

## javascript vanilla
```javascript
// sort items in array by custom criteria
itemsArray.sort(function(a, b) {
  // inner text suits best (even when formated somehow)
  if (a.innerText < b.innerText) return -1;
  if (a.innerText > b.innerText) return 1;
  return 0;
});
// reorder items in the DOM
itemsArray.forEach(function(item) {
  // one by one move to the end in correct order
  parent.appendChild(item);
});
```
