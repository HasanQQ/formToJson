# Form to JSON
Simple, jQuery based library for form to json conversion.

## Usage

```html
<form action="#" method="POST">
  <input type="text" name="abc" value="String_0" />
  <input type="text" name="def" value="String_1" />
  <input type="text" name="ghi" value="String_2" />
  <input type="text" name="test[]" value="String_3" />
  <input type="text" name="test[]" value="String_4" />
  <input type="text" name="foo['bar']['a']" value="String_5" />
  <input type="text" name="foo['bar']['b']" value="String_6" />
  <input type="text" name="foo['bar']['c'][]" value="String_7" />
  <input type="text" name="foo['bar']['c'][]" value="String_8" />
  <input type="text" name="foo[]" value="String_10" />
  <input type="submit" />
</form>

<script>
  $("form").submit(function() {
    console.log($(this).formToJson());
    return false;
  });
</script>
```

## Output
```json
{
    "abc": "String_0",
    "def": "String_1",
    "ghi": "String_2",
    "test": {
        "0": "String_3",
        "1": "String_4"
    },
    "foo": {
        "1": "String_10",
        "bar": {
            "a": "String_5",
            "b": "String_6",
            "c": {
                "0": "String_7",
                "1": "String_8"
            }
        }
    }
}
```
