
IF(DYNAMIC_OPENSCENEGRAPH)
    ADD_DEFINITIONS(-DOSGSHADOW_LIBRARY)
ELSE()
    ADD_DEFINITIONS(-DOSG_LIBRARY_STATIC)
ENDIF()

SET(LIB_NAME osgShadow)
SET(HEADER_PATH ${OpenSceneGraph_SOURCE_DIR}/include/${LIB_NAME})
SET(TARGET_H
    ${HEADER_PATH}/Export
    ${HEADER_PATH}/OccluderGeometry
    ${HEADER_PATH}/ShadowMap
    ${HEADER_PATH}/ShadowTechnique
    ${HEADER_PATH}/ShadowTexture
    ${HEADER_PATH}/ShadowVolume
    ${HEADER_PATH}/ShadowedScene
    ${HEADER_PATH}/ShadowSettings
    ${HEADER_PATH}/SoftShadowMap
    ${HEADER_PATH}/ParallelSplitShadowMap
    ${HEADER_PATH}/Version
    ${HEADER_PATH}/ConvexPolyhedron
    ${HEADER_PATH}/DebugShadowMap
    ${HEADER_PATH}/LightSpacePerspectiveShadowMap
    ${HEADER_PATH}/MinimalCullBoundsShadowMap
    ${HEADER_PATH}/MinimalDrawBoundsShadowMap
    ${HEADER_PATH}/MinimalShadowMap
    ${HEADER_PATH}/ProjectionShadowMap
    ${HEADER_PATH}/StandardShadowMap
    ${HEADER_PATH}/ViewDependentShadowTechnique
    ${HEADER_PATH}/ViewDependentShadowMap
)

# FIXME: For OS X, need flag for Framework or dylib
SET(TARGET_SRC
    OccluderGeometry.cpp
    ShadowMap.cpp
    ShadowTechnique.cpp
    ShadowTexture.cpp
    ShadowVolume.cpp
    ShadowedScene.cpp
    ShadowSettings.cpp
    SoftShadowMap.cpp
    ParallelSplitShadowMap.cpp
    Version.cpp
    ConvexPolyhedron.cpp
    DebugShadowMap.cpp
    LightSpacePerspectiveShadowMap.cpp
    MinimalCullBoundsShadowMap.cpp
    MinimalDrawBoundsShadowMap.cpp
    MinimalShadowMap.cpp
    StandardShadowMap.cpp
    ViewDependentShadowTechnique.cpp
    ViewDependentShadowMap.cpp
    ${OPENSCENEGRAPH_VERSIONINFO_RC}
)

SET(TARGET_LIBRARIES
    osgUtil
    osgDB
    osg
    OpenThreads
)

SETUP_LIBRARY(${LIB_NAME})

