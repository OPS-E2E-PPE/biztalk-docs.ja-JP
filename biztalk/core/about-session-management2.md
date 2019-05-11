---
title: セッション Management2 について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ecdb4f-d384-42ac-9776-e7ad14d5f151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b316a1a145f6f5d6d839febcc02c1fe2056b9579
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362294"
---
# <a name="about-session-management"></a>セッション管理について
Microsoft BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne サーバーへの呼び出しを送信する接続セッションを作成します。 呼び出しが終了すると、セッションは、後続の呼び出しで再利用するプールに格納されます。 アダプターは、JD Edwards EnterpriseOne サーバーに対する同時呼び出しを処理する複数の接続セッションを作成します。 プールが不要になったセッションを削除する定期的にクリーンアップされます。  
  
 Microsoft BizTalk Adapter JD Edwards EnterpriseOne は、呼び出しする必要があります、同じセッション内で発生したときに制御する 2 つのメッセージ コンテキスト プロパティを提供します。  
  
|名前|型|既定|  
|----------|----------|-------------|  
|JDE します。セッション Id|Int|0|  
|JDE します。ReserveSession|boolean|false|  
  
 セッション管理は、ビジネス関数には、JD Edwards EnterpriseOne サーバーを 1 回の呼び出しが必要な場合に必要ではありません。 アダプターが使用可能なセッションを選択し、セッションは後続の呼び出しでも使用できます。 このシナリオで、既定値は適切なメッセージ コンテキスト プロパティを無視できます。  
  
 一部の JD Edwards EnterpriseOne 機能が、JD Edwards EnterpriseOne サーバーを複数回呼び出す必要があります。たとえば、SalesOrder の作成です。 BeginDoc の最初の呼び出しは、空の SalesOrder を作成します。 その後の EditLine の呼び出しでは、SalesOrder を 1 つの行項目を追加します。 最後に EndDoc 呼び出しでは、SalesOrder が閉じられます。  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 成功するには、同じセッションで 1 つの SalesOrder に対するすべての呼び出しを送信する必要があります。 これを行うには、セッションに対して何を行うアダプターを指示するメッセージ コンテキスト プロパティを割り当てます。 SalesOrder の例では、JD Edwards EnterpriseOne セッションを処理するために、メッセージ コンテキスト プロパティに割り当てられる値は、これらは。  
  
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
 [メッセージ コンテキストのプロパティの使用](../core/using-message-context-properties1.md)