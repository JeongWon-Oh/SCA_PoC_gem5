# SCA_PoC_gem5

A PoC of Side-Channel Attack on gem5.

Used [CacheSC](https://github.com/Miro-H/CacheSC.git) and [gem5](https://github.com/gem5/gem5).

## How to run

### Build gem5

```{bash}
cd gem5-SCA
scons build/X86/gem5.opt -j 64
```

### Build single-eviction (CacheSC)

```{bash}
cd SCA-PoC
make
cd demo
make single-eviction
```

### Run & plot single-eviction in gem5

```{bash}
cd gem5-SCA/gem5-quickstart
mkdir result
./gem5-SCA/build/X86/gem5.opt run.py --processor_type=verbatim > ./result/attack.log
./../../SCA-PoC/scripts/plot-log.py -o ./result -v -t ./result/attack.log
```
