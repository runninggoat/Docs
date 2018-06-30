# IPFS command

Startup the IPFS container
===
```
docker run -d --name ipfs_host -v ~/ipfs_staging:/export -v ~/ipfs_data:/data/ipfs -p 4001:4001 -p 127.0.0.1:8080:8080 -p 127.0.0.1:5001:5001 ipfs/go-ipfs:latest
```

Command in IPFS
===
Format of the glossary
---
> * file hash -- QmZ1fH7nFpxN3jhtb5wSrEnSNxb435ShyYtZhudwKksDXy
> * path hash -- QmdL9t1YP99v4a2wyXFYAQJtbD9zKnPrugFLQWXBXb82sn
> * ref -- 

Commands
---
Add file to IPFS
```
ipfs add <file>
```

Add folder to IPFS recursively
```
ipfs add -r <path>
```

List the folder's file and folder inside it
```
ipfs ls <path hash>
```

Print the content of the file
```
ipfs cat <file hash>
```

Download the object with hash address
```
ipfs get <file/path hash> -o <output path>
```

Unpin object
```
ipfs pin rm -r <file/path hash>
```

After unpinning the object recursively, we can use garbage collection to remove the content in IPFS
```
ipfs repo gc
```
***Attention! This garbage collection can only work on the node you owned, if other node had view the content you are about to remove, they will be cached on their node, and if they pin the content, the content will be unremovable.***

Through web browser
---
To inspect the content you have added in your own node, type the address in your browser.
```
http://localhost:8080/ipfs/<file/path hash>
```
or curl in your terminal
```
http://localhost:8080/ipfs/<file/path hash>
```
***Remember the 8080 port you had exposed? The 8080 port is used for HTTP gateway!***

Merkle DAGs
---
This is the core concept of IPFS. IPFS stores big binary file in a series of sub-blocks which refered by the parent block to form a Merkle tree. For example, if you store a 800Kb image, the image will be stored in separate blocks. When you use ```ipfs cat``` to read the content of the picture, you are reading the content of the root node wich content is the join of the whole sub-blocks.
