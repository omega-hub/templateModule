# templateModule depends on cyclops
if(TARGET cyclops)
	# Set the module name here
	SET(MODULE_NAME templateModule)

	include_directories(${OSG_INCLUDES})
	
	# Set module name and source files here
	add_library(${MODULE_NAME} MODULE 
		templateModule.cpp)

	# Set the module library dependencies here
	target_link_libraries(${MODULE_NAME}
		omega 
		omegaToolkit 
		cyclops)

	#------------------------------------------------------------------------------
	# DO NOT MODIFY ANYTHING BELOW AFTER THIS LINE
	set_target_properties(${MODULE_NAME} PROPERTIES PREFIX "")
	if(WIN32)
		set_target_properties(${MODULE_NAME} PROPERTIES FOLDER modules SUFFIX ".pyd")
	endif()
endif()
