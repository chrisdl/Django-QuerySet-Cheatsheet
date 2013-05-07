Cheatsheet for Django QuerySets
===
Current Django Version: [1.5](https://docs.djangoproject.com/en/1.5/ref/models/querysets/)

Methods that return new QuerySets
---

**Can be chained:**

    Entry.objects.filter(**kwargs).exclude(**kwargs).order_by(**kwargs)

 * filter
 * exclude
 * annotate
 * order_by
 * reverse
 * distinct
 * values
 * values_list
 * dates
 * none
 * all
 * select_related
 * prefetch_related
 * extra
 * defer
 * only
 * using
 * select_for_update

Methods that do not return QuerySets
---

 * get
 * create
 * get_or_create
 * bulk_create
 * count
 * in_bulk
 * iterator
 * latest
 * aggregate
 * exists
 * update
 * delete

Field lookups
---

**Field lookups are how you specify the meat of an SQL WHERE clause. They’re specified as keyword arguments to the QuerySet methods *filter()*, *exclude()* and *get()*.**

    Example: Entry.objects.get(id__exact=14)

 * exact
 * iexact
 * contains
 * icontains
 * in
 * gt
 * gte
 * lt
 * lte
 * startswith
 * istartswith
 * endswith
 * iendswith
 * range
 * year
 * month
 * day
 * week_day
 * isnull
 * search
 * regex
 * iregex

**Protip: Use *in* to avoid chaining filter() and exclude()**

    Entry.objects.filter(status__in=['Hung over', 'Sober', 'Drunk'])

Aggregation functions
---

 * Avg
 * Count
 * Max
 * Min
 * StdDev
 * Sum
 * Variance
