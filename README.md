# Semantic Versioning (SemVer)
The "Semantic Versioning" system based on my practical experience.

## Summary
### Format
```
<semantic-versioning number> = <major>.<minor>.<patch>[-<pre-release>][+<build>]
```

### Attributes
- Core version: `<major>.<minor>.<patch>`
    - Public and stable version.
    - Used for release in production.
- Additional version: `[-<pre-release>][+<build>]`
    - Private and unstable version.
    - Used for development.

### Increments
- `<major>` : increased when making incompatible changes.

- `<minor>` : increased when adding functionality in a backwards compatible manner and reset to 0 when increasing `<major>`.

- `<patch>` : increased when making backwards compatible bug fixes and reset to 0 when increasing `<minor>`.

### E.g.
```
v1.0.0-beta-1.0+ozean-2010.10.10
```

## Specifications
![Semantic Versioning](semantic-versioning.svg)

## Workflow
```
v0.1.0  # Version beta (development phase).
   |    # Make backwards compatible bug fixes.
v0.1.1
   |    # Add functionality in a backwards compatible manner.
v0.2.0
   |    # First release used in production.
v1.0.0  # Version 1.
   |    # Make backwards compatible bug fixes.
v1.0.1
   |    # Add functionality in a backwards compatible manner.
v1.1.0
   |    # Make incompatible changes.
v2.0.0  # Version 2.
   |    # Continue.
  ...
```

## Regular Expression Examinations
- [One with named groups](https://regex101.com/r/Ly7O1x/3)
```
/^(?P<major>0|[1-9]\d*)\.(?P<minor>0|[1-9]\d*)\.(?P<patch>0|[1-9]\d*)(?:-(?P<prerelease>(?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\.(?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\+(?P<buildmetadata>[0-9a-zA-Z-]+(?:\.[0-9a-zA-Z-]+)*))?$/gm
```

- [One with numbered capture groups](https://regex101.com/r/vkijKf/1)
```
/^(0|[1-9]\d*)\.(0|[1-9]\d*)\.(0|[1-9]\d*)(?:-((?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\.(?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\+([0-9a-zA-Z-]+(?:\.[0-9a-zA-Z-]+)*))?$/gm
```

## References
- [Semantic Versioning](https://semver.org)
