How to enable OpenVFD Service for tx box running armbian (Amlogic, Rockchip,...)

1. Download kernel headers for amlogic from https://users.armbian.com/balbes150/arm-64/deb/ For other tv box types please contact Rom authors.
2. Install kernel headers with dpkg -i
3. Git clone https://github.com/arthur-liberman/linux_openvfd
4. Edit Makefile content as my Makefile
5. Run sudo ln -sf /boot/System.map-$(uname -r) /lib/modules/$(uname -r)/build/System.map
6. Run make -j 4 within linux_openvfd/driver folder
7. Run sudo depmod -a (Optional)
8. Run sudo make modules_install
9. Verify if our openvfd module is successfully installed/loaded by lsmod. If not, run sudo modprobe openvfd.
10. Run make OpenVFDService within linux_openvfd. Add executable priviledge by running chmod +x 
11. Modify your device tree source by adding openvfd item
openvfd {
	compatible = "open,vfd";
	dev_name = "openvfd";
	status = "okay";
};
12. Place your vfd.conf into /storage/.config folder.
13. Create openvfd.service as mine.
14. Start openvfd.service
15. Enable openvfd.service for autorestart after reboot.
