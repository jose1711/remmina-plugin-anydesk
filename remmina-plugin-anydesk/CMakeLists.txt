#     Project: Remmina Plugin ANYDESK
# Description: Remmina protocol plugin to launch an Anydesk connection.
#      Author: Jose Riha <jose1711@gmail.com>
#     License: GPL-2+
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful, but WITHOUT
# ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or
# FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for
# more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

set(REMMINA_PLUGIN_SRCS
  src/remmina_plugin.c
)
add_library(remmina-plugin-anydesk ${REMMINA_PLUGIN_SRCS})
set_target_properties(remmina-plugin-anydesk PROPERTIES PREFIX "")
include_directories(${CMAKE_SOURCE_DIR}/remmina-plugins)
target_link_libraries(remmina-plugin-anydesk ${REMMINA_COMMON_LIBRARIES})

install(TARGETS remmina-plugin-anydesk DESTINATION ${REMMINA_PLUGINDIR})

set(APPICON16_EMBLEMS_DIR "${REMMINA_DATADIR}/icons/hicolor/16x16/emblems")
install(FILES 16x16/emblems/remmina-anydesk.png DESTINATION ${APPICON16_EMBLEMS_DIR})

set(APPICON22_EMBLEMS_DIR "${REMMINA_DATADIR}/icons/hicolor/22x22/emblems")
install(FILES 22x22/emblems/remmina-anydesk.png DESTINATION ${APPICON22_EMBLEMS_DIR})
