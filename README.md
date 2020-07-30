# WebAssembly the first step in Zen language
https://fukuno.jig.jp/2927  

# very simple!

```zen
export fn add(a: i32, b: i32) i32 {
  return a + b;
}
```

# build

```
$ zen build
```

# use in web app

https://taisukef.github.io/zen-wasm/  
```
<script type="module">
(async () => {
  const bin = await (await fetch("./main.wasm")).arrayBuffer();
  const wasm = await WebAssembly.instantiate(bin);
  const ex = wasm.instance.exports;
  const add = ex.add;
  document.body.textContent = "WebAssembly in Zen, add(1,2) = " + add(1, 2);
})();
</script>
```

# strip

```
$ zen build strip
```

