# Input

Create a regex to make sure URLs have a valid port specified, so within a range from 0 to 65535.

# Answer

```
^(http(s)?:\/\/.+:)([1-9][0-9]{0,3}|[1-5][0-9]{4}|6[0-4][0-9]{3}|65[0-4][0-9]{2}|655[0-2][0-9]|6553[0-5]|0)$
```

# Validation

- `https://asd.com:65535` Match
- `https://asd.com:80` Match
- `https://asd.com:99999` No match
