---
title: 例外の原因 |Microsoft Docs
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
ms.openlocfilehash: 71c6bf04421ca538400545239711637990e3adf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357595"
---
# <a name="causes-of-exceptions"></a>例外の原因
次の方法で、オーケストレーション内で例外を生成できます。  
  
-   によって、**例外のスロー**図形で、すぐに、無条件で例外をスローします。 制御が渡される、**例外のスロー**適切な例外ハンドラーに直接図形。  
  
-   実行時間の長いトランザクションで期限切れにならない、タイムアウトします。 定義済みのシステム例外:**Microsoft.XLANG.BaseTypes.TimeOutException**: この場合にスローされます。  
  
-   その他のトランザクション障害が発生しています。 ランタイム エンジンは、これらのエラー Microsoft.XLANG.BaseTypes.PersistenceException などのシステム定義メッセージをスローします。  
  
-   ユーザー コードの例外。 オーケストレーション内では、外部のユーザー コードへの呼び出しが行われた、ときに呼び出される共通言語ランタイム クラスは例外をスローできます。 これらの例外は、ユーザー コードで処理されない場合最終的に伝達されるをユーザー コードへの呼び出しが行われるスコープにします。  
  
-   いくつかその他のシステム例外によって (永続化エラー、型のローダーの例外などの別の .NET またはシステム例外またはデータ変換エラーなど)。  
  
> [!NOTE]
>  内に、例外型のローダーの例外がスローされると、キャッチされない可能性があります、**例外のキャッチ**同じブロック**スコープ**図形。 これは、ため、例外が、BizTalk オーケストレーション プロセスからではなく、型のローダーからがあります。 そのため、制御フローの BizTalk のルールに従っていません。  
  
-   実行を停止する前後のスコープ内の兄弟分岐します。 各分岐に Microsoft.XLANG.BaseTypes.ForcedTerminationException がここでは、スローされ、それぞれに例外ハンドラーを追加する場合があります。 このような例外ハンドラーからその例外を再スローすることはできません。 また他の種類の例外をスローしよう必要があります。  
  
-   外部のメッセージの受信によっては、エラーを示すです。  
  
## <a name="see-also"></a>参照  
 [エラー メッセージ](../core/fault-messages.md)   
 [例外](../core/exceptions.md)