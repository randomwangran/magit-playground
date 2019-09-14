Dear rg maintainer:

I recently find a strange behavior using rg to search a string with in a folder.

The folder structure is this (or [[https://github.com/randomwangran/magit-playground/commit/16e4eb3d03ca9358f1ad1bbd2a30e42f4c4b4dc7][this minimal example]]):

```
xx-org
|
|-- dummy-A
|-- dummy-A.org
|-- dummy-B
|-- dummy-B.org
|-- dummy-C
`-- dummy-C.org
```

In some of these dummy files, it contains a string: `:leila:'.


If I put `xx-org' somewhere in my file system, for example:


e:\xx-org


Then, typing: `rg :leila: e/xx-org`, I can get:

```
E:\xx-org>rg :leila: e:/xx-org

e:/xx-org\dummy-A.org
4::leila:

e:/xx-org\dummy-B.org
4::leila:

e:/xx-org\dummy-C.org
4::leila:


```

If xx-org is under `c:\xx-org`, positive result.


```
C:\>rg :leila: c:/xx-org

c:/xx-org\dummy-A.org
4::leila:

c:/xx-org\dummy-C.org
4::leila:

c:/xx-org\dummy-B.org
4::leila:
```

And again in `c:\User\xx-org'


```
C:\>rg :leila: c:/Users/xx-org

c:/Users/xx-org\dummy-A.org
4::leila:

c:/Users/xx-org\dummy-B.org
4::leila:

c:/Users/xx-org\dummy-C.org
4::leila:
```


However, if I put `xx-org` in the following path:

c:\User\user\xx-org

No result.

```
C:\>rg :leila: c:/Users/user/xx-org

C:\>

```

I was wondering what is the cause of such behavior? Can anyone help me
out of this issue?


Thanks,

Ran





Extra info
============
rg --version
ripgrep 11.0.1 (rev 344b423da5)
-SIMD -AVX (compiled)
+SIMD +AVX (runtime)

OS Name	Microsoft Windows 7 Ultimate
Version	6.1.7601 Service Pack 1 Build 7601
