在这个仓库中 https://github.com/ghostdragonzero/arceos_test 我直接修改了ixgbe的pid vid匹配参数来匹配igb网卡，并且通过修改axdriver到引用我自己的仓库。以此来实现替换ixgbe的目的。
https://github.com/ghostdragonzero/ixgbe_driver

拉取后可以直接执行
`make A=examples/httpserver PLATFORM=aarch64-qemu-virt LOG=debug SMP=2 NET=y FEATURES=driver-ixgbe NET_DEV=user run`
即可创建网页 http://localhost:5555/
`make A=examples/httpclient PLATFORM=aarch64-qemu-virt LOG=debug SMP=2 NET=y FEATURES=driver-ixgbe NET_DEV=user run`
即可看到
HTTP/1.1 200 OK
Server: nginx
Date: Fri, 20 Dec 2024 13:31:42 GMT
Content-Type: text/plain
Content-Length: 13
Connection: keep-alive
Access-Control-Allow-Origin: *
Cache-Control: no-cache, no-store, must-revalidate
