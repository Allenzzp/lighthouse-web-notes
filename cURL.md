# cURL Commands

##  store output in a file

```curl
curl url > file_name
```

## save result of the curl command to a file
``` cm
-o: curl -o file_name.html url  saved in the filename provided
-O: curl -O url  taken filename in URL and use as name for a new file
```

## fetch multiple files
```
curl -O url1 -O url2
```

## follow HTTP Location headers (redirect)
```
curl -L url
```

##  continue/resume a Previous Download
```
curl -C - -O url
```

## limit the rate of data transfer (rate/second)
```
curl --limit-rate 1000B -O url
```

## download a file only if it is modified before/after the given time
```
after:	curl -z yy-Mmm-dd url	download only it's modified after the given date
before:	curl -z -yy-Mmm-dd url	download only it's modified before the given date
```

## pass HTTP authentication in cURL	(Username & Password)
```
curl -u username:password url
```

## get response header & content
```
curl -i url
```

## specify a custom request instead of GET when communicating with HTTP server
```
curl -X POST "http://localhost:8080/urls/9sm5xK/delete"
```

## send form data in the way a browser does

```
curl -X POST -d "longURL=baidu.com" "http://localhost:8080/urls/9sm5xK/update"
```

## post to a route with cookie and form data

```
curl -X POST -d "longURL=http://www.tcb.com" localhost:8080/urls --cookie "userId=000000"
```

