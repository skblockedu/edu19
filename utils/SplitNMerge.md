# 대용량 파일 Split 하고 Merge 하기

## Split in linux and merge in windows

### Linux
```
split -b 800mega EDU.ova
ls
xaa xab xac xad
```

### Windows
```
copy /b xaa+xab+xac+xad EDU.ova
```
 
