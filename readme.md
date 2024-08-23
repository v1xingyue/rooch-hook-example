# rooch-hook example

## 1. 安装签名器

```shell
cargo install --git https://github.com/v1xingyue/rooch-hook.git --branch  main
```

## 2. 初始化

```shell
sign-tool init --address $your_rooch_hex_address
```

## 3. 配置 hook

```shell
cat > .git/hooks/prepare-commit-msg << 'EOF'
#!/bin/bash

COMMIT_MSG_FILE=$1
CUSTOM_SIGNATURE=$(sign-tool sign -f $COMMIT_MSG_FILE)

# Append the custom signature to the commit message
echo -e "\n$CUSTOM_SIGNATURE" >> "$COMMIT_MSG_FILE"
EOF
```

## 4. 提交 commit

## 5. 提交 PR

## 6. 等待合并， 查看 rooch-hook commits

## 7. 检查 rooch-hook commits

[https://rooch-hook.vercel.app/commits/0x59a2384059899f8458d0febadf68c56c7380e4b9a1bfb8d37ffc7d4568640d99](https://rooch-hook.vercel.app/commits/0x59a2384059899f8458d0febadf68c56c7380e4b9a1bfb8d37ffc7d4568640d99)
