# Metadata tags

all the spacetime related information can be found in tags prefixed by `77223`.

`77223001` is the tag for chunk customisation. The standard format is the following:
```
{
  “77223001”: {
    chunks: [<chunkName>]
    name: <string>,
    logo: <url>,
    image: <url>,
    portal: <url>,
    planet: <url>
  }
}
```
Exept `chunks`, all the other fields are facultatives. Field that are not customized will be set to the default values.

