<img src="./Vector by Datadog.svg" width="200px"/><img src="./clickhouse.png" width="200px"/>

## Vector + Clickhouse + lighthouse Ansible-Playbook

Плейбук для установки и базовой настройки связки Vector + Clickhouse + lighthouse на CentOS 7


## Переменные
В переменных можно указать устанавливаемую версию Vector и Clickhouse:
```yaml
clickhouse_version: "22.3.3.44"
vector_version: "0.31.0"
```
Для Vector обязательно надо указать архетиктуру:
```yaml
vector_arch: "x86_64"
```
А так же конфиг для Vector:
```yaml
vector_config: 
 sources:
  in:
    type: "stdin"

 sinks:
   out:
    inputs:
      - "in"
    type: "console"
    encoding:
      codec: "text"
```
Папку где должен находиться конфиг
```yaml
vector_config_folder: /etc/vector
```

папка для данных lighthouse
```yaml
lighthouse_conf_folder: /var/lighthouse
```

## ТЭГИ
В плейбуке присутствуют теги позволяющие установить выборочный продукт

```yaml
vector - установить только vektor
clickhouse - установить только Clickhouse
lighthouse - установить только lighthouse
```

