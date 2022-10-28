# Segmentation fault in Verilator

The segmentation fault happens with `Verilator 5.001 devel rev v4.228-185-g7b07cf912` but did not use to happen with `Verilator 4.228 2022-10-01 rev v4.228-28-g04fff7ebd`.

## How to reproduce

```
git clone https://github.com/flaviens/verisegf2
cd verisegf2
bash run.sh
```

## Output

```
...
%Warning-UNUSEDSIGNAL: src.sv:260439:14: Bits of signal are not used: '_0005_'[6:0]
                                           : ... In instance rocket_mem_top.i_chip_top.system.tile_prci_domain.tile_reset_domain.tile.dcache.data.data_arrays_0.data_arrays_0_ext.mem_0_7
260439 |   wire [7:0] _0005_;
       |              ^~~~~~
%Warning-UNUSEDSIGNAL: src.sv:269474:9: Signal is not used: 'RW0_clk_t0'
                                          : ... In instance rocket_mem_top.i_chip_top.system.tile_prci_domain.tile_reset_domain.tile.frontend.icache.tag_array.tag_array_0_ext.mem_0_0
269474 |   input RW0_clk_t0;
       |         ^~~~~~~~~~
%Warning-UNUSEDSIGNAL: src.sv:269183:15: Bits of signal are not used: '_004_'[22:0]
                                           : ... In instance rocket_mem_top.i_chip_top.system.tile_prci_domain.tile_reset_domain.tile.frontend.icache.tag_array.tag_array_0_ext.mem_0_0
269183 |   wire [23:0] _004_;
       |               ^~~~~
%Warning-UNUSEDSIGNAL: src.sv:269184:15: Bits of signal are not used: '_005_'[22:0]
                                           : ... In instance rocket_mem_top.i_chip_top.system.tile_prci_domain.tile_reset_domain.tile.frontend.icache.tag_array.tag_array_0_ext.mem_0_0
269184 |   wire [23:0] _005_;
       |               ^~~~~
Segmentation fault (core dumped)
```
