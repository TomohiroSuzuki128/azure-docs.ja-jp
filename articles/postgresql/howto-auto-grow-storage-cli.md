---
title: ストレージを自動拡張する - Azure CLI - Azure Database for PostgreSQL - 単一サーバー
description: この記事では、Azure Database for PostgreSQL - 単一サーバーで Azure CLI を使用して、ストレージを自動拡張するように構成する方法について説明します。
author: ambhatna
ms.author: ambhatna
ms.service: postgresql
ms.topic: conceptual
ms.date: 8/7/2019
ms.openlocfilehash: b0dc2fbb168d9325439ee18a227f71a3b88ef9c8
ms.sourcegitcommit: 6bb98654e97d213c549b23ebb161bda4468a1997
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74767945"
---
# <a name="auto-grow-azure-database-for-postgresql-storage---single-server-using-the-azure-cli"></a>Azure CLI を使用して Azure Database for PostgreSQL ストレージ - 単一サーバーを自動拡張する
この記事では、ワークロードに影響を与えることなく拡張されるように Azure Database for PostgreSQL サーバーのストレージを構成する方法について説明します。

[ストレージの上限に到達](https://docs.microsoft.com/azure/postgresql/concepts-pricing-tiers#reaching-the-storage-limit)したサーバーは、読み取り専用に設定されます。 プロビジョニングされたストレージが 100 GB 未満のサーバーに対してストレージの自動拡張が有効にされている場合、空きストレージがプロビジョニングされたストレージの 1 GB または 10% のどちらか大きい方を下回ると、プロビジョニングされたストレージ サイズが 5 GB 単位ですぐに拡張されます。 プロビジョニングされたストレージが 100 GB を超えるサーバーの場合、空きストレージ領域がプロビジョニングされたストレージ サイズの 5% を下回ると、プロビジョニングされたストレージ サイズが 5% 単位で増加します。 [こちら](https://docs.microsoft.com/azure/postgresql/concepts-pricing-tiers#storage)で指定されているストレージの上限が適用されます。

## <a name="prerequisites"></a>前提条件
このハウツー ガイドを完了するには、次が必要です。
- [Azure Database for PostgreSQL サーバー](quickstart-create-server-database-azure-cli.md)

[!INCLUDE [cloud-shell-try-it.md](../../includes/cloud-shell-try-it.md)]

> [!IMPORTANT]
> このガイドで説明する方法では、Azure CLI バージョン 2.0 以降を使う必要があります。 バージョンを確認するには、Azure CLI コマンド プロンプトで「`az --version`」と入力します。 インストールまたはアップグレードする必要には、「[Azure CLI のインストール]( /cli/azure/install-azure-cli)」をご覧ください。

## <a name="enable-postgresql-server-storage-auto-grow"></a>PostgreSQL サーバー ストレージの自動拡張を有効にする

次のコマンドを使用すると、既存のサーバー上でサーバーの自動拡張ストレージが有効にされます。

```azurecli-interactive
az postgres server update --name mydemoserver --resource-group myresourcegroup --auto-grow Enabled
```

次のコマンドを使用して、新しいサーバーの作成時にサーバーの自動拡張ストレージを有効にします。

```azurecli-interactive
az postgres server create --resource-group myresourcegroup --name mydemoserver  --auto-grow Enabled --location westus --admin-user myadmin --admin-password <server_admin_password> --sku-name GP_Gen5_2 --version 9.6
```

## <a name="next-steps"></a>次の手順

[メトリックに関するアラートを作成する方法](howto-alert-on-metric.md)について学習します。