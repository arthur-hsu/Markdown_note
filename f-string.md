
# python f-string
```python
a = 'world'
b = 'oxxo'
c = f'hello {a:<10s}, I am {b:>10s}'
print(c)   # hello world     , I am       oxxo
d = f'hello {a:-<10s}, I am {b:+^10s}'
print(d)   # hello world-----, I am +++oxxo+++
e = f'hello {a:-<10.3s}, I am {b:+^10.2s}'
print(e)   # hello wor-------, I am ++++ox++++
f = f'hello {a.upper()}, I am {b.title()}'
print(f)   # hello WORLD, I am Oxxo
```
