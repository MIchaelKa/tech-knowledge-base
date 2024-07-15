
Protocol Buffers

# Внешние ссылки

**Official**
https://protobuf.dev/

**GH**
https://github.com/protocolbuffers/protobuf

wiki
https://ru.wikipedia.org/wiki/Protocol_Buffers

# Сводка

Google

Для десериализации данных необходим отдельный .proto-файл, в котором определяется формат сообщения.

```proto
message Person {
  string name = 1;
  int32 id = 2;
  bool has_ponycopter = 3;
}
```

Позволяет явно задавать типы в определении.

бинарные данные vs. текстовые данные
