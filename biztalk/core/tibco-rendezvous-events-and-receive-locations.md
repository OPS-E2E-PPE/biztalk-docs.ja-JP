---
title: "TIBCO Rendezvous イベントと受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive locations, life cycle
ms.assetid: 3576af82-4723-4efc-961e-40b1150cf13d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9278687ff212fc2368eca138780417d7c052824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO Rendezvous イベントと受信場所
TIBCO Rendezvous システムは、選択したサブジェクト名にメッセージを送信できます。 概念*イベント*の他の TIBCO Rendezvous プログラムでメッセージが生成されます。  
  
 次の手順は、受信場所のライフ サイクルについて説明しています。  
  
1.  受信場所が作成されます。  
  
2.  受信場所がホストに関連付けられます。  
  
3.  受信場所がオーケストレーションにバインドされます。  
  
4.  受信場所が有効化されます。  
  
5.  受信場所がメッセージを受信します。  
  
> [!IMPORTANT]
>  各受信場所には一意の名前が必要です。 2 つの受信場所が同じ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開で同じ名前を持つことはできません。  
  
> [!IMPORTANT]
>  お勧め強力なアクセス制御リスト (ACL) に設定することで、受信場所のドロップ場所。 たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。  
  
## <a name="see-also"></a>参照  
 [作成元の TIBCO Rendezvous 受信ハンドラー](../core/creating-tibco-rendezvous-receive-handlers.md)