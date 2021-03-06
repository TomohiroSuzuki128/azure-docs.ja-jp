---
title: Android から Windows Virtual Desktop に接続する - Azure
description: Android クライアントを使用して Windows Virtual Desktop に接続する方法。
services: virtual-desktop
author: heidilohr
ms.service: virtual-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: helohr
ms.openlocfilehash: 41b0c1ced9e66bd58d73683865b2c40afc16c5d3
ms.sourcegitcommit: c62a68ed80289d0daada860b837c31625b0fa0f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "73605850"
---
# <a name="connect-with-the-android-client"></a>Android クライアントに接続する

> 適用対象:Android 4.1 以降、Chrome OS 53 以降の Chromebook。

>[!NOTE]
> Android クライアントから Windows Virtual Desktop リソースにアクセスする機能は、現在プレビューで使用できます。

ダウンロード可能なクライアントを使用して、ご利用の Android デバイスから Windows Virtual Desktop リソースにアクセスできます。 Google Play ストアをサポートする Chromebook デバイスで Android クライアントを使用することもできます。 このガイドでは、Android クライアントを設定する方法について説明します。

## <a name="install-the-android-client"></a>Android クライアントをインストールする

開始するには、クライアントを[ダウンロード](https://play.google.com/store/apps/details?id=com.microsoft.rdc.android)して、ご利用の Android デバイスにインストールします。

## <a name="subscribe-to-a-feed"></a>フィードのサブスクライブ

管理者から提供されたフィードをサブスクライブして、ご利用の Android デバイスでアクセスできる管理対象リソースの一覧を取得します。

フィードをサブスクライブするには:

1. 接続センターで **+** をタップしてから、 **[リモート リソース フィード]** をタップします。
2. **[Feed URL]\(フィード URL\)** フィールドにフィード URL を入力します。 フィード URL には、URL またはメール アドレスのいずれかを指定できます。
   - URL を使用する場合は、管理者によって付与されたものを使用します (通常、<https://rdweb.wvd.microsoft.com>)。
   - 電子メールを使用するには、メール アドレスを入力します。 管理者がそのようにサーバーを構成した場合、このクライアントにより、メール アドレスに関連付けられている URL が検索されます。
3. **[次へ]** をタップします。
4. メッセージが表示されたら、資格情報を入力します。
   - **[User name]\(ユーザー名\)** 。リソースへのアクセス許可を持つユーザー名を指定します。
   - **[パスワード]** には、ユーザー名に関連付けられているパスワードを指定します。
   - 管理者が追加の要素を指定するように認証を構成した場合、そのように求められることもあります。

登録後は、接続センターにリモート リソースが表示されます。

フィードをサブスクライブすると、フィードのコンテンツが自動で定期的に更新されます。 管理者によって行われる変更に基づいて、リソースが追加、変更、または削除されることがあります。

## <a name="next-steps"></a>次の手順

Android クライアントの使用方法の詳細については、「[Android クライアントの概要](https://docs.microsoft.com/windows-server/remote/remote-desktop-services/clients/remote-desktop-android)」を参照してください。
