cmake_minimum_required(VERSION 3.5)
project(CardNumberDetector)

include_directories(
        libs/opencv/include/
        libs/opencv/include/opencv2/
        libs/opencv/include/opencv/
        libs/opencv/lib
        src/
        src/cpp
)

file(GLOB_RECURSE SOURCE_FILE src/cpp/*.*)
file(GLOB_RECURSE HEADERS_FILE libs/opencv/include/opencv/*.* libs/opencv/include/opencv2/*.* libs/opencv/include/opencv2/text/*.*)

set(CMAKE_CXX_STANDARD 11)
link_directories(cryptoniteXUtest
        libs/opencv/lib
        )
add_executable(CardNumberDetector ${SOURCE_FILE} ${HEADERS_FILE})
target_link_libraries(CardNumberDetector opencv_core opencv_imgproc opencv_calib3d opencv_video opencv_features2d opencv_ml opencv_highgui opencv_objdetect opencv_text opencv_imgcodecs)