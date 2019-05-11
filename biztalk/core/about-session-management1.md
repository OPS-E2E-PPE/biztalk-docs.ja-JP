---
title: セッション Management1 について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1848619-d97a-4f1e-ba94-59861bd7aedf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aac0705bc4c9b90b73249a0806aa4b0a8b1aa48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362313"
---
# <a name="about-session-management"></a>セッション管理について
Microsoft BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld サーバーへの呼び出しを送信する接続セッションを作成します。 呼び出しが終了すると、セッションは、後続の呼び出しで再利用するプールに格納されます。 アダプターは、JD Edwards OneWorld サーバーへの同時呼び出しを処理する複数の接続セッションを作成します。 プールが不要になったセッションを削除する定期的にクリーンアップされます。  
  
 Microsoft BizTalk Adapter for JD Edwards OneWorld は、呼び出しする必要があります、同じセッション内で発生したときに制御する 2 つのメッセージ コンテキスト プロパティを提供します。  
  
|名前|型|既定|  
|----------|----------|-------------|  
|JDE します。セッション Id|Int|0|  
|JDE します。ReserveSession|boolean|false|  
  
 セッション管理は、ビジネス関数には、JD Edwards OneWorld サーバーを 1 回の呼び出しが必要な場合に必要ではありません。 アダプターが使用可能なセッションを選択し、セッションは後続の呼び出しでも使用できます。 このシナリオで、既定値は適切なメッセージ コンテキスト プロパティを無視できます。  
  
 一部の JD Edwards OneWorld 機能が、JD Edwards OneWorld サーバーを複数回呼び出す必要があります。たとえば、SalesOrder の作成です。 BeginDoc の最初の呼び出しは、空の SalesOrder を作成します。 その後の EditLine の呼び出しでは、SalesOrder を 1 つの行項目を追加します。 最後に EndDoc 呼び出しでは、SalesOrder が閉じられます。  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 成功するには、同じセッションで 1 つの SalesOrder に対するすべての呼び出しを送信する必要があります。 これを行うには、セッションに対して何を行うアダプターを指示するメッセージ コンテキスト プロパティを割り当てます。 SalesOrder の例では、次が JD OneWorld セッションを処理するために、メッセージ コンテキスト プロパティに割り当てられる値。  
  
|関数|SessionID|ReserveSession|  
|--------------|---------------|--------------------|  
|BeginDoc|0|true|  
|EditLine|BeginDoc 応答からコピー|true|  
|EditLine|BeginDoc 応答からコピー|true|  
|EndDoc|BeginDoc 応答からコピー|false|  
  
- 最初の呼び出しでは、アダプターが自由に (SessionID がゼロであるため)、使用可能なセッションを選択します。  
  
- アダプターは、使用された SessionID を BeginDoc 応答で返します。  
  
- ReserveSession プロパティは、このセッションを明示的に要求する次の呼び出しのためには、このセッションを予約するアダプターを指示します。 その他の呼び出し誤って再利用しないセッションは予約されています。  
  
- 後続の呼び出しでは、SessionID を BeginDoc で返される値に設定して、セッションを要求します。  
  
- ReserveSession プロパティは true、少なくとも、シリーズの最後の呼び出しまでに設定します。  
  
- 最後の呼び出しは、ReserveSession をセッションを任意の呼び出しを使用できるようにする場合は false に設定します。 ただし、オーケストレーションより多くの呼び出しのセッションを維持することができます。  
  
  しばらくの間、セッションを使用しない場合にガベージ コレクト プールで、セッションが誤ってまだ予約されている場合でもです。  
  
  メッセージ コンテキスト プロパティの詳細については、BizTalk Server のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties2.md)   
 [メッセージ コンテキスト プロパティの値を割り当てる方法](../core/how-to-assign-message-context-property-values2.md)   
 [チュートリアル: BizTalk Adapter for JD Edwards OneWorld の使用](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)