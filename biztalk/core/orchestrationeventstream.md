---
title: OrchestrationEventStream |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7c63610-6344-4b71-8d65-3add7883bc79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981f21440f7634fc2444f850c9b10766ae4a636b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262967"
---
# <a name="orchestrationeventstream"></a>OrchestrationEventStream
OrchestrationEventStream (OES) API は、BizTalk Server がインストールされているコンピューターでアプリケーションを実行し、BizTalk オーケストレーション トランザクションの一部である項目を追跡する場合に使用します。  
  
 OES API は、追跡データを最初に BizTalk メッセージ ボックス データベースに格納します。 このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。  
  
 OES API は、Microsoft.BizTalk.Bam.EventObservation 名前空間に含まれています。 API を使用するには、Microsoft.Biztalk.BAM.Xlangs.dll をプロジェクトに追加する必要があります。  
  
## <a name="oes-members"></a>OES のメンバー  
 OES API は、 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) クラスから派生しています。  
  
 OES は、EventStream クラスのメソッドをすべて実装していますが、動作に関して以下の例外があります。  
  
 **パブリック静的 void Clear();**  
  
 操作なし  
  
 **public static void Flush();**  
  
 操作なし  
  
## <a name="see-also"></a>参照  
 [EventStream クラス](../core/eventstream-classes.md)