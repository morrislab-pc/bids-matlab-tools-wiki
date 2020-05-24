Clone the source code of bids-validator from https://github.com/bids-standard/bids-validator.git. Follow their instruction to install all dependencies: https://github.com/bids-standard/bids-validator#development.

Use the tool [pkg](https://www.npmjs.com/package/pkg) to build the executables. The [bids-validator](https://www.npmjs.com/package/bids-validator) is written in ES6 Javascript. The current NodeJS version (as of this writing May 2020) is node12 and it doesn't support ES6's new import/export syntax by default. Instead, it supports ES5 syntax. **pgk** uses NodeJS to compile source code thus will encounter errors if we run it on the bids-validator code as is. We need to translate ES6 syntax into ES5 syntax first before running **pkg**.

The tool for converting Javascript versions (also known as *transpiling*) is [babel](https://babeljs.io/). Babel is already a dependency of the bids-validator. Create a new directory called *es5transpiled*, and transpile the source code of bids-validator/bids-validator into it.

After that, use **pkg** to build the executable, calling on the bin script, with the command pkg -d bin
