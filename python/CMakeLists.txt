include_directories(${PROJECT_SOURCE_DIR})

include_directories(${EIGEN3_INCLUDE_DIR})
include_directories(${CHOLMOD_INCLUDE_DIR})
include_directories(${CSPARSE_INCLUDE_DIR})



add_subdirectory(EXTERNAL/pybind11)
pybind11_add_module(g2o g2o.cpp)
target_link_libraries(g2o PRIVATE 
    core
    solver_cholmod
    solver_csparse
    solver_eigen
    solver_dense
    solver_pcg
    solver_slam2d_linear
    solver_structure_only
    types_data
    types_icp
    types_sba
    types_sclam2d
    types_sim3
    types_slam2d
    types_slam2d_addons
    types_slam3d
    types_slam3d_addons
    contrib
)
