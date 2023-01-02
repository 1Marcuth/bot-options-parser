# Using

```js
import CommandOptionsParser from "bot-command-options-parser/dist"

const commandOptions = [
    {
        name: "person-name",
        type: "string",
        descritpion: "Name of the person",
        required: true
    },
    {
        name: "person-age",
        type: "integer",
        descritpion: "Age of the person",
        required: true
    },
    {
        name: "person-like-minecraft",
        type: "boolean",
        descritpion: "Does the person like to play minecraft?",
        required: true
    }
]
const commandOptionsPassed = [ "Marcuth", "16.7", "true" ]

const optionsParser = new CommandOptionsParser(commandOptions)

const validateResult = optionsParser.validateOptions(commandOptionsPassed)

console.log(validateResult)
```

***Output***
```js
[
  {
    name: 'person-name',
    type: 'string',
    values: { raw: 'Marcuth', parsed: 'marcuth' },
    isValid: { type: true, value: true }
  },
  {
    name: 'person-age',
    type: 'integer',
    values: { raw: '16.7', parsed: null },
    isValid: { type: false, value: false }
  },
  {
    name: 'person-like-minecraft',
    type: 'boolean',
    values: { raw: 'true', parsed: true },
    isValid: { type: true, value: true }
  }
]
```