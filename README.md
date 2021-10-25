nv-i18n-safe
=======

# Fork

nv-i18n-safe is a fork of the [neovisionaries internationalization library](https://github.com/TakahikoKawasaki/nv-i18n).
The original library uses country names which are unsuitable for display in user interfaces because they are
politically inflammatory, confusing, or excessively wordy. This fork is a drop-in replacement which tracks the origin,
but renames several countries to common names used by english-language Wikipedia. There are no other code changes.

| Old Name | New Name |
|:---------------------|:-------------------------------------------------------------|
| Taiwan, Province of China | Taiwan |
| Bolivia, Plurinational State of | Bolivia |
| Korea, Democratic People's Republic of | North Korea |
| Korea, Republic of | South Korea |
| Iran, Islamic Republic of | Iran |
| Moldova, Republic of | Moldova |
| Saint Martin (French part) | Saint Martin |
| Sint Maarten (Dutch part) | Sint Maarten |
| North Macedonia, Republic of | North Macedonia |
| Palestine, State of | Palestine |
| Russian Federation | Russia |
| Syrian Arab Republic | Syria |
| Tanzania, United Republic of | Tanzania |
| Holy See (Vatican City State) | Vatican City |
| Venezuela, Bolivarian Republic of | Venezuela |
| Kosovo, Republic of | Kosovo |

The fork is maintained at https://github.com/stickfigure/nv-i18n-safe

Overview
--------

Package to support internationalization, containing ISO 3166-1 country code enum,
ISO 639-1 language code enum, ISO 15924 script code enum, etc.

| Class                | Description                                                  |
|:---------------------|:-------------------------------------------------------------|
| `CountryCode`        | ISO 3166-1 country code.                                     |
| `LanguageCode`       | ISO 639-1 language code.                                     |
| `LanguageAlpha3Code` | ISO 639-2 language code.                                     |
| `LocaleCode`         | Available locales whose format match either 'xx' or 'xx-XX'. |
| `ScriptCode`         | ISO 15924 script code.                                       |
| `CurrencyCode`       | ISO 4217 currency code.                                      |


License
-------

  Apache License, Version 2.0


Maven
-----

```xml
<dependency>
    <groupId>com.voodoodyne</groupId>
    <artifactId>nv-i18n-safe</artifactId>
    <version>1.29</version>
</dependency>
```


Gradle
------

```gradle
dependencies {
    compile 'com.voodoodyne:nv-i18n-safe:1.29'
}
```


OSGi
----

    Bundle-SymbolicName: com.voodoodyne.i18n
    Export-Package: com.voodoodyne.i18n;version="1.29.0"


Source Code
-----------

  <code>https://github.com/stickfigure/nv-i18n-safe.git</code>


JavaDoc
-------

  <code>http://TakahikoKawasaki.github.io/nv-i18n/</code>


Example
-------

```java
// List all the country codes.
for (CountryCode code : CountryCode.values())
{
    System.out.format("[%s] %s\n", code, code.getName());
}

// List all the language codes.
for (LanguageCode code : LanguageCode.values())
{
    System.out.format("[%s] %s\n", code, code.getName());
}

// List all the locale codes.
for (LocaleCode code : LocaleCode.values())
{
    String language = code.getLanguage().getName();
    String country  = code.getCountry() != null
                    ? code.getCountry().getName() : null;

    System.out.format("[%s] %s, %s\n", code, language, country);
}

// List all the script codes.
for (ScriptCode code : ScriptCode.values())
{
    System.out.format("[%s] %03d %s\n", code, code.getNumeric(), code.getName());
}

// List all the currency codes.
for (CurrencyCode code : CurrencyCode.values())
{
    System.out.format("[%s] %03d %s\n", code, code.getNumeric(), code.getName());
}
```


See Also
--------

* [nv-i18n @ GitHub](https://github.com/TakahikoKawasaki/nv-i18n)
* Country Code [ISO 3166-1](http://en.wikipedia.org/wiki/ISO_3166-1)
* Country Code [ISO 3166-1 alpha-2](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
* Country Code [ISO 3166-1 alpha-3](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-3)
* Country Code [ISO 3166-1 numeric](http://en.wikipedia.org/wiki/ISO_3166-1_numeric)
* Language Code [ISO 639-1](http://en.wikipedia.org/wiki/ISO_639-1)
* Language Alpha3 Code [ISO 639-2](http://en.wikipedia.org/wiki/ISO_639-2)
* Script Code [ISO 15924](http://en.wikipedia.org/wiki/ISO_15924)
* Currency Code [ISO 4217](http://en.wikipedia.org/wiki/ISO_4217)


TODO
----

* To add missing entries to CountryCode.
* To add international telephone dial number.


Note
----

This nv-i18n supersedes https://github.com/TakahikoKawasaki/CountryCode


Author
------

Takahiko Kawasaki, [Authlete, Inc.](https://www.authlete.com/)
