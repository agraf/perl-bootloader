main: prepare test clean

prepare: clean
	mkdir -p Bootloader
	@cp -r ../../../src/* Bootloader/
	cp -rf backup/fake_root1 .
	cp -rf backup/fake_root2 .
	@mkdir -p fake_root{1,2}/var/log/YaST2

test:
	perl -w grub1-test.pl
	perl -w lilo1-test.pl
	perl -w elilo1-test.pl
	perl -w plilo1-test.pl
	perl -w zipl1-test.pl
	perl -w none-test.pl
	perl -w multipath-test.pl
	perl -w md-raid-test.pl
	perl -w core-test.pl
	rm -rf Bootloader
	rm -rf fake_root[12]

#usefull target after failed test
clean: 
	@rm -rf Bootloader
	rm -rf fake_root*
	cp -rf backup/fake_root1 .
	cp -rf backup/fake_root2 .
