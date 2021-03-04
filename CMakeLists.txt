cmake_minimum_required(VERSION 2.8.3)
project(vehicle_interface)

find_package(catkin REQUIRED COMPONENTS
 diagnostic_msgs
 geometry_msgs
 nav_msgs
 message_generation)

add_message_files(DIRECTORY msg FILES
  AcousticDeconstructionStatus.msg
  AcousticLocalization.msg
  AcousticModemAck.msg
  AcousticModemData.msg
  AcousticModemPayload.msg
  AcousticModemStatus.msg
  AcousticModemUSBLANGLES.msg
  AcousticModemUSBLLONG.msg
  Dictionary.msg
  FloatArrayStamped.msg
  NodeStatus.msg
  PathRequest.msg
  PathStatus.msg
  PilotPathRequest.msg
  PilotRequest.msg
  PilotStatus.msg
  PilotWaypointRequest.msg
  String.msg
  ThrusterCommand.msg
  ThrusterFeedback.msg
  Vector6ArrayStamped.msg
  Vector6.msg
  Vector6Stamped.msg
  VehicleStatus.msg
)

add_service_files(DIRECTORY srv FILES
  AlarmStoppedTracking.srv
  BooleanService.srv
  DictionaryService.srv
  FloatService.srv
  PathService.srv
  StringService.srv
  Vector6Service.srv
)

generate_messages(DEPENDENCIES diagnostic_msgs nav_msgs geometry_msgs)

catkin_package(CATKIN_DEPENDS diagnostic_msgs message_generation)
