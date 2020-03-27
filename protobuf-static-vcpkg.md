#Issue Faced:

  Msvcp140.dll is missing 
  
  when c++ console project was compiled with protobuf using vcpkg.
  
  keywords :  c++    visual stido   vcpkg     protobuf    
  
  
#Solution :

  Remove earlier installed vcpk package for protobuf and use the following command
  
  `vcpkg install protobuf protobuf:x64-windows-static`
  
  This will install the package with staic mode ON.
  
  
  Now, Go to properties of project and In C/C++ ->  Code Generation -> Runtime Library -> MT
  
  
  Thats it :) Have fun (y)
  
  
