# Copyright 2011 Free Software Foundation, Inc.
#
# This file is part of GNU Radio
#
# GNU Radio is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3, or (at your option)
# any later version.
#
# GNU Radio is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with GNU Radio; see the file COPYING.  If not, write to
# the Free Software Foundation, Inc., 51 Franklin Street,
# Boston, MA 02110-1301, USA.

########################################################################
# Include python install macros
########################################################################
include(GrPython)
if(NOT PYTHONINTERP_FOUND)
    return()
endif()

########################################################################
# Install python sources
########################################################################
GR_PYTHON_INSTALL(
    FILES
    __init__.py
    qt_pdu_source.py
    pdu_flow_ctrl.py DESTINATION ${GR_PYTHON_DIR}/pdu_utils
)

########################################################################
# Handle the unit tests
########################################################################
include(GrTest)

set(GR_TEST_TARGET_DEPS gnuradio-pdu_utils)
set(GR_TEST_PYTHON_DIRS ${CMAKE_BINARY_DIR}/swig)
GR_ADD_TEST(qa_tags_to_pdu_X ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_tags_to_pdu_X.py)
GR_ADD_TEST(qa_take_skip_to_pdu_X ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_take_skip_to_pdu_X.py)
GR_ADD_TEST(qa_pdu_to_bursts_X ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_to_bursts_X.py)
GR_ADD_TEST(qa_qt_pdu_source ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_qt_pdu_source.py)
GR_ADD_TEST(qa_tag_message_trigger_X ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_tag_message_trigger_X.py)
GR_ADD_TEST(qa_pdu_gmsk_fc ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_gmsk_fc.py)
GR_ADD_TEST(qa_pdu_set_m ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_set_m.py)
GR_ADD_TEST(qa_pdu_split ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_split.py)
GR_ADD_TEST(qa_message_gate ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_message_gate.py)
GR_ADD_TEST(qa_message_counter ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_message_counter.py)
GR_ADD_TEST(qa_message_emitter ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_message_emitter.py)
GR_ADD_TEST(qa_message_keep_1_in_n ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_message_keep_1_in_n.py)
GR_ADD_TEST(qa_pdu_preamble ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_preamble.py)
GR_ADD_TEST(qa_pack_unpack ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pack_unpack.py)
GR_ADD_TEST(qa_extract_metadata ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_extract_metadata.py)
GR_ADD_TEST(qa_upsample ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_upsample.py)
GR_ADD_TEST(qa_pdu_add_noise ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_add_noise.py)
GR_ADD_TEST(qa_pdu_burst_combiner ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_burst_combiner.py)
GR_ADD_TEST(qa_msg_drop_random ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_msg_drop_random.py)
GR_ADD_TEST(qa_pdu_head_tail ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_head_tail.py)
GR_ADD_TEST(qa_time_delta ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_time_delta.py)
GR_ADD_TEST(qa_pdu_length_filter ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_length_filter.py)
GR_ADD_TEST(qa_pdu_logger ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_logger.py)
GR_ADD_TEST(qa_pdu_binary_tools ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_binary_tools.py)
GR_ADD_TEST(qa_pdu_downsample ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_downsample.py)
GR_ADD_TEST(qa_pdu_commutator ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_commutator.py)
GR_ADD_TEST(qa_pdu_complex_to_mag2 ${PYTHON_EXECUTABLE} ${CMAKE_CURRENT_SOURCE_DIR}/qa_pdu_complex_to_mag2.py)
