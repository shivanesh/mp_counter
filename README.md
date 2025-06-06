# stat on pixels

## Introduction

This script is to be used in conjunction with a experimental method designed by DCCEEW NSW only. Microplastics caught in a net trawling method are cleaned and dyed with Nile Red. The Nile Red attaches to the micrplastics and glows orange under blue light. The microplastics are presented in a petri dish under a camera with blue light.
The camera images look like orange spots over a black ground. The script counts these oranges spots and tallys them.

The script requires naming the filenames of images with suffixes of either "_SML", "_MED", or "_LRG" to tag as small, medium or large.

## Method development

The script in this repo is based on the original 'stat-on-pixels' code developed by Rajitha Athukorala as a part of his PhD internship with DCCEEW. The original repo can be accessed through https://github.com/Rajitha-Athukorala/stat_on_pixel.git 

The users of the method described in the MethodX paper, 'An integrated, tiered microplastic workflow, supporting rapid broadscale detection options.' (under review) are advised to use the script available in this repo for reprodcuing results. 

The general users interested on the 'stat-on-pixel' methodolody and it's future developments are advised to refer to:
[‘Stat on pixels’: An automated counting method for selective fluorescent-stained microplastics using Nile Red dye](https://mssanz.org.au/modsim2023/files/athukorala548.pdf),
Authors: Rajitha Athukorala, Samantha K. Lynch, Colin Johnson, Alessandra L. Suzzi, Shivanesh Rao and Edwina L. Foulsham

## What happens inside 'stat-on-pixels'

'Sat-on-pixels' is an easy to use cv2 based procedure to automate the counting of micro plastics. It has 5 main steps.

1. Raw image is split into the respective red, green and blue bands
2. Gaussian blur is applied with a user defined kernel size and an in-situ variance depending on the kernel size
3. An adaptive thresholding step where the image is segmented to a binary image based on the object pixel intensity within a user defined neighbourhood
4. A contour extraction algorithm based on border following (Suzuki et al. 1985) is used on the binary image to extract the outer contours of the objects
5. A filter based on the contour size specified by the user is applied to count the appropriated objects within a certain size range

For more information please contact: shivanesh.rao@environment.nsw.gov.au
