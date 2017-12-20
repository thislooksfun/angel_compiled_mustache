angel_compiled_mustache
=================

[![Travis](https://img.shields.io/travis/thislooksfun/angel_compiled_mustache.svg)](https://travis-ci.org/thislooksfun/angel_compiled_mustache)
[![Pub](https://img.shields.io/pub/v/angel_compiled_mustache.svg)](https://pub.dartlang.org/packages/angel_compiled_mustache)

This is an Angel wrapper for the lightweight [compiled_mustache](https://github.com/thislooksfun/compiled_mustache) render engine.


# Installation
In `pubspec.yaml`:

```yaml
dependencies:
    angel_compiled_mustache: ^1.1.0
```

# Usage
```dart
configureServer(Angel app) async {
  // Run the plug-in
  await app.configure(compiled_mustache(new Directory('views')));
  
  // Render `hello.mustache`
  await res.render('hello', {'name': 'world'});
}
```

# Options
- **fileExtension**: The file extension to search for.
    Default is `.mustache`.
- **defaultLayout**: The default layout file to use if none is specified during the render process.
    Default is `main`
- **layoutsPath**: The path within the viewsDirectory to search for layouts in.
    Default is `./layouts`
- **pagesPath**: The path within the viewsDirectory to search for pages in.
    Default is `./pages`
- **partialsPath**: A path within the viewsDirectory to search for partials in.
    Default is `./partials`.
- **fileSystem**: The FileSystem to use to find the above paths.
    Default is `const LocalFileSystem()`