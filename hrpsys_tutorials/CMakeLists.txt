cmake_minimum_required(VERSION 2.8.3)
project(hrpsys_tutorials)

find_package(catkin REQUIRED COMPONENTS rostest)
catkin_package()

configure_file(${PROJECT_SOURCE_DIR}/models/SampleRobot.conf.in
  ${PROJECT_SOURCE_DIR}/models/SampleRobot.conf)
configure_file(${PROJECT_SOURCE_DIR}/models/SampleRobot.xml.in
  ${PROJECT_SOURCE_DIR}/models/SampleRobot.xml)

find_package(hrpsys)
#if(EXISTS ${hrpsys_PREFIX}/share/hrpsys/samples/HRP4C/HRP4Cmain.wrl)
#  rosbuild_add_rostest(test/hrp4c-test.launch)
#endif()
add_rostest(test/pa10-test.launch)
add_rostest(test/samplerobot-test.launch)

