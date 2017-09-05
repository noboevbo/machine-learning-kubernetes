# caffe-cuda-ssh
This deployment provides Caffe (CUDA) images with a enabled SSH service. The service is reachable via the defined port, the user is: root/root. Change the NVIDIA driver path / ports to your needs.

Mainly used for development via PyCharm Remote Interpreter.

Scale: kubectl scale deployment caffe-cuda-ssh --replicas=1
