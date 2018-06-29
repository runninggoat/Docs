# IPFS command

Format of the glossary
> * file hash -- QmZ1fH7nFpxN3jhtb5wSrEnSNxb435ShyYtZhudwKksDXy
> * path hash -- QmdL9t1YP99v4a2wyXFYAQJtbD9zKnPrugFLQWXBXb82sn
> * ref -- 

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
