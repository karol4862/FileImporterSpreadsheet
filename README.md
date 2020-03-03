# CsvImport

## CSV File Content

  Title | Amount
  --- | --- 
  Srele | 12
  Morele | 9

## Example in use

```
  <CsvImport v-model="val"  :labels="['name', 'surname']" :separators="[',']" />
```

## Output
```
  data() {
    return {
      val:[
        {
          name: "Srele",
          surname: "12"
        }
        ...
      ],
    };
  }
```

## Props

Name | Description | Type
--- | --- | ---
labels | Assign content to variable | Array
separators | What separators the file uses | Array
parse | If want to parse from JSON | Boolean
