# Example data

This repo contains data to demonstrate how to use the panorama generator and multi-calibration tool.
Multicamera Calibration Tool (https://gitlab-mi.informatik.uni-ulm.de/ifr97/multicamera-calibration.git)
Panorama Generator (https://gitlab-mi.informatik.uni-ulm.de/ifr97/panorama-generator.git)

## Getting Started

clone this repo and copy one of the tools above into the data folder:
```
git clone https://gitlab-mi.informatik.uni-ulm.de/ifr97/example-data.git
cd example-data
cp /path/to/multicamera-calibration-build-folder/Release/multicalibration.exe .
```
or if you want to use the panorama generator:
```
git clone https://gitlab-mi.informatik.uni-ulm.de/ifr97/panorama-generator.git
cd example-data
cp /path/to/panorama-generator-build-folder/Release/PanoramaGenerator.exe .
```

### Usage for Multicamera Calibration
```
Usage: ./multicalibration -[m|c|v|e|w|h|tc] calibration_result.xml file_list.xml
m - min matches (default 100)
v - verbose (default false)
e - show feature extraction (default false)
tc - termination count (default 10)
c - number of cameras
w - physical width of pattern in user defined unit (usually cm)
h - physical height of pattern in user defined unit (usually cm)


$ ./multicalibration.exe -c=36 -w=109 -h=82 all_images.xml calibration.xml
camera_count=36
patternWidth=109
patternHeight=82
initialized for camera 0 rms = 1.25491
initialized camera matrix for camera 0 is
[1854.2043, 0, 1063.5328;
 0, 1856.4719, 801.8584;
 0, 0, 1]
xi for camera 0 is []
initialized for camera 1 rms = 1.34718
initialized camera matrix for camera 1 is
[1841.5892, 0, 1050.0885;
 0, 1842.4463, 774.03088;
 0, 0, 1]
xi for camera 1 is []
...
```

### Usage for Panorama Generator
```
Usage: ./PanoramaGenerator.exe -[w|d|n] calibration.xml images.xml [outputdir]
w - cube face size in pixel (default 2000)
d - write debug images (default false)
n - number of cameras

./PanoramaGenerator.exe -n=36 calibration.xml images.xml panorama/
```


## Authors

* **Sebastian Hartwig**