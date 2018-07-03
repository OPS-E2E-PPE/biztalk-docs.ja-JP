---
title: BTARN での SQL 処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21255c03a9a9c1f2a30eb7f716c5e1bf285a3c5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000715"
---
# <a name="sql-processing-in-btarn"></a>BTARN での SQL 処理
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]基幹業務 (LOB) アプリケーションからのメッセージをルーティングする SQL アダプターを使用します。 LOB アプリケーションへのメッセージのルーティングには、SQL 送信ポートが使用されます。  
  
## <a name="message-flow"></a>メッセージ フロー  
 バックエンドの LOB アプリケーションがの MessagesFromLOB テーブルにメッセージをルーティング、発信側または応答側コンピュータ、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SQL アダプターを使用して、プライベート プロセスに MessagesFromLOB テーブルからメッセージを移動します。 詳細については、BizTalk Server ヘルプの「SQL アダプタ」を参照してください。  
  
 既定の SQL アダプタを使用する代わりに、ファイル アダプタを使用してサービス コンテンツを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に送信することもできます。 ファイル アダプタを使用する場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では添付ファイルがサポートされません。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)