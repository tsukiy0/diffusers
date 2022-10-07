```
accelerate config

#In which compute environment are you running? ([0] This machine, [1] AWS (Amazon SageMaker)): 0
#Which type of machine are you using? ([0] No distributed training, [1] multi-CPU, [2] multi-GPU, [3] TPU [4] MPS): 2
#How many different machines will you use (use more than 1 for multi-node training)? [1]: 
#Do you want to use DeepSpeed? [yes/NO]: 
#Do you want to use FullyShardedDataParallel? [yes/NO]: 
#How many GPU(s) should be used for distributed training? [1]:
#What GPU(s) (by id) should be used for training on this machine as a comma-seperated list? [all]:
#Do you wish to use FP16 or BF16 (mixed precision)? [NO/fp16/bf16]: 
```

# Setup pytorch for CUDA11

* https://discuss.pytorch.org/t/nvidia-geforce-rtx-3090-with-cuda-capability-sm-86-is-not-compatible-with-the-current-pytorch-installation/141940/23
* https://discuss.pytorch.org/t/need-help-trouble-with-cuda-capability-sm-86/120235/39
    ```
    pippip uninstall torch torchvision 
    pip3 install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu113
    ```
* Debug 
    ```
    import torch

    torch.cuda.get_arch_list()
    torch.version.cuda
    ```

# Reducing memory

* https://github.com/ShivamShrirao/diffusers/tree/main/examples/dreambooth