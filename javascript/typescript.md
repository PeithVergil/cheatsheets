Installing the TypeScript compiler
----------------------------------

```bash
npm install -g typescript --prefix=/path/to/directory
```

Make sure you add `/path/to/directory/bin` to the system `$PATH`.


Compiling `.ts` to `.js`
------------------------

Compiling a single TypeScript file. Note that `--outDir` is optional.

```bash
tsc sample.ts --outDir /path/to/output/directory
```

Auto compilation.

```bash
tsc *.ts --watch --outDir /path/to/output/directory
```
