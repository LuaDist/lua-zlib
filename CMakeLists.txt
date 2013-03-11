# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Drahoš
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( lua-zlib C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

find_package ( ZLIB REQUIRED )
#find_library ( Z_LIBRARY NAMES zlib z )

install_lua_module ( zlib lua_zlib.c zlib.def LINK ${ZLIB_LIBRARIES} )
install_data ( README )
install_test ( tap.lua test.lua amnon_david.gz tom_macwright.gz tom_macwright.out )
