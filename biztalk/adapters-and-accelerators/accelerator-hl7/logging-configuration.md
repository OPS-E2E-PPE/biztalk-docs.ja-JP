---
title: ログの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 5cd7aec1-bd38-4d37-9a79-b01eeb89337d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e90054dc7316cc0fcae2179845ce56c6254f251
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65300032"
---
# <a name="logging-configuration"></a>ログの構成
同時に、MicrosoftBizTalk サーバーと[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]病院、診療所、看護の現場自宅などの医療のトランザクションとデジタル エンタープライズ アプリケーション統合 (EAI) 通信をセキュリティで保護を提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] アプリケーションの動作とトランザクション処理の調整、動的にメッセージをルーティング、検証、およびデータを変換する機能を提供し、さまざまなアダプターのトランスポート。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 米国規格協会 ANSI 認定された正常性レベル 7 (HL7) をリアルタイムでの医療データを交換プロバイダーのネットワークで臨床および管理アプリケーションで使用される標準のメッセージングをサポートします。  
  
 アクセラレータのシステムを通過する HL7 メッセージは非常に重要となります。 たとえば、データには、患者の医療記録または金融取引ができます。 HL7 のセキュリティとプライバシー規制に準拠するため、システム管理者は、以下を実行できる必要があります。  
  
- 保留メッセージをデバッグします。  
  
- 可能性のある侵入者の検知し、セキュリティ侵害のリスクを軽減する継続的にシステムとファイルのアクセスを監視します。  
  
  このセクションでは、監査を構成し、監査データおよびイベント ログを解釈し、確認、ログ記録を有効にして、ログに記録されたデータに対してクエリを実行する概念と手順の情報を提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ログ処理の概要](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [ログ記録の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)