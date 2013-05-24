Cheatsheet for Django QuerySets
===
Current Django Version: [1.5](https://docs.djangoproject.com/en/1.5/ref/models/querysets/)

Methods that return new [QuerySets](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#queryset-api)
---

**Can be chained:**

    Entry.objects.filter(**kwargs).exclude(**kwargs).order_by(**kwargs)

 * [filter](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#filter)
 * [exclude](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#exclude)
 * [annotate](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#annotate)
 * [order_by](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#order-by)
 * [reverse](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#reverse)
 * [distinct](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#distinct)
 * [values](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#values)
 * [values_list](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#values-list)
 * [dates](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#dates)
 * [none](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#none)
 * [all](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#all)
 * [select_related](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#select-related)
 * [prefetch_related](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#select-related)
 * [extra](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#extra)
 * [defer]((https://docs.djangoproject.com/en/1.5/ref/models/querysets/#defer)
 * [only](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#only)
 * [using](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#using)
 * [select_for_update](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#select-for-update)

Methods that do not return QuerySets
---

 * [get](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#get)
 * [create](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#create)
 * [get_or_create](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#get-or-create)
 * [bulk_create](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#bulk-create)
 * [count](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#count)
 * [in_bulk](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#in-bulk)
 * [iterator](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#iterator)
 * [latest](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#latest)
 * [aggregate](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#aggregate)
 * [exists](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#exists)
 * [update](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#update)
 * [delete](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#delete)

Field lookups
---

**Field lookups are how you specify the meat of an SQL WHERE clause. They’re specified as keyword arguments to the QuerySet methods *filter()*, *exclude()* and *get()*.**

    Example: Entry.objects.get(id__exact=14)

 * [exact](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#exact)
 * [iexact](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#iexact)
 * [contains](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#contains)
 * [icontains](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#icontains)
 * [in](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#in)
 * [gt](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#gt)
 * [gte](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#gte)
 * [lt](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#lt)
 * [lte](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#lte)
 * [startswith](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#startswith)
 * [istartswith](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#istartswith)
 * [endswith](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#endswith)
 * [iendswith](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#iendswith)
 * [range](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#range)
 * [year](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#year)
 * [month](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#month)
 * [day](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#day)
 * [week_day](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#week_day)
 * [isnull](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#isnull)
 * [search](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#search)
 * [regex](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#regex)
 * [iregex](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#iregex)

**Protip: Use *in* to avoid chaining filter() and exclude()**

    Entry.objects.filter(status__in=['Hung over', 'Sober', 'Drunk'])

Aggregation functions
---

 * [Avg](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#avg)
 * [Count](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#id6)
 * [Max](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#max)
 * [Min](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#min)
 * [Std1.5](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#std1.5)
 * [Sum](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#sum)
 * [Variance](https://docs.djangoproject.com/en/1.5/ref/models/querysets/#variance)
