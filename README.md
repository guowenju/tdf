# tdf — TestDataFactory 测试数据工厂

用于快速构造测试数据与常用辅助函数（时间、随机、网络、路径、假数据）。

## 安装

```bash
pip install --pre tdf
```

## 快速上手

```python
from tdf import Rand, Faker, DateTime, Net, Paths

Rand.random_str(12)  # 随机字符串
Rand.random_email()  # 随机邮箱
Rand.random_url()  # 随机 URL

DateTime.parse_iso8601("2024-01-01T00:00:00Z")  # 解析 ISO8601
DateTime.to_timezone("2024-01-01T00:00:00Z", 8)  # 转换时区

Net.generate_ip_list(3)  # 生成 IPv4 列表
Net.ip_in_range("192.168.1.1", "192.168.1.0/24")

faker = Faker()
faker.profile(zh=True)  # 随机中文个人档案
```

## 开发与测试

```bash
uv sync --locked --group dev
uv run --no-sync pytest
uv build
```

### 代码质量检查

```bash
uv run --no-sync ruff check src tests
uv run --no-sync ruff format --check src tests
uv run --no-sync mypy
```
