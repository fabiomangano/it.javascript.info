
<<<<<<< HEAD
Il tag di apertura è `pattern:\[(b|url|quote)\]`.
=======
Opening tag is `pattern:\[(b|url|quote)]`.
>>>>>>> 8d04d0d2db97276dbb2b451c30a7bd3e05d65831

Successivamente per trovare tutto fino al tag di chiusura usiamo il pattern `pattern:.*?` con il flag `pattern:s` per cercare la corrispondenza con ogni carattere inclusa una nuova riga. Per concludere aggiungiamo un riferimento all'indietro per il tag di chiusura.

<<<<<<< HEAD
L'intero pattern risultante è: `pattern:\[(b|url|quote)\].*?\[/\1\]`.
=======
The full pattern: `pattern:\[(b|url|quote)\].*?\[/\1]`.
>>>>>>> 8d04d0d2db97276dbb2b451c30a7bd3e05d65831

In azione:

```js run
let regexp = /\[(b|url|quote)].*?\[\/\1]/gs;

let str = `
  [b]hello![/b]
  [quote]
    [url]http://google.com[/url]
  [/quote]
`;

alert( str.match(regexp) ); // [b]hello![/b],[quote][url]http://google.com[/url][/quote]
```

<<<<<<< HEAD
Si noti che oltre l'escape di `pattern:[` e `pattern:]`, abbiamo dovuto fare l'escape dello slash del tag di chiusura `pattern:[\/\1]`, poiché normalmente lo slash termina il pattern.
=======
Please note that besides escaping `pattern:[`, we had to escape a slash for the closing tag `pattern:[\/\1]`, because normally the slash closes the pattern.
>>>>>>> 8d04d0d2db97276dbb2b451c30a7bd3e05d65831
