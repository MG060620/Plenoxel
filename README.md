### SETUP ENVIRONMENT
#### Plenoxels: Radiance Fields without Neural Networks
#### Windows is not officially supported, and we have only tested with Linux. Adding support would be welcome.
First create the virtualenv, we recommend using conda:
        
        
     conda env create -f environment.yml
     conda activate plenoxel

Then clone the repo and install the library at the root (svox2), which includes a CUDA extension:


    git clone https://github.com/sxyu/svox2.git

And if and only if your CUDA toolkit is older than 11, you will need to install CUDA toolkit ( >= version 11). In the link below, it is Cuda version 11.7:

     https://developer.nvidia.com/cuda-11-7-0-download-archive?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=20.04&target_type=deb_local

Finally, to install the main library, simply run:

     pip install -e . --verbose

If a error occurs: ImportError: cannot import name 'notf' from 'tensorboard.compart'. Sovled it by uninstalling jax and reinstalling the cuda version of iy: 

    pip uninstall jax jaxlib -y
    pip install "jax[cuda11_cudnn805]==0.3.10" -f https://storage.googleapis.com/jax-releases/
