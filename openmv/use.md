# Openmv 使用入门

## 1. 色块查询

在openmv中，我们可以使用`img.find_blobs`来根据阈值查找色块

```py
import sensor, image, time

sensor.reset()
sensor.set_pixformat(sensor.RGB565)
sensor.set_framesize(sensor.QQVGA)
sensor.skip_frames(time = 2000)
sensor.set_auto_gain(False) # must be turned off for color tracking
sensor.set_auto_whitebal(False) # must be turned off for color tracking
clock = time.clock()

red_threshold = (30, 100, 15, 127, 15, 127)

while(True):
    img = sensor.snapshot()
    blobs = img.find_blobs([red_threshold], pixels_threshold=100, area_threshold=100, merge=True)

    largest_blob = None
    largest_blob_area = 0
    for b in blobs:
        if b.area() > largest_blob_area:
            largest_blob = b
            largest_blob_area = b.area()

    if largest_blob:
        img.draw_rectangle(largest_blob.rect())
        img.draw_cross(largest_blob.cx(), largest_blob.cy())
        left_corner = (largest_blob.x(), largest_blob.y())
        print("The w and h are",largest_blob.h(), largest_blob.w())
        print("左上角坐标:", left_corner)
```


