## biome-lesson

biomeの自分用のメモ

biomeはリンターとフォーマッターの機能を提供している。たとえば、下記のコードが書いてあるmain.tsファイルがあったとする。
```
const        foo=function(){
   return 0;
   }
  
   let bar         =    3
  
   export    {
                       bar   as bar
   };
```

そこで、
```npx biome format --write ./src/main.ts```
とターミナルで打つと、フォーマットが実行され、

```
const foo = function () {
	return 0;
};

let bar = 3;

export { bar as bar };
```

という風に、インデントやスペースなどを修正してくれる

さらに、
```npx biome lint --write ./src/main.ts```

と打つと、リントが実行され、

```
const foo = () => 0;

const bar = 3;

export { bar };
```

無名関数がアロー関数へと変わって、letを使っていた箇所がconstを使った宣言に変わっている