---
title: '手順 16: オーケストレーションを開始 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- message enrichment tutorial, orchestrations
ms.assetid: a9032b0b-1497-4f6a-8474-a94c14976be0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5256d33dc6751db34d1d827624d2dbe2644639e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206178"
---
# <a name="step-16-start-the-orchestration"></a>手順 16.、オーケストレーションを開始します。
このステップでは、オーケストレーションが実行される物理環境と、オーケストレーションで設計したビジネス プロセスを関連付けるために、サービスを参加させます。 さらに、アプリケーションをテストすることができるように、オーケストレーションの処理を開始します。  
  
### <a name="to-start-the-orchestration"></a>オーケストレーションを開始するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールのコンソール ツリー ウィンドウで**オーケストレーション**を右クリックして**BTAHL7_Project.Doorbell_Orchestration**、クリックして**参加**.  
  
2.  右クリック**BTAHL7_Project.Doorbell_Orchestration**、クリックして**開始**です。  
  
    > [!NOTE]
    >  開始したことを確認してください、 **MLLPSendPort**送信ポートを有効になっている、 **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**受信場所。  
  
 進みます[手順 17: クライアント アプリケーションを作成する](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)