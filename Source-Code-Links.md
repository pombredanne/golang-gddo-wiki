Package documentation pages automatically link identifiers and file names to source code hosted on version control services known to GoDoc.org. 

The go-source meta tag is used to specify links to source code on services not known to GoDoc.org. 
The go-source meta tag is similar to the vanity path go-import meta tag and is specified in the same resource as the go-import meta tag.

The structure of the go-source meta tag is:

    <meta name="go-source" content="prefix home directory file">

The prefix field is the import path corresponding to the repository root.

The home field is the URL of the repository's home page.

The directory field is a URL template for a page listing the files in the
package. The following substitutions are made in the directory template:

    {dir} - The import path with prefix and leading "/" trimmed.
    {/dir} - If {dir} is not the empty string, then {/dir} is replaced by "/" +
             {dir}. Otherwise, {/dir} is replaced with the empty string.

The file field is a URL template for a link to a line in a source file. The
following substitutions are made in the file template:

    {file} - The name of the file
    {line} - The decimal line number.

_Note:_ The [current implementation](https://github.com/golang/gddo/blob/d5e22321f6d50a058e175b602f2cc55a66a62a18/gosrc/gosrc.go#L379-L390)
imposes a few additional restrictions to the description above. In order for the file field to have an
effect (and not have unexpected adverse effects), these rules must be followed until the implementation is fixed:

- The file field URL template must contain at least one instance of `{file}`.
- If a `#` is present in the URL template, all instances of `{file}` must come before the `#`.
  All instances of `{file}` that come after `#` will not be substituted.
- Instances of `{line}` are optional, but if they are to be included, then the file field
  must contain `#` and all instances of `{line}` must be after the `#`. Instances of `{line}` that come
  before `#` will not be substituted.
- In order for `{line}` substitutions to be made, no more than one `#` character must appear in the file field.
- It's okay for `%` to be present after `#`, but not before.

The meta tag content attribute must contain four fields. Use "_" to fallback to
GoDoc.org's defaults for home, directory and file.

Here's an example of the go-import and go-source meta tags for the
gopkg.in/yaml.v2 package:

    <meta name="go-import"
        content="gopkg.in/yaml.v2 git https://gopkg.in/yaml.v2">
    <meta name="go-source"
        content="gopkg.in/yaml.v2 _ https://github.com/go-yaml/yaml/tree/v2{/dir} https://github.com/go-yaml/yaml/blob/v2{/dir}/{file}#L{line}">
