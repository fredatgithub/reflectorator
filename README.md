# Reflectify - Reflection extensions without causing dependency pains

[![](https://img.shields.io/github/actions/workflow/status/dennisdoomen/reflectify/build.yml?branch=main)](https://github.com/dennisdoomen/reflectify/actions?query=branch%3amain)
[![Coveralls branch](https://img.shields.io/coverallsCoverage/github/dennisdoomen/reflectify?branch=main)](https://coveralls.io/github/dennisdoomen/reflectify?branch=main)
[![](https://img.shields.io/github/release/DennisDoomen/Reflectify.svg?label=latest%20release&color=007edf)](https://github.com/dennisdoomen/reflectify/releases/latest)
[![](https://img.shields.io/nuget/dt/Reflectify.svg?label=downloads&color=007edf&logo=nuget)](https://www.nuget.org/packages/Reflectify)
[![](https://img.shields.io/librariesio/dependents/nuget/Reflectify.svg?label=dependent%20libraries)](https://libraries.io/nuget/Reflectify)
[![GitHub Repo stars](https://img.shields.io/github/stars/dennisdoomen/reflectify)](https://github.com/dennisdoomen/reflectify/stargazers)
[![GitHub contributors](https://img.shields.io/github/contributors/dennisdoomen/reflectify)](https://github.com/dennisdoomen/reflectify/graphs/contributors)
[![GitHub last commit](https://img.shields.io/github/last-commit/dennisdoomen/reflectify)](https://github.com/dennisdoomen/reflectify)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/m/dennisdoomen/reflectify)](https://github.com/dennisdoomen/reflectify/graphs/commit-activity)
[![open issues](https://img.shields.io/github/issues/dennisdoomen/reflectify)](https://github.com/dennisdoomen/reflectify/issues)
![](https://img.shields.io/badge/release%20strategy-githubflow-orange.svg)

## What's this about?

Reflectify offers a bunch of extension methods to provide information such as the properties or fields a type exposes and metadata about those members. It supports all major .NET versions and even understands explicltly implemented properties or properties coming from default interface implementations, a C# 8 feature.

## What's so special about that?

Nothing really, but it offers that functionality through a content-only NuGet package. In other words, you can use this package in your own packages, without the need to tie yourself to the Reflectify package. Oh, and it's used by [an open-source project](https://fluentassertions.com/) with over 400 million downloads.

## How do I use it?

Simple, to get the properties of a type, add the `Reflectify` NuGet package and use

```csharp
using Reflectify;

var properties = typeof(SuperClass).GetProperties(
    MemberKind.Public | MemberKind.ExplicitlyImplemented | MemberKind.DefaultInterfaceProperties);
```

You can take any of the options `Public`, `Internal`, `ExplictlyImplemented` and `DefaultInterfaceProperties`.

If you need the fields, use `GetFields` (which obviously cannot be explicitly implemented, nor be part of interfaces), and if you need the members, use `GetMembers`.

To get more metadata from a `PropertyInfo`, you can use extensions methods like:

* `IsExplictlyImplemented`
* `IsIndexer`

More will follow in time.

> [!TIP]
> If you like this package, consider sponsoring me through [Github Sponsors](https://github.com/sponsors/dennisdoomen)
