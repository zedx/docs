# Extending ZEDx

- [Introduction](#introduction)
- [Widget vs. Module](#widget-vs-module)

<a name="introduction"></a>
## Introduction

ZEDx is fast, lightweight, and easy to use. To ensure it stays that way, the [Core Team](https://github.com/zedx/zedx) thinks carefully about adding functionality to the core ZEDx code. Still, users often find the need to graft additional functionality onto ZEDx to meet their needs, that's why we have ensured that they can do what they want and we maked ZEDx highly extensible.

In order to achieve this extensibility, ZEDx has been built with rich APIs and extension points. With some programming knowledge, you can leverage these APIs to add just about any feature you want. This section of the documentation aims to teach you how ZEDx works, and how to use the APIs so that you can build your own Extensions.

<a name="widget-vs-module"></a>
## Widget vs. Module

Well, if you want to create something that doesn't need any database installation, routes, service providers but just a beautiful thing to display to the end user, so you probably want to create a `widget` for example : `Wysiwig`, `similar ads`, `share buttons`

A module has the ability to create its own database table, a custom uri etc. for example a `Blog`.

    You also can create many widgets inside your module.
