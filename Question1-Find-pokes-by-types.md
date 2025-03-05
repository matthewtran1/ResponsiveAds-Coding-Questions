// You have an array.
// An item of the array has `name`, a string, and `types`, an array of strings.
// The length of `types` in a record can be 1-99 (not always 1-2)
// e.g. [{ name: "bulbasaur", types: ["grass", "poison"] }]
const pokes = getPokes();
console.log("Pokes", pokes);

// Problem 1: Filter by type
// - Populate `answer1` with Pokemon names that contain the type string
const type = "grass";
const answer1 = []; // TODO

```
// check for grass
for (let k = 0; k < pokes.length; k++) {
  if (pokes[k].types.includes(type)) {
    answer1.push(pokes[k].name)
  }
 
};
```

// Problem 2: Filter by types (AND / OR)
// - Populate `answer2Or` with Pokemon names that satisfy AT LEAST ONE of the given types
// - Populate `answer2And` with Pokemon names that satisfy ALL of the given types
// (Note that the length of the given `types` can be 1-99. (not always 1-2))

```
const types = ["bug", "poison"];
const answer2Or = []; // TODO
const answer2And = []; // TODO

// check for all types
for (let i = 0; i < pokes.length; i++) {
  let allTypes = true;
  for (let j = 0; j < types.length; j++) {
    
    // if one type isn't included, break loop
    if (!pokes[i].types.includes(types[j])) {
      allTypes = false;
      break;
      
      
    }
  }
   
  // add if all types is true after the loop
  if (allTypes) {
    answer2And.push(pokes[i].name)
  }
};

// check for at least one type
for (let l = 0; l < pokes.length; l++) {
  for (let m = 0; m < types.length; m++) {
    if (pokes[l].types.includes(types[m])) {
      answer2Or.push(pokes[l].name)
      break;
      }
    }
 };

// See your results in your DevTools console
console.log("Answer 1", answer1);
console.log("Answer 2 (OR)", answer2Or);
console.log("Answer 2 (AND)", answer2And);

// --------------------------------

function getPokes() {
  const elScript = document.querySelector("#pokes");
  const json = elScript.text;
  const data = JSON.parse(json);
  return data;
}

```
// ---------------------------------
// Console

"Answer 1" // [object Array] (8)
["bulbasaur","ivysaur","venusaur","oddish","gloom","vileplume","paras","parasect"]
"Answer 2 (OR)" // [object Array] (26)
["bulbasaur","ivysaur","venusaur","caterpie","metapod","butterfree","weedle","kakuna","beedrill","ekans","arbok","nidoran-f","nidorina","nidoqueen","nidoran-m","nidorino","nidoking","zubat","golbat","oddish","gloom","vileplume","paras","parasect","venonat","venomoth"]
"Answer 2 (AND)" // [object Array] (5)
["weedle","kakuna","beedrill","venonat","venomoth"]
