---
title: Functoid カテゴリ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029905e2-f01a-436a-b2ed-a364379c9cc5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d71180b97cbad95dfcb19798dd46bdc3b1a9057
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345253"
---
# <a name="functoid-categories"></a>Functoid カテゴリ
BizTalk の functoid は、使用目的に応じてカテゴリに分類されます。 たとえば、データベース functoid は実行時にデータベースからデータを抽出するために設計されていますが、数値演算 functoid は、数値演算を実行するために使用します。 カテゴリによって、BizTalk マッパーの functoid が表示されます、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。 

## <a name="categories--description"></a>カテゴリと説明
次の表の functoid カテゴリが表示されます、簡単なカテゴリについて説明し、該当するリファレンス ページへのリンクなど、各カテゴリの functoid の一覧が表示されます。  
  
|Functoid カテゴリ <br/><br/> カテゴリの説明|カテゴリの Functoid|  
|---|---|  
|**詳細設定** <br /><br /> 主にループ レコードと共に使用します。 任意のスクリプトを実行するために使用またはコードをコンパイルします。|Assert、インデックス、ループのイテレーション、一括コピー、Nil 値、レコードの数、スクリプティング、テーブルの抽出、テーブル値のマッピングにすると、値のマッピング (フラット化) をループします。|  
|**変換** <br /><br /> 使用して、ASCII および数値基本型間の変換します。|ASCII 文字の値の ASCII 文字、16 進数、8 進数|  
|**累積的です** <br /><br /> 平均および連結などのレコードをループで算術演算を実行するために使用します。|累積平均、累積的な連結、累積最大値、累積最小値、累積合計|  
|**[データベース]** <br /><br /> データベースからデータを抽出し、送信先インスタンス メッセージで使用するために使用します。|データベースを参照して、エラーが返される、メッセージの書式設定、アプリケーション ID の取得、アプリケーション値の取得、共通 ID の取得、共通値の取得、アプリケーション ID の削除、共通の ID 値抽出の設定|  
|**日付と時刻** <br /><br /> 現在の日付と時刻を取得し、差分を算出するを使用します。|日、日付、日付と時刻、時間を追加します。|  
|**論理** <br /><br /> さまざまなより大きい、論理的な実態などの論理操作を実行するために使用します。|Equal、Greater Than より大きいまたは Equal To、IsNil、小さい場合、論理数値、論理、論理 AND、日付検査、論理的な実体に等しいまたはそれよりも小さいいない、論理 OR、文字列の検査が等しくないです。|  
|**数学** <br /><br /> さまざまな加算や乗算などの算術演算を実行するために使用します。|絶対値、加算、除算、整数、最大値、最小値、剰余、減算、乗算、ラウンド、平方根|  
|**[指数]** <br /><br /> 指数演算、対数および三角関数などのさまざまな実行するために使用します。|10 ^ n、アーク タンジェント、底指定対数、常用対数、コサイン、自然指数関数、自然対数、サイン、タンジェント、X ^ Y|  
|**String** <br /><br /> さまざまなトリミングや連結などの文字列関数を実行するために使用します。|小文字、サイズ、文字列の連結、文字列の抽出、文字列の検索文字列を左、文字列左スペース削除、文字列、文字列右スペース削除、大文字|  
  
> [!NOTE]
>  Functoid の目的は、通常は、名前から明らかです。  
> 
> [!NOTE]
>  Microsoft に含まれているすべての functoid[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を除きインライン c# は、**データベース**functoid。  
  
## <a name="see-also"></a>参照  
 [基本 Functoid](../core/basic-functoids.md)   
 [高度な Functoid](../core/advanced-functoids.md)