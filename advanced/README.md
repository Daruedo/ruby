# Avançado

## Regex:

- Formatos:

```
/…/
%r{…}
Regexp.new(‘…’)
```

- Retorna o offset, ou seja, a distância entre o começo da string até o local onde ocorre o casamento de padrão especificado na expressão:
```
/by/ =~ 'ruby'
```

- Retorna um objeto do tipo MatchData, contendo todos os resultados do casamento de padrão:
```
phrase = "Hellow, how are you?"
 
match_data = /how/.match(phrase)
```

```
match_data.pre_match
```

```
match_data.post_match
```

- Os símbolos (, ), [, ], {, }, ., ?, +, *,  são metacharacters. Eles possuem um significado quando utilizados em expressões regulares. Caso o padrão que você procura seja um metacharacter, utilize o símbolo de escape \ para realizar a busca:

```
/\?/.match('Tudo bem?')
 
/bem\!\!\!/.match('Muito bem!!!')
```

- Uma character class é delimitada por colchetes [, ]

```
/[t]exto/.match('texto começando com t')
```

- Você pode especificar um range com o símbolo –

```
/[1-5]/.match('123')
```

- Note que o casamento também ocorre em uma string que começa com o número 2

```
/[1-5]/.match('223')
```

- O range pode ser utilizado para letras

```
/[a-z]/.match('Oi')
```

- Existem alguns metacharacters que se comportam como character classes. Por exemplo, o metacharacter \d verifica o padrão [0-9]:

```
/A\d/.match('A4')
```

- É possível definir a repetição de um mesmo padrão, evitando escrever a mesma coisa diversas vezes. Por exemplo, verifique o casamento de padrão em uma etiqueta que começa com uma letra e 3 números:

```
"A343".match(/[A-Z]\d{3}/)
```

- Verifique se uma letra foi escrita mantendo o padrão de repetição entre três ou mais vezes

```
"BBB AAAA".match(/A{3,}/)
```

## Math

- Raiz quadrada

```
Math.sqrt(64)
```

- Logaritmo de 16 na base 2

```
Math.log2(16)
```

- Cosseno para o ângulo de 30º

```
radian = 30 * (Math::PI / 180)
Math.cos(radian)
```

- Constante E

```
Math::E
```

- Constante PI

```
Math::PI
```

## Time

- Horário atual

```
time = Time.now
puts time
```

- Ano

```
puts time.year
```

- Mês

```
puts time.month
```

- Dia

```
puts time.day
```

- Formatação

```
time.strftime('%d/%m/%y')
```

- Verificar se o dia da semana é sábado

```
puts time.saturday?
```

- Comparar duas datas

```
time.year == time2.year
```

## Method Missing

## Self

## Private and Protected

Private é um método interno de uma classe,  Apenas os métodos públicos dessa classe ou de classes descendentes podem chamá-lo.

Protected pode ter como receptor qualquer instância de sua classe. Ao contrário do private onde o self é o único receptor de um método private.