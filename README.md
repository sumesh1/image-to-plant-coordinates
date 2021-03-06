# Image to Plant Coordinates

Generates coordinates to grow plants in the shape of an image using _diffused pixel ordered dithering_

Orders plant coordinates for an optimized path using a _nearest neighbor algorithm_

## Dependencies

`sudo apt-get install imagemagick python-numpy python-matplotlib  python-scipy`

__ImageMagick__ is used for image processing

__NumPy__ and __matplotlib__ are used for simulations

__SciPy__ is used for path optimization

## Usage

##### Convert `farmbot.png` to plant coordinates:

`bash I2P.sh farmbot.png`

See [options](#options) for descriptions of parameters

## Input

![farmbot](https://cloud.githubusercontent.com/assets/12681652/18229154/e97b0d1c-7221-11e6-9992-f78d1b94abb7.png)


## Output

#### Trimmed image:

![farmbot_0-trimmed](https://cloud.githubusercontent.com/assets/12681652/18229153/e971dddc-7221-11e6-9ed6-be40529b4115.png)


#### Processed image (enlarged):

![farmbot_1-processed](https://cloud.githubusercontent.com/assets/12681652/18229151/e96aa5b2-7221-11e6-93b2-0e56ee586d42.png)


#### Black Pixel text file (x, y) from top left of image:

```
90,1
92,1
94,1
96,1
...
```

#### Plant coordinate text file (x, y) from bottom left of bed:

```
1370,1370
1396,1370
1422,1370
1448,1370
...
```

#### Simulated plant-rendered image - plants small:

![simulated_stage-03](https://cloud.githubusercontent.com/assets/12681652/18229214/09ac3d10-7225-11e6-87ec-a5304a1f40b2.png)


#### Simulated plant-rendered image - plants larger:

![simulated_stage-06](https://cloud.githubusercontent.com/assets/12681652/18229207/94f1f316-7224-11e6-8997-b901ca91b7d6.png)


#### __Optimized__ plant coordinate text file (x, y) from bottom left of bed:

```
200.0,460.0
200.0,486.0
213.0,499.0
226.0,486.0
...
```

Coordinate path optimization uses a nearest neighbor algorithm, beginning at the leftmost point.

![farmbot_optimization-details](https://cloud.githubusercontent.com/assets/12681652/18240497/0cbd3b76-7301-11e6-8943-b92defbbadcd.png)


## Options

variable | default | description
 :---: | :---: | :---
`image` | farmbot.png | Input image: try a dark object on a light background.
`size` | 200 | Pixel width/height used to resize the image. Affects number of coordinate results.
`scale` | 13 | Scale for image rendered in plants.
`startx` | 200 | X coordinate of bottom left of plant-rendered image.
`starty` | 200 | Y coordinate of bottom left of plant-rendered image.
`n` | 2 | (2,3,4,8). Ordered dither tiling size. Affects number of coordinate results.

## Convert text

##### Convert text to plant coordinates:

`bash text.sh`

Enter text at prompt.
```
Enter text and press <Enter>:
farmbot
```

![farmbot_3-coord_simulated_stage-03](https://cloud.githubusercontent.com/assets/12681652/18233267/0e02a13e-7297-11e6-889c-7171a9df4557.png)

See [options](#options) for descriptions of parameters

## User interface screenshot
![user_interface_screenshot](https://cloud.githubusercontent.com/assets/12681652/20242744/d612095c-a8ee-11e6-8c80-ee3134be3eea.png)
