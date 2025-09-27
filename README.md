
## How to integrate Aurora Sofle V2 updates from main

```
dir=$(pwd)
cd ..
git clone https://github.com/zmkfirmware/zmk.git
cp -Rf app/boards/shields/splitkb_aurora_sofle/* "$dir"/boards/shields/splitkb_aurora_sofle_dongled/
cd $dir
```
