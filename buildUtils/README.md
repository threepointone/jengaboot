#### Fake it til you make it

Jenga currently doesn't allow a jengaroot build rules file to load external dependencies, e.g. [yojson](https://github.com/mjambon/yojson) for parsing our package.json files. Therefore, we've made two bytecode (i.e. cross-platform) executables (which use yojson under the hood, but since it's an executable this no longer matters). One of these takes in a package.json and outputs the `name` field's value to stdout. Another takes in package.json and outputs the `dependencies` JavaScript object keys, one per row. Our jengaroot can therefore call the executables and easily "parse" the output.

The package.json in this directory is only for testing. Compile extractName.re & extractDeps.re (make sure you have yojson installed via `opam install yojson`) and run the executables.
