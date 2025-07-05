# Trilium Notes

Trilium Notes is a free and open-source, cross-platform hierarchical note taking application with focus on building large personal knowledge bases.

See [screenshots](https://triliumnext.github.io/Docs/Wiki/screenshot-tour) for quick overview:

<a href="https://triliumnext.github.io/Docs/Wiki/screenshot-tour"><img src="https://raw.githubusercontent.com/TriliumNext/Trilium/refs/heads/main/docs/app.png" alt="Trilium Screenshot" width="1000"></a>

## 🎁 Features

* Notes can be arranged into arbitrarily deep tree. Single note can be placed into multiple places in the tree (see [cloning](https://triliumnext.github.io/Docs/Wiki/cloning-notes))
* Rich WYSIWYG note editor including e.g. tables, images and [math](https://triliumnext.github.io/Docs/Wiki/text-notes) with markdown [autoformat](https://triliumnext.github.io/Docs/Wiki/text-notes#autoformat)
* Support for editing [notes with source code](https://triliumnext.github.io/Docs/Wiki/code-notes), including syntax highlighting
* Fast and easy [navigation between notes](https://triliumnext.github.io/Docs/Wiki/note-navigation), full text search and [note hoisting](https://triliumnext.github.io/Docs/Wiki/note-hoisting)
* Seamless [note versioning](https://triliumnext.github.io/Docs/Wiki/note-revisions)
* Note [attributes](https://triliumnext.github.io/Docs/Wiki/attributes) can be used for note organization, querying and advanced [scripting](https://triliumnext.github.io/Docs/Wiki/scripts)
* UI available in English, German, Spanish, French, Romanian, and Chinese (simplified and traditional)
* Direct [OpenID and TOTP integration](./docs/User%20Guide/User%20Guide/Installation%20%26%20Setup/Server%20Installation/Multi-Factor%20Authentication.md) for more secure login
* [Synchronization](https://triliumnext.github.io/Docs/Wiki/synchronization) with self-hosted sync server
  * there's a [3rd party service for hosting synchronisation server](https://trilium.cc/paid-hosting)
* [Sharing](https://triliumnext.github.io/Docs/Wiki/sharing) (publishing) notes to public internet
* Strong [note encryption](https://triliumnext.github.io/Docs/Wiki/protected-notes) with per-note granularity
* Sketching diagrams, based on [Excalidraw](https://excalidraw.com/) (note type "canvas")
* [Relation maps](https://triliumnext.github.io/Docs/Wiki/relation-map) and [link maps](https://triliumnext.github.io/Docs/Wiki/link-map) for visualizing notes and their relations
* Mind maps, based on [Mind Elixir](https://docs.mind-elixir.com/)
* [Geo maps](./docs/User%20Guide/User%20Guide/Note%20Types/Geo%20Map.md) with location pins and GPX tracks
* [Scripting](https://triliumnext.github.io/Docs/Wiki/scripts) - see [Advanced showcases](https://triliumnext.github.io/Docs/Wiki/advanced-showcases)
* [REST API](https://triliumnext.github.io/Docs/Wiki/etapi) for automation
* Scales well in both usability and performance upwards of 100 000 notes
* Touch optimized [mobile frontend](https://triliumnext.github.io/Docs/Wiki/mobile-frontend) for smartphones and tablets
* Built-in [dark theme](https://triliumnext.github.io/Docs/Wiki/themes), support for user themes
* [Evernote](https://triliumnext.github.io/Docs/Wiki/evernote-import) and [Markdown import & export](https://triliumnext.github.io/Docs/Wiki/markdown)
* [Web Clipper](https://triliumnext.github.io/Docs/Wiki/web-clipper) for easy saving of web content
* Customizable UI (sidebar buttons, user-defined widgets, ...)
* [Metrics](https://github.com/TriliumNext/Trilium/blob/main/docs/User%20Guide/User%20Guide/Advanced%20Usage/Metrics.md), along with a [Grafana Dashboard](https://github.com/TriliumNext/Trilium/blob/main/docs/User%20Guide/User%20Guide/Advanced%20Usage/Metrics/grafana-dashboard.json)

✨ Check out the following third-party resources/communities for more TriliumNext related goodies:

- [awesome-trilium](https://github.com/Nriver/awesome-trilium) for 3rd party themes, scripts, plugins and more.
- [TriliumRocks!](https://trilium.rocks/) for tutorials, guides, and much more.

## ⚠️ Why TriliumNext?

[The original Trilium project is in maintenance mode](https://github.com/zadam/trilium/issues/4620).

### Migrating from Trilium?

There are no special migration steps to migrate from a zadam/Trilium instance to a TriliumNext/Notes instance. Simply install TriliumNext/Notes as usual using your existing database.

Versions up to and including [v0.90.4](https://github.com/TriliumNext/Notes/releases/tag/v0.90.4) are compatible with the latest zadam/trilium version of [v0.63.7](https://github.com/zadam/trilium/releases/tag/v0.63.7). Any later versions of TriliumNext have their sync versions incremented.