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
ms.openlocfilehash: e35feaa691833c570217ded76e95b1d79a377f4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994603"
---
# <a name="about-session-management"></a>セッション管理について
Microsoft BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld サーバーの呼び出しを送信する接続セッションを作成します。 呼び出しが終了すると、セッションはプールに格納され、その後の呼び出しで再利用されます。 このアダプターは、JD Edwards OneWorld サーバーの同時呼び出しを処理する複数の接続セッションを作成します。 プールは不要になったセッションを削除するために定期的に消去されます。  
  
 Microsoft BizTalk Adapter for JD Edwards OneWorld には、1 つのセッション内で呼び出しがいつ発生する必要があるかを制御するメッセージ コンテキスト プロパティが 2 つあります。  
  
|名前|型|既定|  
|----------|----------|-------------|  
|JDE.SessionID|Int|0|  
|JDE.ReserveSession|boolean|false|  
  
 ビジネス関数で JD Edwards OneWorld サーバーを 1 回だけ呼び出す必要がある場合、セッション管理は不要です。 このアダプタは使用可能なセッションを選択でき、そのセッションは後続の呼び出しでも使用可能になります。 このシナリオでは、既定値のままで適切であるため、メッセージ コンテキスト プロパティは無視できます。  
  
 一部の JD Edwards OneWorld 機能では、JD Edwards OneWorld サーバーを複数回呼び出す必要があります (SalesOrder の作成など)。 最初に BeginDoc を呼び出したときに、空の SalesOrder が作成されます。 その後の EditLine の呼び出しでは、1 行の項目が SalesOrder に追加されます。 最後に EndDoc を呼び出したときに、SalesOrder が閉じられます。  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 1 つの SalesOrder に対するすべての呼び出しは、1 回のセッションで送信する必要があります。 この操作を行うには、セッションの処理方法をアダプタに指示するために、メッセージ コンテキスト プロパティを割り当てます。 SalesOrder の例では、次の表の値が JD OneWorld セッションを処理するためにメッセージ コンテキスト プロパティに割り当てられます。  
  
|機能|SessionID|ReserveSession|  
|--------------|---------------|--------------------|  
|BeginDoc|0|true|  
|EditLine|BeginDoc 応答からのコピー|true|  
|EditLine|BeginDoc 応答からのコピー|true|  
|EndDoc|BeginDoc 応答からのコピー|false|  
  
- 最初の呼び出しについては、アダプタは任意の使用可能なセッションを自由に選択できます (SessionID がゼロであるため)。  
  
- アダプタは、BeginDoc 応答で使用された SessionID を返します。  
  
- ReserveSession プロパティは、このセッションを明示的に要求する後続の呼び出しのためにこのセッションを予約しておくようにアダプタに指示します。 このセッションは予約済みであるため、他の呼び出しによって誤って再利用されることはありません。  
  
- 後続の呼び出しでは、SessionID を BeginDoc で返された値に設定することにより、このセッションが要求されます。  
  
- ReserveSession プロパティは、少なくとも、一連の呼び出しの最後までは、true に設定されます。  
  
- 最後の呼び出しで、ReserveSession が false に設定され、その後の任意の呼び出しでこのセッションが使用可能になります。 ただし、オーケストレーションではその後の呼び出しでもこのセッションを保持することができます。  
  
  セッションがしばらく使用されない場合は、セッションが誤ってまだ予約されている場合であっても、プールによるガベージ コレクションが行われます。  
  
  メッセージ コンテキスト プロパティの詳細については、BizTalk Server のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties2.md)   
 [メッセージ コンテキスト プロパティの値を割り当てる方法](../core/how-to-assign-message-context-property-values2.md)   
 [チュートリアル: BizTalk Adapter for JD Edwards OneWorld の使用](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)