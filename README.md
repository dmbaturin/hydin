# HYDIN

HYDIN (HYperlinked Document Interchange Network) is a hypothetical alternative to the World Wide Web.

Like the World Wide Web, it offers a transport protocol and a markup language.

## Motivation

* Accessible, discoverable sites — through machine-readable resource maps and document info queries.
* Client control over the page looks and rendering, a new plugin system that builds upon the ideas of user scripts and old browser addons.

## Goals

* Machine-readable and discoverable resouce maps (inspired by Gopher maps, but with a modern approach).
* Extensible markup language.
* Easy to bootstrap on top of the WWW.

## Structure

* HDTP — HYDIN Document Transfer Protocol.
* Markup language — to be determined.
* Client platform — to be determined.

## Ideas

The HYDIN protocol is like:

* HTTP: Similar set of methods and header syntax.
* Gopher: it supports machine-readable resource maps.
* The old shared hosting with tildes but better: protocol address (for connecting) and HYDIN location are _separate_ concepts.

The HYDIN markup language is like:

* HTML: similar syntax with tags.
* XHTML: extensible with custom elements.

HYDIN browsers can delegate handling of custom elements to plugins, a bit like web components,
but the user can decide what plugin to install and use by default.

## Contributing

So far the project in a discussion stage, so any discussion is welcome.
