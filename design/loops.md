Loops
---

Turn all types of loops into do...while loops

---
##For

```
for <init>;<term>;<action> do
  <loop>
done
<deinit>
```

to

```
<init>
do
  <loop>
  <action>
while <term>
```

to

```
0 <init>
1 <loop>
2 <action>
3 if <term> goto 1
```

---
##For-each

```
for-each <var> in <grouping> do
  <loop>
done
```

to

```
pos=0
len=<grouping>.len
do
  <var>=<grouping>[pos]
  <loop>
while not pos++ == len
```

to

```
0 pos=0
1 len=<grouping>.len
2 <var>=<grouping>[pos]
3 <loop>
4 if not pos++ == len goto 2
```

---
##While

```
while <condition>
  <loop>
done
```

to (okay convert this one right to final pseudo-bytecode)

```
0 if <condition> goto 3
1 <loop>
2 goto 0
```

---
##Do-While

```
do
  <loop>
while <condition>
```

to

```
0 <loop>
1 if <condition> goto 0
```
