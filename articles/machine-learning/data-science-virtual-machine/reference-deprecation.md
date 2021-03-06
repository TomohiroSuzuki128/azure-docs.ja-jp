---
title: 'リファレンス: DSVM イメージの非推奨'
description: Azure Data Science Virtual Machine (DSVM) に影響する非推奨の詳細
author: gvashishtha
ms.service: machine-learning
ms.subservice: data-science-vm
ms.author: gopalv
ms.date: 10/14/2019
ms.topic: reference
ms.openlocfilehash: 4968ac08b75141ed84994ca287215a34728232c4
ms.sourcegitcommit: 1d0b37e2e32aad35cc012ba36200389e65b75c21
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72333444"
---
# <a name="reference-deprecation-of-dsvm-images"></a>リファレンス: DSVM イメージの非推奨

以下では、Azure Data Science Virtual Machine の今後の非推奨化に対処するための推奨事項について説明します。

## <a name="windows-2012-migrating-data-disks"></a>Windows 2012: データ ディスクの移行

Windows 2012 DSVM イメージのサポートは、2019 年 11 月 5 日に終了します。 既存の Windows 2012 DSVM から Windows 2016 DSVM にデータ ディスクを移行するには、次の手順を行います。

1. [こちら](./provision-vm.md#create-your-dsvm)に示されている手順に従って、新しい Windows 2016 DSVM を作成します。
1. [こちらの手順](../../virtual-machines/windows/detach-disk.md)を使用して、Windows 2012 イメージから既存のデータ ディスクをデタッチします。
1. [こちらの手順](../../virtual-machines/windows/attach-disk-ps.md#attach-an-existing-data-disk-to-a-vm)を使用して、前のステップのディスクを Windows 2016 イメージにアタッチします。
