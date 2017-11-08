The GoDoc API is comprised of these endpoints:

**api.godoc.org/search?q=`Query`**&mdash;Returns search results for Query, in JSON format.

```json
{
	"results": [
		{
			"path": "import/path/one",
			"synopsis": "Package synopsis is here, if present."
		},
		{
			"path": "import/path/two",
			"synopsis": "Package synopsis is here, if present."
		}
	]
}
```

**api.godoc.org/packages**&mdash;Returns all packages, in JSON format. This API returns all packages, including packages with errors, vendored packages, internal packages and more.

```json
{
	"results": [
		{
			"path": "import/path/one"
		},
		{
			"path": "import/path/two"
		},
		{
			"path": "import/path/three"
		}
	]
}
```

**api.godoc.org/importers/`ImportPath`**&mdash;Returns packages that import ImportPath, in JSON format. Not recursive, direct imports only.

```json
{
	"results": [
		{
			"path": "import/path/one",
			"synopsis": "Package synopsis is here, if present."
		},
		{
			"path": "import/path/two",
			"synopsis": "Package synopsis is here, if present."
		}
	]
}
```

**api.godoc.org/imports/`ImportPath`**&mdash;Returns packages that ImportPath imports, in JSON format. Not recursive, direct imports only.

```json
{
	"imports": [
		{
			"path": "import/path/one",
			"synopsis": "Package synopsis is here, if present."
		},
		{
			"path": "import/path/two",
			"synopsis": "Package synopsis is here, if present."
		}
	],
	"testImports": [
		{
			"path": "import/path/three",
			"synopsis": "Package synopsis is here, if present."
		}
	]
}
```

A [[plain text interface|Plain-Text-Interface]] to GoDoc.org is also available.