## How to take command line arguments in NodeJS?

Taking arguments from the command line is very common. You can take certain arguments you need as variables, certain flags, etc. In NodeJS, it's very easy

## Process Object
NodeJS exposes an array of argument values in the form of `process.argv`.

## Example
`index.js`
```js
console.log(process.argv)
```

`Command Line`
```sh
node index.js arg1 arg2 arg3
```

`Output`
```sh
[
  '/usr/local/Cellar/node/16.0.0/bin/node',
  '/Users/username/Code/arg/index.js',
  'arg1',
  'arg2',
  'arg3'
]
```
The first element of the array is the Node Executable file in your machine. The second element is the file you're running.
You can now take the arguments with indexes 2, 3, 4, etc. like `process.argv[2]`, `process.argv[3]`, etc.

But a nicer way would be to remove the first two elements from the array like so
`index.js`
```js
const args = process.argv.slice(2)
console.log(args)
```
`Output`
```sh
[ 'arg1', 'arg2', 'arg3' ]
```

You can also use this way to take flags from the command line like `-s, `-o`, `--help`, etc, like in my [Airtable Url CLI](https://github.com/kavin25/airtable-url-cli).
But, a better way would be to use a third party library like `yargs`. It can really make this much easier and with lesser code.

## Reference
1. https://nodejs.org/en/knowledge/command-line/how-to-parse-command-line-arguments/