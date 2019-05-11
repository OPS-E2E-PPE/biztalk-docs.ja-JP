---
title: Windows SharePoint Services 列の型のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], supported column types
- Windows SharePoint Services adapters, supported column types
ms.assetid: 14992f52-9d18-4321-9152-83c8a37751bc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686f521f8a31974919e83487e1f2d403c8682155
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396864"
---
# <a name="supported-windows-sharepoint-services-column-types"></a>Windows SharePoint Services 列の型のサポート
このトピックでは、Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型について説明します。 メッセージには、これらの列型の値を設定できます。  

> [!NOTE]
>  計算列は、アダプターによっては更新されません。  

## <a name="supported-types"></a>サポートされている型  
 次の表では、サポートされている列の型について説明します。  


|           UI 型           | SharePoint オブジェクト モデルの種類 |                    サンプル                    |                                                                                                                                                                                                                                                                            コメント                                                                                                                                                                                                                                                                            |
|-----------------------------|------------------------------|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     1 行のテキスト     |       SPFieldType.Text       |                 1 つの行                  |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
|   複数行のテキスト    |       SPFieldType.Note       | 1 行目<br /><br /> 2 行目<br /><br /> 3 行目 |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
|      選択肢のドロップダウン       |      SPFieldType.Choice      |                   ChoiceA                    |                                                                                                                                                                                                                                                 使用できる選択肢 (ChoiceA、ChoiceB、ChoiceC) うちの choicea です。                                                                                                                                                                                                                                                 |
|    オプション ボタンの選択肢     |      SPFieldType.Choice      |             #ChoiceB; #ChoiceC; #              |                                                                                                                                                                                                                 ChoiceB および ChoiceC が有効になっている、ChoiceA が無効です (使用可能な選択肢は ChoiceA、ChoiceB、ChoiceC です)。 #、区切り記号として使用します。                                                                                                                                                                                                                 |
|           数値            |      SPFieldType.Number      |                   123.456                    |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
| USD 通貨 (またはその他) |     SPFieldType.Currency     |                    100.00                    |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
|           Lookup            |      SPFieldType.Lookup      |                      1                       |                                                                                                                                                                                                                                                 数は、参照先一覧内のアイテム識別子です。                                                                                                                                                                                                                                                  |
|            はい/いいえ (Yes/No)            |     SPFieldType.Boolean      |                      1                       |                                                                                                                                                                                                                                                                     1 = [はい]<br /><br /> 0 = いいえ                                                                                                                                                                                                                                                                     |
|    ハイパーリンクまたは画像     |       SPFieldType.URL        | [http://www.microsoft.com](http://www.microsoft.com) 、Microsoft Web サイト |                                                                                                                                                                                                                  URL と表示テキストは "," で区切っています。 「Microsoft Web サイト」テキストへのハイパーリンクになります http://www.microsoft.com                                                                                                                                                                                                                   |
|        日時        |     SPFieldType.DateTime     |             2005-02-11T10:05:04              | Xs:dateTime の XML 標準で定義されている日時。 DateTime のパターンは CCYY-MM-DDThh:mm:ss が CC は世紀、YY は年、MM を表す負の数を示す省略可能な先頭負 (-) 文字前に、日、月、および DD します。 負の文字は省略すると、正 (+) と見なされます。 T は日付/時刻の区切り記号と hh、mm、ss は 1 時間、分、および秒をそれぞれ表します. この表現は、"Z"を示す UTC またはタイム ゾーンを示すために、直後に可能性があります。 |

## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ハンドラーを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services アダプターのプロパティに関するリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md)