# About

C implementation of the three-dimensional Multiscale Entropy algorithm for {paper1} and {paper2}. Implementation for one and two-dimensional Multiscale Entropy also included.

# Installation

## Step 1: Clone repo.

From a desired directory, do this:

```console
git clone https://github.com/bcerdam/Multiscale_Entropy_id.git
cd Multiscale_Entropy_id
python3 -m venv env
source ./env/bin/activate
pip install -v -e . 
```

## Step 2: Install requirements.

```console
pip install -r requirements.txt
```

## Step 3: Compile C code.

Should work out of the box for Ubuntu (gcc). It should also work for macOS, however, you need to set up ([Clang](https://clang.llvm.org/get_started.html)). Windows hasn't been tested, it probably doesn't work.

#### gcc
```console
gcc -o core_c/mse_1d/executables/mse_1d_p core_c/mse_1d/scripts/mse_1d.c core_c/mse_1d/scripts/read_csv.c core_c/mse_1d/scripts/signal_std.c core_c/mse_1d/scripts/utils.c  -lm -Icore_c/mse_1d/headers && \
gcc -o core_c/mse_2d/executables/mse_2d_p core_c/mse_2d/scripts/mse_2d.c core_c/mse_2d/scripts/read_csv.c core_c/mse_2d/scripts/utils.c  -lm -Icore_c/mse_2d/headers && \
gcc -o core_c/mse_3d/executables/mse_3d_p core_c/mse_3d/scripts/mse_3d.c core_c/mse_3d/scripts/read_csv.c core_c/mse_3d/scripts/signal_std.c core_c/mse_3d/scripts/utils.c -lm -fopenmp -Icore_c/mse_3d/headers
```

#### clang:
```console
clang -Xclang -fopenmp -I/usr/local/opt/libomp/include -L/opt/homebrew/Cellar/libomp/16.0.6/lib -lomp -Icore_c/mse_1d/headers core_c/mse_1d/scripts/mse_1d.c core_c/mse_1d/scripts/read_csv.c core_c/mse_1d/scripts/signal_std.c core_c/mse_1d/scripts/utils.c -o core_c/mse_1d/executables/mse_1d_p  && \
clang -Xclang -fopenmp -I/usr/local/opt/libomp/include -L/opt/homebrew/Cellar/libomp/16.0.6/lib -lomp -Icore_c/mse_2d/headers core_c/mse_2d/scripts/mse_2d.c core_c/mse_2d/scripts/read_csv.c core_c/mse_2d/scripts/utils.c -o core_c/mse_2d/executables/mse_2d_p  && \
clang -Xclang -fopenmp -I/usr/local/opt/libomp/include -L/opt/homebrew/Cellar/libomp/16.0.6/lib -lomp -Icore_c/mse_3d/headers core_c/mse_3d/scripts/mse_3d.c core_c/mse_3d/scripts/read_csv.c core_c/mse_3d/scripts/signal_std.c core_c/mse_3d/scripts/utils.c -o core_c/mse_3d/executables/mse_3d_p
```

# Multiscale_Entropy_id
