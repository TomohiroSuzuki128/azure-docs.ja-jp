---
title: Azure Data Factory のマッピング データ フローのパラメーター
description: データ ファクトリのパイプラインからマッピング データ フローをパラメーター化する方法について学習します
author: kromerm
ms.author: makromer
ms.service: data-factory
ms.topic: conceptual
ms.date: 06/10/2019
ms.openlocfilehash: 0a1051d67bf45e96f82833ef8190008204cdc90b
ms.sourcegitcommit: 38251963cf3b8c9373929e071b50fd9049942b37
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "72387547"
---
# <a name="mapping-data-flow-parameters"></a>マッピング データ フローのパラメーター



Azure Data Factory の Mapping Data Flow では、パラメーターの使用をサポートします。 ご利用のデータ フローの定義内でパラメーターを定義できます。その後、これは自分の式全体で使用することができます。 パラメーター値は、データ フローの実行アクティブティ経由でパイプラインを呼び出すことにより設定できます。 データ フロー アクティビティの式で値を設定するには、次の 3 つのオプションがあります。

* パイプラインの制御フローの式を使用して動的な値を設定する
* データ フロー式の言語を使用して動的な値を設定する
* いずれかの式の言語を使用して静的なリテラル値を設定する

この機能を使用して、ご利用のデータ フローを汎用的かつ柔軟性があり、再利用可能なものにします。 3 つのパラメーターを使って、データ フローの設定と式をパラメーター化することができます。

> [!NOTE]
> パイプラインの制御フローの式を使用するには、ご利用のデータ フローのパラメーターは文字列型である必要があります。

## <a name="create-parameters-in-mapping-data-flow"></a>マッピング データ フローでパラメーターを作成する

ご利用のデータ フローにパラメーターを追加するには、データ フローのキャンバスの空白部分をクリックして、全般プロパティを表示します。 設定ウィンドウで、[パラメーター] という名前のタブが表示されます。 [新規] ボタンをクリックして、新しいパラメーターを作成します。 パラメーターごとに、名前を割り当て、型を選択し、必要に応じて既定値を設定する必要があります。

![データ フローのパラメーターを作成する](media/data-flow/create-params.png "データ フローのパラメーターを作成する")

パラメーターは任意のデータ フロー式で使用することができます。 パラメーターは $ で始まり、変更することはできません。 [パラメーター] タブの下に、式ビルダー内で利用可能なパラメーターの一覧が表示されます。

![データ フロー パラメーター式](media/data-flow/parameter-expression.png "データ フロー パラメーター式")

## <a name="use-parameters-in-your-data-flow"></a>データ フローでパラメーターを使用する

* 変換式内でパラメーター値を使用できます。 式ビルダーの [パラメーター] タブの下にパラメーターの一覧が表示されます。 ![データ フローのパラメーターを使用する](media/data-flow/params9.png "Uデータ フローのパラメーターを使用する")

* パラメーターは、自分のソースおよびシンクの変換設定に動的な値を構成するためにも使用されます。 構成フィールド内をクリックすると、[動的なコンテンツの追加] リンクが表示されます。 そこをクリックすると、パラメーターを使用して動的な値を使用できる式ビルダーに移動します。 ![データ フローの動的なコンテンツ](media/data-flow/params6.png "Dデータ フローの動的なコンテンツ")

## <a name="set-mapping-data-flow-parameters-from-pipeline"></a>パイプラインからマッピング データ フローのパラメーターを設定する

パラメーターを使ってデータ フローを作成したら、データ フローの実行アクティブティを使用してパイプラインからそれを実行できます。 パイプラインのキャンバスにアクティビティを追加した後、アクティビティの [パラメーター] タブに利用可能なデータ フローのパラメーターが提示されます。

![データ フロー パラメーターの設定](media/data-flow/parameter-assign.png "データ フロー パラメーターの設定")

パラメーターのデータ型が文字列の場合、テキスト ボックスをクリックしてパラメーター値を設定するときに、パイプラインまたはデータ フロー式のいずれかを入力することを選択できます。 パイプライン式を選択した場合、パイプラインの式パネルが表示されます。 `'@{<expression>}'` を使用して、必ず文字列補間の構文内にパイプライン関数を含めてください。たとえば、次のようになります。

```'@{pipeline().RunId}'```

パラメーターが文字列型でない場合、常に Data Flow の式ビルダーが提示されます。 ここで、パラメーターのデータ型に一致させたい任意の式またはリテラル値を入力できます。 式ビルダーからのデータ フロー式とリテラル文字列の例を以下に示します。

* ```toInteger(Role)```
* ```'this is my static literal string'```

各マッピング データ フローには、パイプラインとデータ フロー式のパラメーターの任意の組み合わせを含めることができます。 

![データ フロー パラメーターのサンプル](media/data-flow/parameter-example.png "データ フロー パラメーターのサンプル")



## <a name="next-steps"></a>次の手順
* [データ フローの実行アクティビティ](control-flow-execute-data-flow-activity.md)
* [制御フローの式](control-flow-expression-language-functions.md)
