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
