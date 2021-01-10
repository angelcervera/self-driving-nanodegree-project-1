# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]



#### Approach one.
After split and collect all points in the right and left line separator, I create a line using with max and min values.
```python
(left, right) = left_or_right(lines)
x_left,y_left = extract_coords(left)
x_right,y_right = extract_coords(right)


cv2.line(img, (min(x_left), max(y_left)), (max(x_left), min(y_left)), (255, 0, 0), 10)
cv2.line(img, (max(x_right), max(y_right)), (min(x_right), min(y_right)), (255, 0, 0), 10)
```

This way to extrapolate the line is not accurate enough because:
- It is limited to the location of the max and min coordinate found.
- It is not ignoring false located lines.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
