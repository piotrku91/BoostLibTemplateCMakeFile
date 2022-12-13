## How to

- Download boost library 
- Untar library to folder
- Cd to library installation folder
- Make some target folder for library somewhere
- type ./bootstrap.sh prefix=/path/to/target_lib_folder
- type ./b2
- type ./b2 install
- Go to this project folder
- Change target boost path in CMakeFiles.txt
- Create folder build
- Cd to build folder
- Execute cmake ..
- Execute make -j4
- Run example regex program: ./BoostTest < ../mail.txt
- Should parse text in Subject line