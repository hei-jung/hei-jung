[GPU usage monitoring (CUDA)](https://unix.stackexchange.com/questions/38560/gpu-usage-monitoring-cuda)

[Ubuntu에서 GPU 모니터링 하는 4가지 방법](https://eungbean.github.io/2018/08/23/gpu-monitoring-tool-ubuntu/)

### To see the total amount of physical RAM installed

```console
user@pc:~$ sudo lshw -c memory
```

### To determine how much memory the computer has

```console
user@pc:~$ cat /proc/meminfo
```

### To see how much memory the computer has

(total available memory)

```console
user@pc:~$ grep MemTotal /proc/meminfo
```

### To see how much free memory the pc has

```console
user@pc:~$ free -m
```

[How to clear RAM memory cache, buffer and swap space on linux](https://www.tecmint.com/clear-ram-memory-cache-buffer-and-swap-space-on-linux/)

[linux command to check memory usage in percentage](https://www.codegrepper.com/code-examples/shell/linux+command+to+check+memory+usage+in+percentage)
