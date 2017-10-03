---
title: "BTARN での SQL 処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf1aba9f2d4d2ea77f369e76c277160739f7f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sql-processing-in-btarn"></a>BTARN での SQL 処理
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]基幹業務 (LOB) アプリケーションからのメッセージをルーティングする、SQL アダプターを使用します。 LOB アプリケーションへのメッセージのルーティングには、SQL 送信ポートが使用されます。  
  
## <a name="message-flow"></a>メッセージ フロー  
 発信側または応答側コンピューターで、バックエンド LOB アプリケーション メッセージをルーティングしますの MessagesFromLOB テーブル、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]MessagesFromLOB テーブルから、プライベート プロセスにメッセージを移動するのにには、SQL アダプタを使用します。 詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「SQL アダプタ」を参照してください。  
  
 既定の SQL アダプタを使用する代わりに、ファイル アダプタを使用してサービス コンテンツを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に送信することもできます。 ファイル アダプタを使用する場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では添付ファイルがサポートされません。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)