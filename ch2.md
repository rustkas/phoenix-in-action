```
add_ingredient = fn(plate, ingredient) -> Enum.concat(plate, [ingredient]) end
```

```
for each order received:
 plate = []
 plate = add_ingredient.(plate, :bread)
 plate = add_ingredient.(plate, :mustard)
 plate = add_ingredient.(plate, :turkey)
 plate = add_ingredient.(plate, :cheese)
 plate = add_ingredient.(plate, :lettuce)
 plate = add_ingredient.(plate, :tomato)
 plate = add_ingredient.(plate, :bread)
end
```
```
Enum.filter([1,3,5,7,9], fn(x) -> x < 6 end)
```

```
8 / 4
8.0 / 5
div(8, 5)
round(1.6)
trunc(1.6)
```

```
1 == 5
is_integer(5)
```

```
is_binary("Phoenix in Action")
"Phoenix" <> " in " <> "Action"
```

```
haiku = """
Build web apps for fun, profit
Phoenix in Action
Learning the things you need to know
"""
```

```
subject = "Phoenix"
"#{subject} in Action"
```
```
'Geo'
i('Geo')
[71, 101, 111]
{71, 101, 111}
```
```
list = [1, 2]
[:number, "for example", list]
```

```
[1,2] ++ ["three", :four]
[1,2,3] -- [1,3]
[head | tail] = ["Phoenix", "in", "Action"]
head
tail
hd(head)
hd(tail)
[1 | [2 | []]]

trees = ["Oak", "Pine"]
more_trees = ["Maple" | trees]
```

```
tuple= {:ok, 5, ["Phoenix", "in", "Action"]}
elem(tuple, 1)
```

```
map = %{:status => 200, "content" => "Hello world!"}
Map.fetch(map, "content")
%{a: 1, b: 2, c: 3}
%{a: 1, "hello": :world}
%{"hello": :world, a: 1 }
map = %{"hello": :world, a: 1 }
map[:a]
map[:hello]
map[:world]
map.a
map.hello

```

```
defmodule Sandwich do
def accept?(sandwich) do
edible_meats = %{turkey: true, ham: false, chicken: true, olive_loaf: false}
[:bread, mystery_meat, :bread] = sandwich

case Map.fetch(edible_meats, mystery_meat) do
{:ok, edible} -> 
if edible, do: "Yes, please!", else: "No, thanks."
:error ->
"I don't know what this is!"
end 
end
end
```

```
Sandwich.accept?([:bread, :turkey, :bread])
Sandwich.accept?([:bread, :olive_loaf, :bread])
Sandwich.accept?([:bread, :head_cheese, :bread])
```
