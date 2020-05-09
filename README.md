# pypeg2tools
A suite of command line scripts for transforming code with [pypeg2](https://fdik.org/pyPEG/)

The following libraries are included:
* **pypeg2.py** The original copy of pypeg2, provided for convenience
* **pypeg2glsl.py** A complete specification of the glsl 3.3 grammar.
* **pypeg2js.py** A specification for a subset of the javascript grammar for use in porting glsl.
* **pypeg2cpp.py** A specification for a subset of the javascript grammar for use in porting glsl.

The following scripts are included:

* **glsl_js.py** Converts glsl to javascript using [glm-js](http://humbletim.github.io/glm-js/) for linear algebra functionality.
* **glsl_derivative.py** Generates derivatives for simple glsl functions, where able.
* **glsl_simplify.py** Simplifies superfluous expressions within glsl, intended for use within glsl_derivative.py
* **glsl_standardize.py** Standardizes the formatting of glsl code

All scripts share a single common command line user interface, meant to resemble [sed](https://www.gnu.org/software/sed/manual/sed.html). 

You can pass input to any script using pipes:

`echo "float foo(float bar){return 2.0*bar;}" | python3 glsl_js.py`

You can also transform entire files by specifying file names:

`python3 glsl_js.py -f foo.glsl`

If you want to replace the contents of a file, use the `-i` flag:
`python3 glsl_js.py -f foo.glsl`

The following is a full list of command line arguments you can supply to scripts:

* **-f** **--filename** the name of a glsl file to use as input
* **-i** **--in-place** allows the file to be edited, in place
* **-v** **--verbose** shows debug information, if any is provided
