# CsvImport

## CSV File
  Content:
  Srele | 12
  --- | --- 
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

Name | Description 
--- | --- 
labels | Name content to variable
--- | --- 
separators | What separators the file uses
