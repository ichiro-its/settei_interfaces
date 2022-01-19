cmake_minimum_required(VERSION 3.5)
project(settei_interfaces)

if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "srv/aruku/ArukuGetData.srv"
  "srv/aruku/ArukuSetData.srv"
  "srv/atama/AtamaGetData.srv"
  "srv/atama/AtamaSetData.srv"
  "srv/suiryoku/SuiryokuGetData.srv"
  "srv/suiryoku/SuiryokuSetData.srv"
  "msg/aruku/Balance.msg"
  "msg/aruku/InitAngles.msg"
  "msg/aruku/Kinematic.msg"
  "msg/aruku/Odometry.msg"
  "msg/aruku/ArukuOffset.msg"
  "msg/aruku/PID.msg"
  "msg/aruku/Ratio.msg"
  "msg/atama/Center.msg"
  "msg/atama/Gain.msg"
  "msg/atama/Limit.msg"
  "msg/atama/AtamaOffset.msg"
  "msg/atama/PanDistanceToTilt.msg"
  "msg/atama/PanTiltToDistance.msg"
  "msg/suiryoku/Dribble.msg"
  "msg/suiryoku/Follow.msg"
  "msg/suiryoku/Kick.msg"
  "msg/suiryoku/Move.msg"
  "msg/suiryoku/Pivot.msg"
  "msg/suiryoku/Position.msg"
 )

ament_export_dependencies(rosidl_default_runtime)
ament_package()
