---
title: 手順 16:オーケストレーションの開始 |Microsoft Docs
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
ms.openlocfilehash: ade61af4ced6af3e256b3bc9095e911bf40db2a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288702"
---
# <a name="step-16-start-the-orchestration"></a>手順 16:オーケストレーションを開始します
この手順では、オーケストレーションを実行する物理環境と、オーケストレーションで設計したビジネス プロセスを関連付けるために、サービスを参加させます。 さらに、アプリケーションをテストできるように、オーケストレーションの処理を開始します。  
  
### <a name="to-start-the-orchestration"></a>オーケストレーションを開始するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、コンソールのツリー ウィンドウで [**オーケストレーション**、右クリックして**BTAHL7_Project.Doorbell_Orchestration**、] をクリックし、**参加**.  
  
2. 右クリック**BTAHL7_Project.Doorbell_Orchestration**、 をクリックし、**開始**します。  
  
   > [!NOTE]
   >  開始したことを確認、 **MLLPSendPort**送信ポートを有効になっている、 **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**受信場所。  
  
   続行する[手順 17。WSClient アプリケーションの作成](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)