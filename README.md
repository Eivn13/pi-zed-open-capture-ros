Na spravnu funkcnost tohto repozitara treba nainstalovat zed-open-capture https://github.com/stereolabs/zed-open-capture

Tuto cast systemu som pustal s prikazom roslaunch zed-open-capture-ros new\_zed\_node.launch resolution:=2

Parameter resolution nastavuje v akom rozliseni a akou frekvenciou bude posielat kamera obraz. 0 == HD2K a 15 fps, 1 == HD1080 a 30 fps, 2 == HD720 a 60 fps, 3 == VGA a 100 fps.

Subor src/zed\_node.cpp posiela cez ROS zbernice obraz "/zed\_2/whole/image\_raw" a imu data "/zed\_2/imu/raw". Obraz vznika spojenim obrazu z lavej a pravej sosovky.

Subor src/zed\_node\_multiple\_cameras.cpp som vobec nepouzival ale mozno sa bude hodit, tak som ho nezmazal.

TODO: prerobit v CMakeLists.txt linky, aby sa dynamicky menili podla user name.
