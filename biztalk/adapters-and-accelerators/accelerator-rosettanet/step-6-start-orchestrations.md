---
title: "手順 6: オーケストレーションの開始 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- loopback tutorial, starting orchestratrations
ms.assetid: f16a4a77-04fe-4e73-8517-556668174eb9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef08b7c0db08d527df4943aa25650d81231e703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-start-orchestrations"></a>手順 6: オーケストレーションを開始します。
このステップで使用して[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]のオーケストレーションを開始する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]です。  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a>Visual Studio を使用して BTARN オーケストレーションを開始するには  
  
1.  **BTARN**管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、および展開し、 **BizTalk アプリケーション 1**です。  
  
2.  をクリックして**送信ポート**、し、開始**PrivateInitiator_To_LOB**と**PrivateResponder_To_LOB**送信ポート。  
  
3.  をクリックして**受信場所**、し有効にして**LOB_To_PrivateInitiator**、 **LOB_To_PrivateResponder**、 **Async_Http_Receive**、および**Sync_Http_Receive**受信場所。  
  
4.  をクリックして**オーケストレーション**、すべてを開始および**BTARN オーケストレーション**です。  
  
## <a name="see-also"></a>参照  
 [手順 7: サンプル LOB メッセージを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)   
 [停止および開始オーケストレーション、送信ポート、および受信場所をプログラムで](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)