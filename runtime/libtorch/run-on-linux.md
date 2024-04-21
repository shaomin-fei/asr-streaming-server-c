1. get into libtorch folder
2. mkdir build
   cd build
    cmake ..
    cmake --build .
3. get into libtorch folder, create a .sh file, e.g:
create run.sh with contents:

export GLOG_logtostderr=1
export GLOG_v=2
model_dir=/home/fsm/Desktop/ml/asr-integration-pretrained-models/asr-runtime/
./build/bin/websocket_server_main \
    --port 10086 \
    --chunk_size 16 \
    --model_path $model_dir/final.zip \
    --unit_path $model_dir/units.txt 2>&1 | tee server.log

4. open a terminal, get into libtorch folder, run
bash run.sh