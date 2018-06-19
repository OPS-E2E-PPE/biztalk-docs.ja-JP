---
title: 例外の原因 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, errors
- errors, orchestrations
- errors, causes
ms.assetid: b0422382-d034-4c58-87c6-fc269dbbfe43
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9006234d71751078269e5a88559839fdadd91e91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232466"
---
# <a name="causes-of-exceptions"></a>例外の原因
次のような場合、オーケストレーション内で例外が生成されることがあります。  
  
-   によって、**例外のスロー**図形、直ちに無条件で例外をスローします。 制御が渡される、**例外のスロー**適切な例外ハンドラーに直接図形です。  
  
-   長時間トランザクションで、タイムアウトが超過した場合。 定義済みのシステム例外 —**Microsoft.XLANG.BaseTypes.TimeOutException**— この場合にスローされます。  
  
-   その他のトランザクション エラーが発生した場合。 これらのエラーには、Microsoft.XLANG.BaseTypes.PersistenceException などのシステム定義のメッセージがランタイム エンジンによりスローされます。  
  
-   ユーザー コードの例外が発生した場合。 オーケストレーション内で外部のユーザー コードを呼び出したとき、呼び出された共通言語ランタイム クラスが例外をスローすることがあります。 こうした例外がユーザー コード内で処理されないと、最終的には、ユーザー コードを呼び出したスコープまで例外が反映されます。  
  
-   その他のシステム例外が発生した場合 (永続化エラー、型のローダーの例外などの .NET またはシステム例外、データ変換エラーなど)。  
  
> [!NOTE]
>  内に、例外型のローダーの例外がスローされると、キャッチされない場合があります、**例外のキャッチ**同じブロック**スコープ**図形です。 これは、例外が、BizTalk オーケストレーション プロセスではなく型のローダーからスローされるためです。 よって、BizTalk の制御フローのルールが適用されません。  
  
-   前後のスコープ内の兄弟分岐によって実行が停止された場合。 この場合、各分岐に Microsoft.XLANG.BaseTypes.ForcedTerminationException がスローされるため、それぞれに例外ハンドラーを追加することをお勧めします。 このような例外ハンドラーでは、その例外を再スローできません。また、他の種類の例外をスローしようとしないでください。  
  
-   エラーを示す外部メッセージを受信した場合。  
  
## <a name="see-also"></a>参照  
 [エラー メッセージ](../core/fault-messages.md)   
 [例外](../core/exceptions.md)