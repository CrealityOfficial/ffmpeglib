if(CC_INSTALL_FFMPEGLIB)
	__install_directory_specif(${CMAKE_CURRENT_SOURCE_DIR}/include/ ffmpeglib)
	
	set(LIBS)
	set(DLLS)
	
	if(CC_BC_WIN)
		set(LIBS ${CMAKE_CURRENT_SOURCE_DIR}/lib/avcodec.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/avdevice.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/avfilter.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/avformat.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/avutil.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/swresample.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/postproc.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/swscale.lib
				 )
		set(DLLS ${CMAKE_CURRENT_SOURCE_DIR}/bin/avcodec-58.dll
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avdevice-58.dll
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avfilter-7.dll
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avformat-58.dll
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avutil-56.dll
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/postproc-55.dll
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/swresample-3.dll
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/swscale-5.dll
				 )
	elseif(CC_BC_LINUX)
		set(LIBS ${CMAKE_CURRENT_SOURCE_DIR}/lib/libavcodec.so
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/libavdevice.so
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/libavfilter.so
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/libavformat.so
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/libavutil.so
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/libswresample.so
				 ${CMAKE_CURRENT_SOURCE_DIR}/lib/libswscale.so
				 )	
	else()
	endif()
	
	INSTALL(FILES ${LIBS} DESTINATION lib)
	INSTALL(FILES ${DLLS} DESTINATION bin)
endif()