apt-get install git-flow

git flow init 

git flow feature start python_grpc

<!--more-->

 pip install grpcio-tools

  python -m grpc_tools.protoc -I../../protos --python_out=. --grpc_python_out=. ../../protos/route_guide.proto

  https://danielkummer.github.io/git-flow-cheatsheet/