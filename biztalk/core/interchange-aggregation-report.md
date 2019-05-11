---
title: インターチェンジの集計レポート |Microsoft Docs
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
ms.openlocfilehash: df8163506f3b71379038e8beb82bc8f9f2297249
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381946"
---
# <a name="interchange-aggregation-report"></a>インターチェンジの集計レポート
このレポートは、同じ EDI エンコードの種類、送信者パーティ、受信者パーティ、および方向を共有する EDI インターチェンジの数を示す 1 つのレコードを提供します。 このレポートでは、個別のインターチェンジの詳細は提供されません。  
  
 [グループ ハブ] ページの下部にインターチェンジの集計レポート リンクをクリックしてこの状態レポートを表示、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="fields-in-the-status-report"></a>状態レポート内のフィールド  
 インターチェンジの集計レポートには、各レコードに対して次の情報が表示されます。  
  
- 同じ EDI エンコードの種類、送信者パーティ、受信者パーティ、および方向を共有するインターチェンジの数のカウント  
  
- レコード内の各インターチェンジの送信者パーティ  
  
- レコード内の各インターチェンジの受信者パーティ  
  
- 方向 (受信または送信)、レコード内の各インターチェンジの  
  
- 日付と時刻を時間の範囲内の最初のインターチェンジが送信または受信 (最も早い開始日付/時刻)  
  
  > [!NOTE]
  >  受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。 日付が 75 未満である場合は、20YY として表示されます。  
  > 
  >  たとえば、インターチェンジを受信した場合を含む最も早い開始 ISA09 の値の日付/時刻は、11/13/1999 としてレポートに表示されます。  
  
- 日付と時刻を時間の範囲の最後のインターチェンジが送信または受信 (最新が終了した日付/時刻)  
  
- EDI エンコードのレコード内の各インターチェンジの種類  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状態レポートのクエリ式のフィールド  
 表示されるデータを決定するクエリ式のフィールドを変更することで、インターチェンジの集計レポートをカスタマイズできます。 使用できるフィールドは以下のとおりです。  
  
|||||  
|-|-|-|-|  
|クエリ式のフィールド|有効な演算子|潜在的な値|既定で含まれますか。|  
|検索|[等しい]|インターチェンジの集計レポート|指定あり (必須)|  
|インターチェンジの日時|[以下]<br /><br /> [以上]|特定の日時<br /><br /> [今日]<br /><br /> 昨日|はい<br /><br /> 注:1 回と、クエリ式に 2 回含めることができます-演算子、値が高い 1 回の演算子は、範囲を指定します。|  
|[最大一致数]|[等しい]|整数 (既定値 50)|はい|  
|Direction|[等しい]|すべて (既定)<br /><br /> Receive<br /><br /> Send|いいえ|  
|受信者パーティ名|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名 (AN 文字列)|いいえ|  
|送信者パーティ名|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名 (AN 文字列)|いいえ|  
|状態|[等しい]<br /><br /> 等しくないです。|受理<br /><br /> 受理 (ただしエラーが発生)<br /><br /> 送信済み<br /><br /> All<br /><br /> 確認が必要<br /><br /> 確認は不要<br /><br /> 拒否されました。|いいえ|