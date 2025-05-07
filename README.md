# BakeLang

## By Raul Montes

---

### Features

- **Recipe-based structure**: define reusable “recipes” (functions) and invoke them with `Make`.  
- **Ingredient declarations**: `Ingredient name : type;` reserves variables.  
- **Mix / Fold**: assignment via `Mix <expr> into <ingredient>;` (alias `Fold`).  
- **Serve**: output with `Serve <expr>;` (like `print`).  
- **Ask**: prompt the baker for input: `Ask <expr> into <var>;`.  
- **Repeat loops**: `Repeat <start> to <end> { … }` with loop index `i`.  
- **If/Else**: conditional steps: `If (<cond>) then { … } Else { … }`.  
- **Parameterized recipes**: pass ingredients into sub-recipes for complex workflows.

---

### Example: FizzBuzz in BakeLang

```bake
Ingredient i        : int;
Ingredient current  : int;

Repeat 1 to 100 {
  Mix i into current;
  If (current % 15 == 0) then {
    Serve "FizzBuzz";
  } Else {
    If (current % 3 == 0) then {
      Serve "Fizz";
    } Else {
      If (current % 5 == 0) then {
        Serve "Buzz";
      } Else {
        Serve current;
      }
    }
  }
}
