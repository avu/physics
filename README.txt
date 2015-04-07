Ubuntu configuration:

sudo apt-get install freeglut3 freeglut3-dev
sudo apt-get install libxmu-dev libxi-dev

Windows MinGW configuration:
1. download freeglut package http://files.transmissionzero.co.uk/software/development/GLUT/freeglut-MinGW-3.0.0-1.mp.zip
2. create c:\glut\bin c:\glut\include c:\glut\Release folders
3. copy from freeglut-MinGW-3.0.0-1.mp.zip
   bin\freeglut.dll --> c:\glut\bin
   include\GL --> c:\glut\include\GL
   lib\libfreeglut* --> c:\glut\Release
4. Add -D GLUT_ROOT_PATH=c:\glut into CMake options in the project settings
5. Add c:\glut\bin into windows PATH variable to run the demos
