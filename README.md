# simple-json-lib

# Возможности:  

* Чтение json из потока  

```C++
json::Document json::Load(std::istream& input);
```

* Печать json в поток с форматированием  

```C++
void Print(const json::Document& doc, std::ostream& output);
```

* Создание json, можно создавать документ напрямую работая с Node  

```C++
json::Dict item_node;
item_node.insert({"stop_name"s, std::string{edge.name}});
item_node.insert({"type"s, "Wait"s});
```

* Можно воспользоваться классом Builder, который реализует method chaining, что позволяет отловить ошибку в структуре json во время компиляции  

```C++
json::Print(json::Document{json::Builder{}.StartDict().Key("1").StartDict().EndDict().Key("2").Value(2).EndDict().Build()}, cout);
```

# Компилятор  
g++.exe (MinGW-W64 x86_64-ucrt-posix-seh, built by Brecht Sanders) 12.2.0