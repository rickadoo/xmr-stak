Compiling and Using XMR-Stak with Alpine Linux, Donation Free

## Install Deps
apk add --update git cmake make gcc g++ libmicrohttpd-dev openssl-dev
wget https://www.open-mpi.org/software/hwloc/v1.11/downloads/hwloc-1.11.8.tar.gz
tar xzvf hwloc-1.11.8.tar.gz
cd hwloc-1.11.8
./configure --prefix=/usr/local
make
make install
cd ..

## Clone Git and Compile

git clone https://github.com/rickadoo/xmr-stak-alpine.git xmr-stak
mkdir xmr-stak/build
cd xmr-stak/build
cmake .. -DCUDA_ENABLE=OFF -DOpenCL_ENABLE=OFF
make install

## Usage

xmr-stak -o <miningpoolurl:port> -u <wallet address> -p <password> --currency <cointomine>
  
# Example

xmr-stak -o xmr-usa.dwarfpool.com:8005 -u 46tDZpvT2VN9cwobmqdyykAW9VcaJfYNbDSoomLP54dkAbE3Yit2XUYgV5DKW9MR69NuUuqjYGavjfxr8zu7yd4r8oDr3yY -p x --currency monero
