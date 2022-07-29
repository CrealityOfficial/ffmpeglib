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
		set(DLLS ${CMAKE_CURRENT_SOURCE_DIR}/bin/avcodec-58.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avdevice-58.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avfilter-7.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avformat-58.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/avutil-56.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/postproc-55.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/swresample-3.lib
				 ${CMAKE_CURRENT_SOURCE_DIR}/bin/swscale-5.lib
				 )
	else()
	endif()
	
	INSTALL(FILES ${LIBS} DESTINATION lib)
	INSTALL(FILES ${DLLS} DESTINATION dll)
endif()