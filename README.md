![Logo](doc/img/restore-logo.png)

[![Build Status](https://travis-ci.org/NewProggie/Restore.svg?branch=master)](https://travis-ci.org/NewProggie/Restore) [![Coverage Status](https://coveralls.io/repos/NewProggie/Restore/badge.svg?branch=master)](https://coveralls.io/r/NewProggie/Restore?branch=master) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](http://opensource.org/licenses/MIT)

# What is RESTORE?
RESTORE: REconStruction with Texture-based Object REfinement

The 3D reconstruction of real objects from multiple images is a recent and
exciting research topic in the field of computer vision. At the same time the
demand for 3D models in the movie and game industry is increasing.

A simple and cost-efficient way of reconstruction real objects is using only
a single camera. In this project a hard- and software system is developed which
makes the 3D reconstruction of real objects easy. The hardware consists of a
turntable on which an object can be placed, a motor which drives the rotary
table, a controller to control the motor as well as a calibrated camera for
taking pictures of the object.

From the camera images a visual hull is first computed, which gives a first
rough estimation of the 3D reconstruction. This model is then refined using
only the texture of the object.

## Visual Hull
With the silhouettes of an object from multiple camera views, the first step of
the 3D reconstruction is computing the visual hull. That is the maximum volume
in 3D space which may have produced them. This step requires the camera
projection matrix from every camera image to be known.

![Visual Hull](doc/img/voxelcarving-squirrel.gif)

## Texture-based mesh refinement
With the visual hull as a first rough estimation of the final mesh
reconstruction, we can use the texture information from the given camera images
to calculate an offset for each vertex. Since the visual hull is known to be the
maximum volume (encapsulating the ground truth of the model) each vertex is
either part of the ground truth (no offset needed) or part of the visual hull.

## License
RESTORE is released under the terms of the MIT License.
