# 1.3. JSON, YAML 소개

## B. JSON(JavaScript Object Notation)
- 장점:- Lightweight data-interchange format
- 구조: A collection of name/value paris. An ordered list of values
```
{
    "format": {
        "type": "json",
        "members": {
            {"id": "0001", "name": "Bob", "age": 32},
            {"id": "0002", "name": "Alice", "age": 28}
        }
    }
}
```

## C. YAML(YAML Ain't markup language)
- 장점
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
