# Dune project that depends on csexp

This project demonstrates a bug in package management where the csexp dependency is not built in some cases. To reproduce, build dune from source ind put it in your PATH as `dune`. Then run:

```
dune pkg lock
dune build
```

In some cases this will print:
```
File "dune", line 3, characters 12-17:
3 |  (libraries csexp))
                ^^^^^
Error: Library "csexp" not found.
-> required by _build/default/foo.exe
-> required by alias all
-> required by alias default
```
