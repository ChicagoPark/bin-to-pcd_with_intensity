# bin-to-pcd_with_Intensity
KITTI Visualization, KITTI Intensity, KITTI point cloud intensity

Point cloud transformation program from bin file to pcd with intensity



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
