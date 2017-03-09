# -*- Mode: CMake; indent-tabs-mode: nil; tab-width: 4 -*-
#
# Copyright (C) 2017 Canonical, Ltd.
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; version 3.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

cmake_minimum_required (VERSION 3.0)

find_package (PkgConfig)
pkg_check_modules (PC_PULSE_AUDIO REQUIRED libpulse)
pkg_check_modules (PC_PULSE_AUDIO_SIMPLE REQUIRED libpulse-simple)
include_directories (${PC_PULSE_AUDIO_INCLUDE_DIRS}
                     ${PC_PULSE_AUDIO_SIMPLE_INCLUDE_DIRS})

add_executable (pulseaudio-example pacat-simple.c)
target_link_libraries (pulseaudio-example
                       ${PC_PULSE_AUDIO_LIBRARIES}
                       ${PC_PULSE_AUDIO_SIMPLE_LIBRARIES})

install (TARGETS pulseaudio-example DESTINATION /usr/bin)
