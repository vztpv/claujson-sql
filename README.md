# claujson-sql
with vztpv/scj3, claujson(https://github.com/vztpv/scj3)  and motivated from https://www.postgresql.org/docs/current/functions-json.html

# example
    // 변수 선언, 접근?, and 출력 
    x = '[{"a":"foo"},{"b":"bar"},{"c":"baz"}]'json;
    // json->integer -> json
    print(x -> 2); // {"c":"baz"} - object
    // json->text -> json
    print(x -> -3) // {"a":"foo"} - object
    y = '{"a": {"b":"foo"}}'json;
    // json->text -> json
    print(y -> 'a'); // {"b":"foo"} - object
    // json->>integer -> text
    print(x ->> 2); // {"c":"baz"} - as text
    // json->>text -> text
    print(y ->> 'a'); // {"b":"foo"} - as text
    // json#>text[] -> json
    z = '{"a": {"b": ["foo","bar"]}}'json;
    print(z #> '{a,b,1}'); // "bar" as claujson::Value?
    // json#>>text[] -> text
    print(z #>> '{a,b,1}'); // "bar" as text
    // load and save
    x = load('test.json', 1); // # of thread?
    save(x, 1); // # of thread?
    
