Sample 1:
Optimization
```
convert -strip -interlace Plane -gaussian-blur 0.05 -quality 85% source.jpg result.jpg
```
Sample 2:
Optimization
```
convert -strip -interlace Plane -quality 85% source.jpg result.jpg
```

Sample 3:
Resize
```
mogrify -resize 800x image.jpg
```

Sample 4:
Resize with compress
```
mogrify -quality "85%" -resize 800x image.jpg
```
Sample 5:
Resize with crop and gravity center
```
convert -strip -interlace Plane -quality 85% -resize 150x150^ -gravity center -extent 150x150 main.jpg main_out.jpg
```

Sample 6:
Resize with fill
```
convert main.jpg -resize 150x150\> -size 150x150 xc:white +swap -gravity center -composite main_out.jpg
```
