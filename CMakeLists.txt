
cmake_minimum_required(VERSION 2.8)

project(ROBOTICSCAPE)

set(FUSION_DIR Fusion/)

include_directories(
	${FUSION_DIR}
)

set(FUSION_SRCS
	${FUSION_DIR}FusionAhrs.c
	${FUSION_DIR}FusionBias.c
	${FUSION_DIR}FusionCompass.c
)


add_library(Fusion SHARED ${FUSION_SRCS})
target_include_directories(Fusion PUBLIC ${FUSION_DIR})

install(TARGETS Fusion
	DESTINATION /usr/lib
	)
