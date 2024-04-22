Getting Started
The fx utility operates in two primary modes: a reducer and an interactive viewer.

Quick Start
To initiate the interactive mode, pipe a JSON into fx:

sh
$ curl ... | fx
Alternatively, specify the filename directly:

sh
$ fx data.json
JSON Processing

npx

deno
sh
$ cat file.json | npx fx .field
In fx, arguments are treated as JavaScript functions. Input data is passed sequentially through each provided function:

sh
echo '{"name": "world"}' | fx 'x => x.name' 'x => `Hello, ${x}!`'
For easier access to input data:

Use this or x to reference the input.
Start expressions with . to avoid using the x => x notation.
sh
echo '{"name": "world"}' | fx '.name' '`Hello, ${this}!`'
You can also utilize standard JavaScript functions:

sh
echo '{"name": "world"}' | fx 'Object.keys'
Advanced Usage
Stream Processing
fx can handle a stream of JSON objects and apply arguments to each object:

sh
echo '{"name": "hello"}\n{"name": "world"}' | fx '.name'
For collective processing of a JSON stream as a single array, use the --slurp or -s flag:

sh
echo '{"name": "hello"}\n{"name": "world"}' | fx --slurp '.map(x => x.name)' '.join(", ")'
Non-JSON Data
For non-JSON content, use the --raw or -r flag:

sh
ls | fx -r '[x, x.includes(".md")]'
Combine --raw and --slurp (or -rs) to process as a single string array:

sh
ls | fx -rs '.filter(x => x.includes(".md"))'
Utilize the skip symbol in fx to skip printing certain results:

sh
ls | fx -r '.includes(".md") ? this : skip'
Built-in Functions
fx comes equipped with several useful functions: uniq, sort, groupBy, chunk, zip.

sh
cat file.json | fx 'uniq' 'sort' 'groupBy(x => x.name)'
fx is also promise-compatible:

sh
echo '"https://medv.io/*"' | fx 'fetch' '.text()'
Syntactic Sugar
fx provides shortcuts for commonly-used operations:

Use a shortcut for the map function:
sh
curl https://api.github.com/repos/antonmedv/fx/commits | fx 'map(.commit.message)'
There's a special notation for the flatMap function:
sh
curl https://api.github.com/repos/kubernetes/kubernetes/issues | fx '.[].labels[].name'
Configuration: .fxrc.js
fx can recognize the .fxrc.js file, either in the current directory or home directory. Here's how you can define custom functions:

js
global.myFunction = x => x + 1
Invoke your custom function in fx:

sh
echo '1' | fx 'myFunction'
Streaming Mode
fx is designed to handle both line-delimited JSON and concatenated JSON streaming:

sh
echo '
> {"message": "hello"}
> {"message": "world!"}
> ' | fx .message
hello
world!
Interactive Mode
While in interactive mode, press ? to display a list of available shortcuts.

Search
Initiate a search by pressing / and entering a regex pattern. Navigate using n (next) and N (previous).

Text Selection
Text selection in fx differs due to mouse event redirection to stdin. Depending on your terminal, use specific key combinations to select text:

Key	Terminal
Option+Mouse	iTerm2, Hyper
Fn+Mouse	Terminal.app
Shift+Mouse	Linux
