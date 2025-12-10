# Doppler Test Project

这是一个用于测试 Doppler 和 GitHub CI/CD 的简单项目。

## 项目结构

- `apps/p1/`: 第一个应用，打印 VALUE_P1 环境变量
- `apps/p2/`: 第二个应用，打印 VALUE_P2 环境变量

## 部署流程

1. 推送代码到 main/master 分支会触发部署
2. 检测文件变化，只部署有变化的应用
3. 使用 Doppler 获取环境变量
4. 部署完成后发送邮件通知

## 需要配置的 GitHub Secrets

- `DOPPLER_TOKEN`: Doppler API token
- `EMAIL_USERNAME`: 邮件发送者用户名
- `EMAIL_PASSWORD`: 邮件发送者密码
- `NOTIFICATION_EMAIL`: 接收通知的邮箱地址

## 本地运行

```bash
# 安装依赖
pnpm install

# 运行 P1
VALUE_P1=test1 pnpm run deploy:p1

# 运行 P2
VALUE_P2=test2 pnpm run deploy:p2
```