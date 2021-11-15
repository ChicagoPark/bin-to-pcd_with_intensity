# bin-to-pcd_with_Intensity
KITTI Visualization, KITTI Intensity, KITTI point cloud intensity

Point cloud transformation program from bin file to pcd with intensity



### [1] Point clouds without intensity
`has a problem to do researches which need to use intensity of point clouds`



### [2] Point clouds with intensity
`all the points' intensity values are defined`

<img width="300" alt="IMG" src="https://user-images.githubusercontent.com/73331241/141401889-1f0920ca-4837-4f61-9202-bc35c579e030.png">

<img width="300" alt="IMG" src="https://user-images.githubusercontent.com/73331241/141401882-ae45bb14-f0b9-47bd-9659-2749beb5c2b1.png">

<img width="300" alt="IMG" src="https://user-images.githubusercontent.com/73331241/141401905-1ebf5b52-b88d-4e78-b146-555a0f2303da.png">


---
# How to do

## [1] Modify CMakeLists.txt

```bash
find_package(PCL 1.2 REQUIRED)
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

FIND_PACKAGE( Boost 1.65 COMPONENTS program_options REQUIRED )
#add_executable (pcl_visualizer_demo pcl_visualizer_demo.cpp)
#target_link_libraries (pcl_visualizer_demo ${PCL_LIBRARIES})

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries (${PROJECT_NAME} ${PCL_LIBRARIES} ${Boost_LIBRARIES})
```

## [2] get main.cpp from this repository

## [3] After build your code, operate the executable file

```bash
rosrun <PKG_NAME> pcd_with_intensity --m=bin2pcd --b=<ABSOLUTE_PATH_OF_BIN_FOLDER>
--p=<ABSOLUTE_PATH_OF_DESTINATION_PCD_FOLDER>

# Example code
rosrun first_pkg pcd_with_intensity --m=bin2pcd --b=/home/kaai/chicago_ws/src/first_pkg/src/KITTI/bin/
--p=/home/kaai/chicago_ws/src/first_pkg/src/KITTI/pcd/
```
