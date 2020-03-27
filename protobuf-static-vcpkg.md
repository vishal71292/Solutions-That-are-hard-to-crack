# Issue Faced:

  Msvcp140.dll is missing 
  
  when c++ console project was compiled with protobuf using vcpkg.
  
  keywords :  c++    visual stido   vcpkg     protobuf    
  
  
# Solution :

  Remove earlier installed vcpk package for protobuf and use the following command
  
  `vcpkg install protobuf protobuf:x64-windows-static`
  
  This will install the package with staic mode ON.
  
  
  Now need to modify the <project>.vccproj  file to make visual studio to use static lib.
  
  Add the following lines in Global PropertyGroup

    <VcpkgTriplet Condition="'$(Platform)'=='Win32'">x86-windows-static</VcpkgTriplet>
    <VcpkgTriplet Condition="'$(Platform)'=='x64'">x64-windows-static</VcpkgTriplet>
  
  
  Now, Go to properties of project and In C/C++ ->  Code Generation -> Runtime Library -> MT
  
  
  Thats it :) Have fun (y)
  
  

Reference-1 :  https://stackoverflow.com/questions/58506430/how-to-statically-link-vcpkg-produced-lib-file-in-visual-studio
Reference-2 :  https://developerpaul123.github.io/c++/cmake/using-vcpkg-on-windows/
