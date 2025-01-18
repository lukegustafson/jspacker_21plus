# JSPacker 2:1-Plus

This is a "packer" program for JavaScript, intended for use in code golf. Given JavaScript source code as input, it will attempt to produce an equivalent program that uses fewer Unicode characters. However, the result will be longer in bytes, so it has little practical usage outside of code golf.

This program is intended to be run with Node.js. (It's also easy to modify it to run on other JS platforms: search for "process" and replace it with something else.) To use the program, you can either:
* Edit the `to_pack` variable on the first line of `packer_21.js`, then run it with `node packer_21`
* Put your program in the first argument on the command line: `node packer_21 "my code here"`

By default, the program will print info on its attempts at packing. If you only want it to output the final result, you may append "--quiet" to the command line: `node pack_21 "my code here" --quiet`

# How it works

See a complete write-up [here](https://www.luke-g.com/unicode-packing-in-javascript-the-21-plus-packer/). The general idea is given by the code

```eval(unescape(escape`packed_data`.replace(/uD./g,``)))```

This can achieve 2:1 packing (of ASCII source code) by exploiting the way Unicode surrogate pairs work. The 2:1-plus packer will try alternative regular expressions that sometimes allow 3:1 or even 4:1 packing of certain patterns.

# Testing

A small test suite is available and can be run by calling the function `run_tests()`.

# License

CC0. You may modify and distribute as you please.
