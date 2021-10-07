# Neos CMS Locomotive Scroll

A package to use Locomotive Scroll (https://locomotivemtl.github.io/locomotive-scroll/) in Neos.

## Installation

The NeosRulez.LocomotiveScroll package is listed on packagist (https://packagist.org/packages/neosrulez/locomotivescroll) - therefore you don't have to include the package in your "repositories" entry any more.

Just run:

```
composer require neosrulez/locomotivescroll
```

## Configuration

All settings from here: https://github.com/locomotivemtl/locomotive-scroll can be used:

```yaml
NeosRulez:
  LocomotiveScroll:
    settings:
      smooth: true
      reloadOnContextChange: true
      scrollFromAnywhere: true
```

## NodeType Mixin

Add the mixin to the superTypes of your content superType:

````yaml
'Acme.Site:Component.AbstractContent':
  superTypes:
    'Neos.Neos:Content': true
    'NeosRulez.LocomotiveScroll:Mixin.LocomotiveScroll': true
````

## Fusion component

All you have to do is wrap your AbstractContent with the Locomotive Wrapper:

```neosfusion
prototype(Acme.Site:Component.AbstractContent) {
    
    renderer = afx`
        <NeosRulez.LocomotiveScroll:Wrapper>
            {props.content}
        </NeosRulez.LocomotiveScroll:Wrapper>
    `
}
```

or use it like this:

```neosfusion
prototype(Acme.Site:Component.Foo) {
    
    renderer = afx`
        <NeosRulez.LocomotiveScroll:Wrapper isScrollable="true" dataScrollSpeed="1" direction="horizontal">
            <p>My awesome component</p>
        </NeosRulez.LocomotiveScroll:Wrapper>
    `
}
```

## Author

* E-Mail: mail@patriceckhart.com
* URL: http://www.patriceckhart.com
