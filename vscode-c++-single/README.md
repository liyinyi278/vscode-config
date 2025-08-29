这是单个目录的编译配置包，需要修改CMakeLists.txt中的SRC_DIR为自己要编译的当前目录：

if(NOT DEFINED SRC_DIR)
    # 默认目录（可选，避免未传参数时报错，可改为你的常用目录）
    set(SRC_DIR "${CMAKE_SOURCE_DIR}/src/ch11/ex07" CACHE PATH "源文件所在目录")    
endif()    

上面的CMAKE_SOURCE_DIR为项目的根目录，/src/ch11/ex07是你要修改的编译目录。

！在编译时，一定要确保你编译的目录处于VSCode的激活状态：

在 VS Code 中，导航到你的源代码目录（比如 src/ch11/ex07），双击打开其中一个 .cpp 或 .c 文件（比如 main.cpp）。

确保该文件是 “当前激活的”（即编辑区显示的是这个文件，标题栏高亮）。

此时 ${fileDirname} 会自动变为该文件所在的目录（比如 D:\cpp-code\CPP-Plus\src\ch11\ex07），-DSRC_DIR 就会传递正确的路径。