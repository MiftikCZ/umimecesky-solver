## umimecesky-solver
kod který napíše odpověd k dané otázce na umimecesky.cz

# kód
```js
function solve() {
  document.getElementById("cards").innerHTML += "<div id='cardss'></div>"
   try {
      var odpovedi = questions.find(q => q.id == window.location.pathname.split("/")[2])
      var explanation = odpovedi.options.find(o => o.correct === 1)
      var odpoved = explanation.option[0][1]
      document.getElementById("cardss").innerHTML = `<p style="font-size:34px;">Odpověd: ${odpoved}</p>`
      console.log("Odpověd je: <"+odpoved+">")
   } catch (error) {}
}
solve()
```

# lepší verze
nefunguje úplně nejlíp 
```js
var odpovedi = questions.find(q => q.id == window.location.pathname.split("/")[2])
var explanation = odpovedi.options.find(o => o.correct === 1)
var odpoved = explanation.option[0][1]
$("span:contains("+odpoved+")").click()
console.log("Odpověd je: <"+odpoved+">")
```

# první verze
100% funguje ale je nejhorší
```js
var odpovedi = questions.find(q => q.id == window.location.pathname.split("/")[2])
var explanation = odpovedi.options.find(o => o.correct === 1)
console.log("Odpověd je: <"+explanation.option[0][1]+">")

// -> Odpověd je: <...>
```

<br><br>

Podobné kódy: [<img src="https://camo.githubusercontent.com/b079fe922f00c4b86f1b724fbc2e8141c468794ce8adbc9b7456e5e1ad09c622/68747470733a2f2f6564656e742e6769746875622e696f2f537570657254696e7949636f6e732f696d616765732f7376672f6769746875622e737667" alt="gh" width="18"/>](#/) [MP3Martin/umimecesky-solver](https://github.com/MP3Martin/umimecesky-solver) (*automatické vyplňování a ovládání rychlosti*)
