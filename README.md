# `gltfgen`

A command line time to generate glTF 2.0 animations from a numbered sequence of mesh files.


# Examples

The following example assumes that there is a sequence of meshes located at
`./meshes/animation_#.vtk` where `#` represents the frame number.
To generate an animated binary glTF file named `output.glb` in the current directory, run:

`> gltfgen output.glb "./meshes/animation_#.vtk"`

This will assume a time step of 1 second between frames. To specify a time step like 0.01 seconds between frames, use

`> gltfgen -t 0.01 output.glb "./meshes/animation_#.vtk"`

Alternatively, you may produce the same result by specifying the number of frames per second (FPS) using

`> gltfgen -f 100 output.glb "./meshes/animation_#.vtk"`


# Usage

`> gltfgen [OPTIONS] <output> <pattern>`

  - `<output>`     Output glTF file

  - `<pattern>`    A glob pattern matching files to be included in the generated glTF document. Use `#` to match a frame number. Use '{' and '}' to select parts of the pattern to be used to name meshes in the output glTF.

Run `gltfgen -h` to get more details.


# Features

Input types:
 - Unstructured Legacy VTK polygon and tetrahedral meshes in double or float format.
   Tetrahedral VTK meshes are converted to triangle meshes on the fly.

Output types:
 - glTF 2.0 in binary format.


# License

This repository is licensed under the [Mozilla Public License, v. 2.0](https://mozilla.org/MPL/2.0/).

# Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.
