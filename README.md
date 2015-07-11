README
======

## Installation

You can install this library using composer

``` bash
$ php composer.phar require proyecto404/coding-standard "dev-master" --dev
```

or add the package to your `composer.json` file directly.

Composer will install the library to your project's `vendor/proyecto404` directory.

## Phing configuration

Add this to your phing's `build.xml` file:

``` xml
    <target name="check:cs" description="Checks coding standard." depends="prepare">
        <echo msg="Checking coding standard ..." />
        <phpcodesniffer standard="vendor/proyecto404/coding-standard/Proyecto404"
                        showSniffs="true"
                        showWarnings="true">
            <fileset refid="sourcecode" />
            <formatter type="checkstyle" outfile="${dir.reports}/checkstyle.xml" />
        </phpcodesniffer>
    </target>
```

You have to configure your reports directory:

``` xml
    <property name="dir.reports" value="${dir.build}/logs" />
```

## PHP Storm configuration

In `Settings/Languages & Frameworks/PHP/CodeSniffer` configure directory to point to `[PROJECT_DIR]/bin/phpcs.bat`

In `Settings/Editor/PHP/Inspections` enable `PHP/PHP Code Sniffer validation`

In `Settings/Editor/PHP/Inspections/PHP/Code Sniffer` select custom coding standard and point directory to `[PROJECT_DIR]/vendor/proyecto404/coding-standard/Proyecto404`


License
-------

This code is under the MIT license. See the complete license in the `LICENSE` file.
