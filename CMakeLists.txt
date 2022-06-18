cmake_minimum_required(VERSION 3.11)

project(TrafficMonitor)

# enabled cxx 11
set(CMAKE_CXX_STANDARD 11)
# enable mfc
ADD_DEFINITIONS(-D_AFXDLL)
SET(CMAKE_MFC_FLAG 2)

add_subdirectory(OpenHardwareMonitorApi)

file(GLOB traffic_SRC ${CMAKE_CURRENT_SOURCE_DIR}/include/PluginInterface.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/AboutDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/AdapterCommon.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/AppAlreadyRuningDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/auto_start_helper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/BaseDialog.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CalendarHelper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CAutoAdaptSettingsDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CMFCColorDialogEx.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ColorSettingListCtrl.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ComboBox2.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CPUUsage.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/crashtool.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CTabCtrlEx.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CVariant.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DisplayTextSettingDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DrawCommonEx.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/FilePathHelper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HighResolutionTimer.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficCalendarDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficFile.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficListDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/LinkStatic.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ColorStatic.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/Common.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CommonData.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CSkinPreviewView.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DonateDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DrawCommon.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/GeneralSettingsDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/IconSelectDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/IniHelper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficListCtrl.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ListCtrlEx.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/MainWndColorDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/MainWndSettingsDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/MessageDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/NetworkInfoDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/OptionsDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PictureStatic.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PluginInfoDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PluginManager.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PluginManagerDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/Resource.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SelectConnectionsDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SetItemOrderDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SimpleXML.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SkinDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SkinFile.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SpinEdit.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/StaticEx.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/stdafx.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TabDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/targetver.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskbarColorDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskbarDefaultStyle.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskBarDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskbarItemOrderHelper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskBarSettingsDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/Test.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TinyXml2Helper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/tinyxml2/tinyxml2.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TrafficMonitor.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TrafficMonitorDlg.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/UpdateHelper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/WIC.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/WindowsSettingHelper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/WinVersionHelper.h
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/AboutDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/AdapterCommon.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/AppAlreadyRuningDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/auto_start_helper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/BaseDialog.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CalendarHelper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CAutoAdaptSettingsDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CMFCColorDialogEx.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ColorSettingListCtrl.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ComboBox2.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CommonData.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CPUUsage.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/crashtool.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CTabCtrlEx.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CVariant.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DisplayTextSettingDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DrawCommonEx.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/FilePathHelper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficCalendarDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficFile.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficListDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/LinkStatic.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ColorStatic.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/Common.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/CSkinPreviewView.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DonateDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/DrawCommon.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/GeneralSettingsDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/IconSelectDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/IniHelper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/HistoryTrafficListCtrl.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/ListCtrlEx.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/MainWndColorDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/MainWndSettingsDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/MessageDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/NetworkInfoDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/OptionsDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PictureStatic.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PluginInfoDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PluginManager.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/PluginManagerDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SelectConnectionsDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SetItemOrderDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SimpleXML.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SkinDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SkinFile.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/SpinEdit.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/StaticEx.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/stdafx.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TabDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskbarColorDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskbarDefaultStyle.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskBarDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskbarItemOrderHelper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TaskBarSettingsDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/Test.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TinyXml2Helper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/tinyxml2/tinyxml2.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TrafficMonitor.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TrafficMonitorDlg.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/UpdateHelper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/WIC.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/WindowsSettingHelper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/WinVersionHelper.cpp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/TrafficMonitor.rc
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/license.bin
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/TrafficMonitor.rc2
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/about_background.bmp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/about_background_hd.bmp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/bitmap3.bmp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/donate.bmp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/donate_wechart.bmp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/close.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/connection.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/exit.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/function.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/help.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/info.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/item.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/lock.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/main_window.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/more.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/mouse.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/notify.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/pin.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/plugins.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/setting.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/skn.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/statistics.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/taskbar_window.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/menu_icon/task_manager.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/notifyicon.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/notifyicon2.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/notifyicon3.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/notifyicon4.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/notifyicon5.ico
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/notify_preview.bmp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/notify_preview_light.bmp
                    ${CMAKE_CURRENT_SOURCE_DIR}/TrafficMonitor/res/TrafficMonitor.ico)

add_executable(trafficmonitor ${traffic_SRC})

target_include_directories(trafficmonitor PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include/)

#support unicode
target_compile_definitions(trafficmonitor PRIVATE _AFXDLL _UNICODE UNICODE)

target_link_libraries(trafficmonitor PRIVATE hardwaremonitor)
# set_target_properties(trafficmonitor PROPERTIES
#     COMPILE_DEFINITIONS _AFXDLL,_UNICODE,UNICODE,_BIND_TO_CURRENT_CRT_VERSION,_BIND_TO_CURRENT_MFC_VERSION
#     LINK_FLAGS "/ENTRY:\"wWinMainCRTStartup\"")