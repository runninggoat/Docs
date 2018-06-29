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
