# Cheatsheet for Django QuerySets
Current Django Version: [1.7](https://docs.djangoproject.com/en/1.7/ref/models/querysets/)

Methods that return new [QuerySets](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#methods-that-return-new-querysets)

**Can be chained:**

````python
Entry.objects.filter(**kwargs).exclude(**kwargs).order_by(**kwargs)
````

 * [filter](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#filter)
 * [exclude](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#exclude)
 * [annotate](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#annotate)
 * [order_by](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#order-by)
 * [reverse](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#reverse)
 * [distinct](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#distinct)
 * [values](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#values)
 * [values_list](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#values-list)
 * [dates](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#dates)
 * [datetimes](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#datetimes)
 * [none](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#none)
 * [all](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#all)
 * [select_related](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#select-related)
 * [prefetch_related](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#prefetch-related)
 * [extra](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#extra)
 * [defer](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#defer)
 * [only](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#only)
 * [using](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#using)
 * [select_for_update](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#select-for-update)
 * [raw (1.7)](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#raw)

## Methods that do not return QuerySets

 * [get](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#get)
 * [create](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#create)
 * [get_or_create](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#get-or-create)
 * [update_or_create (1.7)](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#update-or-create)
 * [bulk_create](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#bulk-create)
 * [count](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#count)
 * [in_bulk](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#in-bulk)
 * [iterator](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#iterator)
 * [latest](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#latest)
 * [earliest](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#earliest)
 * [first](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#first)
 * [last](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#last)
 * [aggregate](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#aggregate)
 * [exists](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#exists)
 * [update](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#update)
 * [delete](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#delete)
 * [as_manager (1.7)](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#as-manager)

## Field lookups

**Field lookups are how you specify the meat of an SQL WHERE clause. They’re specified as keyword arguments to the QuerySet methods *filter()*, *exclude()* and *get()*.**

````python
Example: Entry.objects.get(id__exact=14)  # note double underscore.
````

 * [exact](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#exact)
 * [iexact](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#iexact)
 * [contains](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#contains)
 * [icontains](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#icontains)
 * [in](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#in)
 * [gt](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#gt)
 * [gte](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#gte)
 * [lt](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#lt)
 * [lte](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#lte)
 * [startswith](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#startswith)
 * [istartswith](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#istartswith)
 * [endswith](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#endswith)
 * [iendswith](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#iendswith)
 * [range](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#range)
 * [year](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#year)
 * [month](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#month)
 * [day](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#day)
 * [week_day](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#week_day)
 * [hour](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#hour)
 * [minute](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#minute)
 * [second](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#second)
 * [isnull](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#isnull)
 * [search](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#search)
 * [regex](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#regex)
 * [iregex](https://docs.djangoproject.com/en/1.7/ref/models/querysets/#iregex)

**Protip: Use *in* to avoid chaining filter() and exclude()**

````python
Entry.objects.filter(status__in=['Hung over', 'Sober', 'Drunk'])
````

## Aggregation functions

 * [Avg](https://docs.djangoproject.com/en/1.6/ref/models/querysets/#avg)
 * [Count](https://docs.djangoproject.com/en/1.6/ref/models/querysets/#id6)
 * [Max](https://docs.djangoproject.com/en/1.6/ref/models/querysets/#max)
 * [Min](https://docs.djangoproject.com/en/1.6/ref/models/querysets/#min)
 * [StdDev](https://docs.djangoproject.com/en/1.6/ref/models/querysets/#stddev)
 * [Sum](https://docs.djangoproject.com/en/1.6/ref/models/querysets/#sum)
 * [Variance](https://docs.djangoproject.com/en/1.6/ref/models/querysets/#variance)

- - -

<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/deed.en_US"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">Django-QuerySet-Cheatsheet</span> by <span xmlns:cc="http://creativecommons.org/ns#" property="cc:attributionName">@chrisdl and @briandant</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/deed.en_US">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>.<br />

The Django web framework referenced in the Django-QuerySet-Cheatsheet is ​© 2005-2014 Django Software Foundation.
Django is a registered trademark of the Django Software Foundation.
