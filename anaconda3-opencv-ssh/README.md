# caffe-cuda-ssh
This deployment provides Caffe (CUDA) images with a enabled SSH service. The service is reachable via the defined port, the user is: root/root. Change the NVIDIA driver path / ports to your needs.

Mainly used for development via PyCharm Remote Interpreter.

Scale: kubectl scale deployment caffe-cuda-ssh --replicas=1

Useage example:
kubectl create -f deployment.yaml
ssh root@<node> -p 30001 (pw: root)

Pycharm: Setup remote interpreter and deployment via SFTP
Maybe required: Setup environment variables in pycharm:

PATH = /usr/local/nvidia/bin:/usr/local/cuda/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
LD_LIBRARY_PATH = /usr/local/nvidia/lib:/usr/local/nvidia/lib64
PYTHONPATH = /root/caffe/python:

Usage with Pubkey:
e.g. kubectl create secret generic ssh-key-secret --from-file=authorized_keys=/path/to/.ssh/id_rsa.pub