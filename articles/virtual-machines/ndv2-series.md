---
 title: NDv2-series - Azure Virtual Machines
 description: Specifications for the NDv2-series VMs.
 services: virtual-machines
 author: vikancha
 ms.service: virtual-machines
 ms.topic: article
 ms.date: 02/03/2020
 ms.author: lahugh
---

# Updated NDv2-series (Preview)

The NDv2-series virtual machine is a new addition to the GPU family designed for the needs of the most demanding GPU-accelerated AI, machine learning, simulation, and HPC workloads.

NDv2 is powered by 8 NVIDIA Tesla V100 NVLINK-connected GPUs, each with 32 GB of GPU memory. Each NDv2 VM also has 40 non-HyperThreaded Intel Xeon Platinum 8168 (Skylake) cores and 672 GiB of system memory.

NDv2 instances provide excellent performance for HPC and AI workloads utilizing CUDA GPU-optimized computation kernels, and the many AI, ML, and analytics tools that support GPU acceleration 'out-of-box,' such as TensorFlow, Pytorch, Caffe, RAPIDS, and other frameworks.

Critically, the NDv2 is built for both computationally intense scale-up (harnessing 8 GPUs per VM) and scale-out (harnessing multiple VMs working together) workloads. The NDv2 series now supports 100-Gigabit InfiniBand EDR backend networking, similar to that available on the HB series of HPC VM, to allow high-performance clustering for parallel scenarios including distributed training for AI and ML. This backend network supports all major InfiniBand protocols, including those employed by NVIDIA’s NCCL2 libraries, allowing for seamless clustering of GPUs.


> [!NOTE]
> When [enabling InfiniBand](https://docs.microsoft.com/azure/virtual-machines/workloads/hpc/enable-infiniband) on the ND40rs_v2 VM, please use the 4.7-1.0.0.1 Mellanox OFED driver.
>
> Due to increased GPU memory, the new ND40rs_v2 VM requires the use of [Generation 2 VMs](https://docs.microsoft.com/azure/virtual-machines/windows/generation-2) and marketplace images. 
>
> [Sign-up to request early access to the NDv2 virtual machine preview.](https://aka.ms/AzureNDrv2Preview)
>
> Please note: The ND40s_v2 featuring 16 GB of per-GPU memory is no longer available for preview and has been superceded by the updated ND40rs_v2.

<br>

Premium Storage:  Supported

Premium Storage caching:  Supported

InfiniBand: Supported

| Size | vCPU | Memory: GiB | Temp Storage (SSD): GiB | GPU | GPU Memory: GiB | Max data disks | Max uncached disk throughput: IOPS / MBps | Max network bandwidth | Max NICs |
|---|---|---|---|---|---|---|---|---|---|
| Standard_ND40rs_v2 | 40 | 672 | 2948 | 8 V100 32 GB (NVLink) | 16 | 32 | 80000 / 800 | 24000 Mbps | 8 |

[!INCLUDE [virtual-machines-common-sizes-table-defs](../../includes/virtual-machines-common-sizes-table-defs.md)]

## Supported operating systems and drivers

To take advantage of the GPU capabilities of Azure N-series VMs, NVIDIA GPU drivers must be installed.

The [NVIDIA GPU Driver Extension](./extensions/hpccompute-gpu-windows.md) installs appropriate NVIDIA CUDA or GRID drivers on an N-series VM. Install or manage the extension using the Azure portal or tools such as Azure PowerShell or Azure Resource Manager templates. See the [NVIDIA GPU Driver Extension documentation](./extensions/hpccompute-gpu-windows.md) for supported operating systems and deployment steps. For general information about VM extensions, see [Azure virtual machine extensions and features](/.extensions/overview.md).

If you choose to install NVIDIA GPU drivers manually, see [N-series GPU driver setup for Windows](./windows/n-series-driver-setup.md) or [N-series GPU driver setup for Linux](./linux/n-series-driver-setup.md) for supported operating systems, drivers, installation, and verification steps.

## Other sizes

- [General purpose](sizes-general.md)
- [Memory optimized](sizes-memory.md)
- [Storage optimized](sizes-storage.md)
- [GPU optimized](sizes-gpu.md)
- [High performance compute](sizes-hpc.md)
- [Previous generations](sizes-previous-gen.md)

## Next steps

Learn more about how [Azure compute units (ACU)](acu.md) can help you compare compute performance across Azure SKUs.
