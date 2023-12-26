# Slurm Node Usage

Inspired by Htop and [TengdaHan/slurm-web](https://github.com/TengdaHan/slurm_web)

![image](https://github.com/simonLeary42/slurm-node-usage/assets/71396965/8bd9240d-fa43-4426-a10b-6b8dede2a8a2)

## Features
* uses only python standard library
* finds out which partitions can be used to access a given node, and then finds out which of those partitions the current user is actually allowed to use
* pipes itself to `less` but you can change/disable pager with the `PAGER` env. var.
* allows for cacheing the output of `sinfo` to a file

## Downsides
* The `--json` Slurm argument prevents the use of any other arguments which would filter the output
* If a multi-node job has GPUs allocated, this script does not bother trying to track down which GPUs are taken. Instead it neglects to mark any GPUs as allocated and prints a warning.

## Requirements
* Slurm version that supports `--json` argument
