# 模板说明

这3个模板是现代且成熟的配置模板，可以作为实际应用的配置。

## config.json

这个文件是服务端的配置文件，里面需要的修改有：

- id: 这个ID可以说是用户的唯一标识, 用`xray uuid`生成
- email: 随便填一个字符串，是不是email格式都无所谓，这个email仅仅对应日志中出现的名字。
- privateKey: 这是服务端的私钥，需要通过`xray x25519`生成。注意生成后privateKey,password,hash32要对应。
- shortIds: 这个是防侦查时需要用到的ID，用`openssl rand -hex 8`生成

注意private key和对应的password，**总共只需要一份**。id, email, shortId, **每个用户需要一份独立的**。

## client-config.json

这个文件是xray-core作为客户端启动时的配置文件，里面需要修改的有:

- address：你的服务器IP或者域名
- password: 和上面private key对应的password
- id: 用户的唯一标识跟服务端的配置的ID要对齐
- shortId：对应的shortId，也出现在服务端的配置里

## clash-profile.yaml

这个文件是客户端clash的配置文件，所有Mihomo内核的clash客户端都可以用同一份(clash Verge Rev, clash Mi, clash Meta, etc)

这个文件需要改的地方有

- server: 你服务器的IP或者域名
- uuid: 对应上面的ID
- public-key: 对应上面的Password
- short-id: 对应上面的shortId

