== Recovering save file from crash == 
```./recover -d /nethackathon/nethackdir alock```



1. Clone nethackathon/nethack repo
2. Switch to nethackathon branch
3. ./sys/unix/setup.sh sys/unix/hints/linux.370
4. make fetch-lua
5. export HACKDIR=/usr/games/lib/nethackdir
6. make WANT_WIN_TTY=1 WANT_WIN_CURSES=1 all
7. sudo make WANT_WIN_TTY=1 WANT_WIN_CURSES=1 install
8. Fix permissions of /usr/games/lib
```
sudo chgrp -R nethackathon /usr/games/lib
sudo chmod 775 /usr/games/lib/nethackdir
sudo chmod 775 /usr/games/lib/nethackdir/save
``
9. copy the /usr/games/lib/nethackdir to /nethackathon/nethack
```
sudo cp -Rp /usr/games/lib/nethackdir /nethackathon
sudo chmod 770 /nethackathon/nethackdir
sudo chmod 770 /nethackathon/nethackdir/save
find /nethackathon/nethackdir -type f -exec sudo chmod 660 -- {} +
find /nethackathon/nethackdir -type d -exec sudo chmod 770 -- {} +
sudo chmod 770 /nethackathon/nethackdir/nethack
sudo chmod 770 /nethackathon/nethackdir/recover
find /usr/games/lib -type f -exec sudo chmod 660 -- {} +
find /usr/games/lib -type d -exec sudo chmod 770 -- {} +
sudo chmod 770 /usr/games/lib/nethackdir/nethack
sudo chmod 770 /usr/games/lib/nethackdir/recover
```
