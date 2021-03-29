cmake_minimum_required(VERSION 2.8.3)
project(cosima_msgs)


find_package(catkin REQUIRED genmsg geometry_msgs std_msgs)

add_service_files(DIRECTORY srvs FILES Assemble.srv GetClamp.srv Move.srv ContactSituation.srv ContactForce.srv)
generate_messages(DEPENDENCIES geometry_msgs std_msgs)

catkin_package(CATKIN_DEPENDS message_runtime geometry_msgs std_msgs)

install(FILES
  srvs/Assemble.srv srvs/GetClamp.srv srvs/Move.srv srvs/ContactSituation.srv srvs/ContactForce.srv
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
