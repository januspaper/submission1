## Janus Paper Repository and Code Disclosure

#### Running the zero knowledge opening

Jump into the folder `gnark_zkp` and run `go mod init gnark_zkp`, then run `go mod tidy` and then run a sample exection of the opening algorithm as `go run main.go -debug -tls13-zkopen -byte-size 256 -iterations 1`

#### Running the 2PC circuits

The circuits are in the location ``.
Inside the 2pc circuit files, you find the commands of the garbler and evaluator and TLS 1.3 sample values that are used for the verification of the circuit.
An example execution of a circuit is as follows. Jump with each terminal into the folder `2pc_circuit/tls_mpc/garbled` and first execute `go build .`. Then, take one terminal and run the command `MPCLDIR=./../../ ./garbled -e -v -i 0x677f7ff26ac202469e1a2d39dc001c5e7fcfb1f967a3cb4affa51185facc57ac,0x002012746c7331332073206873207472616666696320825e4f79bbcb0e8adb287cac19c378145b7d6c465734422da6882463eadc905701,0x00200d746c733133206465726976656420e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b85501,0x002012746c7331332073206170207472616666696320803fe80818374bc995571054979e54a316f266b4908ed43f5df4752bdef093b801,0x002012746c7331332063206170207472616666696320803fe80818374bc995571054979e54a316f266b4908ed43f5df4752bdef093b801,0x000c08746c7331332069760001,0x001009746c733133206b65790001 examples/tls13_hvzk_total_v2.mpcl`, then take another terminal and run the command `MPCLDIR=./../../ ./garbled -v -i 0xffffffff00000001000000000000000000000000ffffffffffffffffffffffff,0xfbe470a4a1e11bbaa2ebb9da082924f99a20681e5feed0000e2d2b5e613d22df,0x6f2615a108c702c5678f54fc9dbab69716c076189c48250cebeac3576c3611ba,0x7691bca4c1a92ffc70efe68a178d928540f47254512c290693fbc2a8c28ab59c,0x9b89f7120fe41972a4e81f2e63453807,0x895b8c63da8da17e9d6d30c62f09d6f5,0xf8895999038a3cb1169a882ebba33ca5,0xf0cecf8cdd4452c1f77a297cff13a605,0x51f870d025adaf98478f28d6abd81ca7,0x45123ceef731619582d1570c31a38724,0x4647eb76ffd794580046acf096d6b7a2,0x2222115555532db2e3bd2a8a examples/tls13_hvzk_total_v2.mpcl`.
All files which start with tls13 have been generated and used to evaluate the paper under submission.

#### ECTF

The EC2F code is provided in another folder called `ectf`. We used the cipher suite `TLS_AES_128_GCM_SHA256` of the Golang `crypto/tls` library to generate the inputs.

