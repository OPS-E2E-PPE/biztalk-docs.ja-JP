---
title: '手順 6: オーケストレーションの開始 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- loopback tutorial, starting orchestratrations
ms.assetid: f16a4a77-04fe-4e73-8517-556668174eb9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 973d0c5e8628d2363e8192c7faffeaebcc6d63b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993187"
---
# <a name="step-6-start-orchestrations"></a>手順 6: オーケストレーションを開始します。
この手順で Microsoft を使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Microsoft のオーケストレーションを開始する[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a>Visual Studio を使用して BTARN オーケストレーションを開始するには  
  
1.  **BTARN**管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**と順に展開**BizTalk アプリケーション 1**します。  
  
2.  クリックして**送信ポート**、し、開始**PrivateInitiator_To_LOB**と**PrivateResponder_To_LOB**送信ポート。  
  
3.  クリックして**受信場所**、しを有効にして**LOB_To_PrivateInitiator**、 **LOB_To_PrivateResponder**、 **Async_Http_Receive**、**Sync_Http_Receive**受信場所。  
  
4.  クリックして**オーケストレーション**、すべてを開始および**BTARN オーケストレーション**します。  
  
## <a name="see-also"></a>参照  
 [手順 7: サンプル LOB メッセージを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)   
 [プログラミングによるオーケストレーション、送信ポート、受信場所の停止および開始](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)