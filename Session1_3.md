# 1.3. JSON, YAML 소개

## JSON(JavaScript Object Notation)
- 장점: Lightweight data-interchange format
- 구조: A collection of name/value paris. An ordered list of values
```
{
    "format": {
        "type": "json",
        "members": [
            {"id": "0001", "name": "Bob", "age": 32},
            {"id": "0002", "name": "Alice", "age": 28}
        ]
    }
}
```

## YAML(YAML Ain't markup language)
- 특징: a human-readable data serialization language
- 구조: Indentation-based markup language
```
___
format:
    type: yaml
    members:
    - id: '0001'
      name: Bob
      age: 32
    - id: '0002'
      name: Alice
      age: 28
```
- 실습: https://www.json2yaml.com

["2.1. cryto. & configuration 파일 생성" >>](https://github.com/skblockedu/edu19/blob/master/Session2_1.md)
