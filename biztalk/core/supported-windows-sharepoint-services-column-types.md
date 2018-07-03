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
ms.openlocfilehash: 4f2f62709cf1d8c552d5f60c1ec9e7fbe627f8d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966723"
---
# <a name="supported-windows-sharepoint-services-column-types"></a>サポートされている Windows SharePoint Services 列の型
このトピックでは、Windows SharePoint Services アダプタでサポートされている Windows SharePoint Services 列の型について説明します。 これらの列の型の値は、メッセージで設定できます。  

> [!NOTE]
>  計算される列は、アダプタによって更新されません。  

## <a name="supported-types"></a>サポートされている型  
 サポートされている列の型を次の表に示します。  


|           UI の種類           | SharePoint オブジェクト モデルの型 |                    サンプル                    |                                                                                                                                                                                                                                                                            コメント                                                                                                                                                                                                                                                                            |
|-----------------------------|------------------------------|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     1 行のテキスト     |       SPFieldType.Text       |                 single line                  |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
|   複数行のテキスト    |       SPFieldType.Note       | 1 行目<br /><br /> 2 行目<br /><br /> line 3 |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
|      ドロップダウンの選択肢       |      SPFieldType.Choice      |                   ChoiceA                    |                                                                                                                                                                                                                                                 使用できる選択肢 (ChoiceA、ChoiceB、ChoiceC) のうちの ChoiceA です。                                                                                                                                                                                                                                                 |
|    オプション ボタンの選択肢     |      SPFieldType.Choice      |             #ChoiceB;#ChoiceC;#              |                                                                                                                                                                                                                 ChoiceB および ChoiceC が有効で、ChoiceA が無効です (使用できる選択肢は ChoiceA、ChoiceB、ChoiceC です)。 区切り記号として ";#" を使用します。                                                                                                                                                                                                                 |
|           数値            |      SPFieldType.Number      |                   123.456                    |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
| USD 通貨 (またはその他の通貨) |     SPFieldType.Currency     |                    100.00                    |                                                                                                                                                                                                                                                                              なし                                                                                                                                                                                                                                                                              |
|           Lookup            |      SPFieldType.Lookup      |                      1                       |                                                                                                                                                                                                                                                 この番号は参照先一覧内のアイテム識別子です。                                                                                                                                                                                                                                                  |
|            はい/いいえ (Yes/No)            |     SPFieldType.Boolean      |                      1                       |                                                                                                                                                                                                                                                                     1 = [はい]<br /><br /> 0 = いいえ                                                                                                                                                                                                                                                                     |
|    ハイパーリンクまたは画像     |       SPFieldType.URL        | http://www.microsoft.com、Microsoft Web サイト |                                                                                                                                                                                                                  URL と表示テキストは "," で区切っています。 「Microsoft Web サイト」テキストへのハイパーリンクになります http://www.microsoft.com                                                                                                                                                                                                                   |
|        日時        |     SPFieldType.DateTime     |             2005-02-11T10:05:04              | xs:dateTime の XML 標準によって定義されている DateTime です。 dateTime の形式は CCYY-MM-DDThh:mm:ss です。CC は世紀、YY は年、MM は月、DD は日を表します。オプションで負の値を表す負号 (-) が先頭に付いています。 負号を省略すると、正号 (+) が使用されます。 T は日付と時刻の区切り記号を表し、hh、mm、ss はそれぞれ時、分、秒を表します。 この表記では、直後に "Z" を付けると、UTC またはタイム ゾーンを表すことができます。 |

## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ハンドラーを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services アダプターのプロパティに関するリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md)