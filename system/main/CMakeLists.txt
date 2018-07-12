set(SOURCE_VIDEO_READ_INDEX AddIndexServer.cpp)
add_executable(AddIndexServer ${SOURCE_VIDEO_READ_INDEX})

set(SOURCE_VIDEO_SYSTEM VideoRetrievalSystem.cpp)
add_executable(VideoRetrievalSystem ${SOURCE_VIDEO_SYSTEM})

target_link_libraries(
        VideoRetrievalSystem
        libbinary.so
        libfeature.so
        pthread
        libboost_system.so
        libboost_filesystem.so
        libboost_thread.so
        libopencv_core.so
		libopencv_highgui.so
        libopencv_imgcodecs.so
        libopencv_imgproc.so
        libopenblas.so.0
        ${PROJECT_SOURCE_DIR}/caffe/build/lib/libcaffe.so
        libglog.so
)

target_link_libraries(
        AddIndexServer
        libopencv_core.so
		libopencv_imgcodecs.so
        libopencv_highgui.so
		libopencv_imgproc.so
        pthread
)
