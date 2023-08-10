# be-in

Interpolate microdata with string constants to (three-way) bind with attributes / properties.  By three-way, I mean a kind of delicate dance involving host properties, server-rendered microdata combined with server-rendered attributes.



Example 1:

```html
<meta itemprop=protocol content=https>
<meta itemprop=domain content=docs.joshatz.com>
<meta itemprop=articleType content=cheatsheets>
<meta itemprop=language content=js>
<meta itemprop=topic content=classes>
<meta itemprop=section content=basic-improved---prototype-definition>
<a be-in='{
    "href": "{protocol}://{domain}/{articleType}/{language}/{language}-{classes}/#{section}"
}'
>Basic, Improved - Prototype Definition</a>
```

results in:

```html
<a href=https://docs.joshuatz.com/cheatsheets/js/js-classes/#basic-improved---prototype-definition>Basic, Improved - Prototype Definition</a>
```


Example 2:

```html
<a href=https://docs.joshuatz.com/cheatsheets/js/js-classes/#basic-improved---prototype-definition be-itemized='{
    "href": "{protocol}://{domain}/{articleType}/{language}/{language}-{classes}/#{section}"
}'
>Basic, Improved - Prototype Definition</a>
```

results in:

```html
<a be-out='{
    "href": "{protocol}://{domain}/{articleType}/{language}/{language}-{classes}/#{section}"
}'
>Basic, Improved - Prototype Definition</a>
<meta itemprop=protocol content=https>
<meta itemprop=domain content=docs.joshatz.com>
<meta itemprop=articleType content=cheatsheets>
<meta itemprop=language content=js>
<meta itemprop=topic content=classes>
<meta itemprop=section content=basic-improved---prototype-definition>
```


