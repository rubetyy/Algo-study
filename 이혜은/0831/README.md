# README

[toc]

## collection.counterπ¨βπ§βπ¦

### collection.counter

> νΈλ¦¬νκ³  λΉ λ₯΄κ² κ°μλ₯Ό μΈλλ‘ μ§μνλ κ³μκΈ° λκ΅¬κ° μ κ³΅λ©λλ€.

```
# Tally occurrences of words in a list
cnt = Counter()
for word in ['red', 'blue', 'red', 'green', 'blue', 'blue']:
     cnt[word] += 1
cnt
Counter({'blue': 3, 'red': 2, 'green': 1})

# Find the ten most common words in Hamlet
import re
words = re.findall(r'\w+', open('hamlet.txt').read().lower())
Counter(words).most_common(10)
[('the', 1143), ('and', 966), ('to', 762), ('of', 669), ('i', 631),
 ('you', 554),  ('a', 546), ('my', 514), ('hamlet', 471), ('in', 451)
```



### elements()

> κ°μλ§νΌ λ°λ³΅λλ μμμ λν μ΄ν°λ μ΄ν°λ₯Ό λ°νν©λλ€. μμλ μ²μ λ°κ²¬λλ μμλλ‘ λ°νλ©λλ€. μμμ κ°μκ° 1λ³΄λ€ μμΌλ©΄ `elements()`λ μ΄λ₯Ό λ¬΄μν©λλ€

```
c = Counter(a=4, b=2, c=0, d=-2)
sorted(c.elements())
['a', 'a', 'a', 'a', 'b', 'b']
```



### most_commone(n)

> *n* κ°μ κ°μ₯ νν μμμ κ·Έ κ°μλ₯Ό κ°μ₯ νν κ²λΆν° κ°μ₯ μ μ κ² μμΌλ‘ λμ΄ν λ¦¬μ€νΈλ₯Ό λ°νν©λλ€. *n*μ΄ μλ΅λκ±°λ `None`μ΄λ©΄, `most_common()`μ κ³μκΈ°μ *λͺ¨λ * μμλ₯Ό λ°νν©λλ€. κ°μκ° κ°μ μμλ μ²μ λ°κ²¬λ μμλ₯Ό μ μ§ν©λλ€

```
Counter('abracadabra').most_common(3)
[('a', 5), ('b', 2), ('r', 2)]
```



### subtract()

> *μ΄ν°λ¬λΈ*μ΄λ λ€λ₯Έ *λ§€ν* (λλ κ³μκΈ°)μΌλ‘λΆν° μ¨ μμλ€μ λΊλλ€. `dict.update()`μ λΉμ·νμ§λ§ κ΅μ²΄νλ λμ  κ°μλ₯Ό λΊλλ€. μλ ₯κ³Ό μΆλ ₯ λͺ¨λ 0μ΄λ μ

```
c = Counter(a=4, b=2, c=0, d=-2)
d = Counter(a=1, b=2, c=3, d=4)
c.subtract(d)
c
Counter({'a': 3, 'b': 0, 'c': -3, 'd': -6})
```



### update()

> μμλ *μ΄ν°λ¬λΈ*μμ μΈκ±°λ λ€λ₯Έ *λ§€ν*(λλ κ³μκΈ°)μμ λν΄μ§λλ€. `dict.update()`μ λΉμ·νμ§λ§, κ΅μ²΄νλ λμ  λν©λλ€. λν, *μ΄ν°λ¬λΈ*μ `(key, value)` μμ μνμ€κ° μλ, μμμ μνμ€μΌ κ²μΌλ‘ κΈ°λν©λλ€.



### λ§μ && λΊμ

> λνκΈ°μ λΉΌκΈ°λ ν΄λΉ μμμ κ°μλ₯Ό λ νκ±°λ λΉΌμ κ³μκΈ°λ₯Ό κ²°ν©. κ° μ°μ°μ λΆνΈ μλ κ°μλ₯Ό μλ ₯μΌλ‘ λ°μ μ μμ§λ§, μΆλ ₯μ κ°μκ° 0 μ΄νλ©΄ κ²°κ³Όμμ μ μΈ

```
c = Counter(a=3, b=1)
d = Counter(a=1, b=2)

c + d                       # add two counters together:  c[x] + d[x]
Counter({'a': 4, 'b': 3})
c - d                       # subtract (keeping only positive counts)
Counter({'a': 2})
```



### κ΅μ§ν© && ν©μ§ν©

> κ΅μ§ν©(intersection)κ³Ό ν©μ§ν©(union)μ ν΄λΉ κ°μμ μ΅μκ°κ³Ό μ΅λκ°μ λ°νν©λλ€. κ° μ°μ°μ λΆνΈ μλ κ°μλ₯Ό μλ ₯μΌλ‘ λ°μ μ μμ§λ§, μΆλ ₯μ κ°μκ° 0 μ΄νλ©΄ κ²°κ³Ό

```
c = Counter(a=3, b=1)
d = Counter(a=1, b=2)

c & d                       # intersection:  min(c[x], d[x]) 
Counter({'a': 1, 'b': 1})
c | d                       # union:  max(c[x], d[x])
Counter({'a': 3, 'b': 2})
```



###### μ°Έμ‘°

- [`python κ³΅μ λ¬Έμ`](https://docs.python.org/ko/3/library/collections.html )  



## itertools.permutations && itertools.combinationsβ­

### itertools.combinations

```
itertools.combinations('ABCD', 2) --> AB AC AD BC BD CD
itertools.combinations(range(4), 3) --> 012 013 023 123
```



### itertools.permutations

```
def combinations(iterable, r):
    pool = tuple(iterable)
    n = len(pool)
    for indices in permutations(range(n), r):
        if sorted(indices) == list(indices):
            yield tuple(pool[i] for i in indices)
```





###### μ°Έμ‘°

- [`python κ³΅μ λ¬Έμ`](https://docs.python.org/ko/3/library/itertools.html )  