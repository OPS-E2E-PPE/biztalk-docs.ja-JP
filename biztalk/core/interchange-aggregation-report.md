---
title: インターチェンジの集計レポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4619e8d0-9e9e-4d19-a67a-ac1058a0579b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac86a43bc74d862aa856a18f1564b03bc7f4e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257882"
---
# <a name="interchange-aggregation-report"></a>インターチェンジの集計レポート
このレポートでは、同じ EDI エンコードの種類、送信者パーティ、受信者パーティ、および方向を共有する EDI インターチェンジの数を示すレコードが 1 つ提供されます。 このレポートには、個別のインターチェンジの詳細情報は含まれません。  
  
 この状態レポートを表示するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで [グループ ハブ] ページの最下部にある [インターチェンジの集計レポート] リンクをクリックします。  
  
## <a name="fields-in-the-status-report"></a>状態レポート内のフィールド  
 インターチェンジの集計レポートには、各レコードに関する次の情報が表示されます。  
  
-   同じ EDI エンコードの種類、送信者パーティ、受信者パーティ、および方向を共有するインターチェンジの数  
  
-   レコード内の各インターチェンジの送信者パーティ  
  
-   レコード内の各インターチェンジの受信者パーティ  
  
-   レコード内の各インターチェンジの方向 (受信または送信)  
  
-   時間範囲内の最初のインターチェンジが送信または受信された日付と時刻 (初回開始日時)  
  
    > [!NOTE]
    >  受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。 日付が 75 未満である場合は、20YY として表示されます。  
    >   
    >  たとえば、インターチェンジを受信した場合を値が 991113 ISA09、最も早い開始の日付/時刻は 11/13/1999 としてレポートに表示されます。  
  
-   時間範囲内の最後のインターチェンジが送信または受信された日付と時刻 (前回終了日時)  
  
-   レコード内の各インターチェンジの EDI エンコードの種類  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状態レポートのクエリ式のフィールド  
 表示されるデータを指定するクエリ式のフィールドを変更することにより、インターチェンジ集計レポートをカスタマイズできます。 使用できるフィールドは以下のとおりです。  
  
|||||  
|-|-|-|-|  
|クエリ式のフィールド|有効な演算子|潜在的な値|既定で含まれますか。|  
|検索|[等しい]|インターチェンジの集計レポート|指定あり (必須)|  
|インターチェンジの日時|[以下]<br /><br /> [以上]|特定の日時<br /><br /> [今日]<br /><br /> 昨日|はい<br /><br /> 注: は小で 1 回、クエリ式に 2 回含めることが-演算子と、大きい値が 1 回よりも-演算子は、範囲を指定します。|  
|[最大一致数]|[等しい]|整数 (既定値 50)|はい|  
|Direction|[等しい]|すべて (既定)<br /><br /> Receive<br /><br /> Send|不可|  
|受信者パーティ名|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名 (AN 文字列)|不可|  
|送信者パーティ名|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名 (AN 文字列)|不可|  
|[状態]|[等しい]<br /><br /> 等しくないです。|受理<br /><br /> 受理 (ただしエラーが発生)<br /><br /> 送信済み<br /><br /> すべて<br /><br /> 確認が必要<br /><br /> 確認は不要<br /><br /> 拒否しました|不可|