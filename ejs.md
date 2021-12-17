# EJS

## Embed partials

```ejs
<%- include("relative/path/to/file") %> 
```

## Passing DATA to views and partials

### Echo A Single Variable

``` ejs
<%= variable %>
```

### Embed JS Logic

```ejs
<% js code here %>
```

### Passing DATA to a Partial in EJS

```ejs
<%- include("relative/path/to/file", {key: value}) %> 
```

