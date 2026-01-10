### Common Patterns

- Anchors: `^` start, `$` end
    
- Any character: `.`
    
- Repetition: `*` 0 or more, `+` 1 or more, `?` 0 or 1
    
- Character sets: `[abc]`, `[0-9]`, `[^0-9]`
    
- Groups: `(abc)`, `{n}` exactly n, `{n,m}` n to m
    
- Escape special chars: `\?`, `\$`
    

### Examples

```bash
[[ "hello world" =~ ^h.+d$ ]]  # starts with h, ends with d
[[ "123" =~ ^[0-9]{3}$ ]]      # exactly 3 digits
[[ "Bangladesh" =~ ^[A-Z][a-z]+$ ]]  # capital letter then lowercase
[[ "Is it ok?" =~ \?$ ]]       # ends with ?
```
