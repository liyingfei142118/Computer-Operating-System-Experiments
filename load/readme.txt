virt  phys
0-4M  0-4M
0-3G  0-4M
3G+64K(0xC001000) => 64K


[3G,3G+64K]      stack
[3G+64K,3G+...]  code

fd.img
boot.img uxos.img

软盘结构/程序功能
主结构

int 13h

int drive = DISK_A;
int track = 0;
int head = 0;
int sector = 2;
int total_sectors = 128;

while (total_sectors > 0) {
   read_sector (drive, track, head, sector);

   if (++sector == 19) {
      sector = 1;
      if (++head == 2) {
         head = 0;
         track++;
      }
   }
   total_sectors--;
}


