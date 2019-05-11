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
ms.openlocfilehash: adbf3e0cfdc397b94383d7e0241eeddad045572d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281726"
---
# <a name="sql-processing-in-btarn"></a>BTARN での SQL 処理
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]基幹業務 (LOB) アプリケーションからのメッセージをルーティングする SQL アダプターを使用します。 SQL 送信ポートを使用して LOB アプリケーションにメッセージをルーティングします。  
  
## <a name="message-flow"></a>メッセージ フロー  
 バックエンドの LOB アプリケーションがの MessagesFromLOB テーブルにメッセージをルーティング、発信側または応答側コンピュータ、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SQL アダプターを使用して、プライベート プロセスに MessagesFromLOB テーブルからメッセージを移動します。 詳細については、BizTalk Server ヘルプの「SQL アダプタ」を参照してください。  
  
 ファイル アダプターを使用して、サービス コンテンツを送信することもできます[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]既定の SQL アダプタを使用する代わりにします。 ファイル アダプターを使用する場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]は添付ファイルをサポートしていません。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)