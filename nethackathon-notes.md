1. Clone nethackathon/nethack repo
2. Switch to nethackathon branch
3. ./sys/unix/setup.sh sys/unix/hints/linux.370
4. make fetch-lua
5. export HACKDIR=/usr/games/lib/nethackdir
6. make WANT_WIN_TTY=1 WANT_WIN_CURSES=1 all
7. sudo make WANT_WIN_TTY=1 WANT_WIN_CURSES=1 install
8. Fix permissions of /usr/games/lib
9. sudo chgrp -R nethackathon /usr/games/lib (etc)
10. copy the /usr/games/lib/nethackdir to /nethackathon/nethack
11. sudo cp -Rp /usr/games/lib/nethackdir /nethackathon
