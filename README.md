#Compiling and Using XMR-Stak with Alpine Linux, Donation Free<br><br>

## Install Deps 
apk add --update git cmake make gcc g++ libmicrohttpd-dev openssl-dev <br>
wget https://www.open-mpi.org/software/hwloc/v1.11/downloads/hwloc-1.11.8.tar.gz <br>
tar xzvf hwloc-1.11.8.tar.gz <br>
cd hwloc-1.11.8 <br>
./configure --prefix=/usr/local <br>
make <br>
make install <br>
cd .. <br>

## Clone Git and Compile 

git clone https://github.com/rickadoo/xmr-stak-alpine.git xmr-stak <br>
mkdir xmr-stak/build <br>
cd xmr-stak/build <br>
cmake .. -DCUDA_ENABLE=OFF -DOpenCL_ENABLE=OFF <br>
make install <br>

## Usage 

xmr-stak -o <miningpoolurl:port> -u <wallet address> -p <password> --currency <cointomine> <br>
  
# Example 

xmr-stak -o xmr-usa.dwarfpool.com:8005 -u 46tDZpvT2VN9cwobmqdyykAW9VcaJfYNbDSoomLP54dkAbE3Yit2XUYgV5DKW9MR69NuUuqjYGavjfxr8zu7yd4r8oDr3yY -p x --currency monero
