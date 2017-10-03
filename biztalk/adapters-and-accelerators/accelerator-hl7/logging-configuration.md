---
title: "ログの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 5cd7aec1-bd38-4d37-9a79-b01eeb89337d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 058a1fce8105a3147fb2e537a9182e7d886bb953
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="logging-configuration"></a><span data-ttu-id="14ea1-102">ログの構成</span><span class="sxs-lookup"><span data-stu-id="14ea1-102">Logging Configuration</span></span>
<span data-ttu-id="14ea1-103">同時に、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]と[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]医療機関病院、クリニック、看護住宅などのトランザクションとデジタル エンタープライズ アプリケーション統合 (EAI) 通信をセキュリティで保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="14ea1-103">Together, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] and [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] offer secure transactional and digital Enterprise Application Integration (EAI) communications for health care providers such as hospitals, clinics, and nursing homes.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14ea1-104">アプリケーションのアクティビティおよびトランザクション処理の調整、動的にメッセージをルーティング、検証、およびデータを変換する機能を提供し、さまざまなアダプタ経由で転送します。</span><span class="sxs-lookup"><span data-stu-id="14ea1-104"> provides the ability to coordinate application activity and transaction processing, dynamically route messages, validate and transform data, and transport over a variety of adapters.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="14ea1-105">米国規格協会 ANSI accredited ヘルス レベル 7 (HL7) をリアルタイムで医療のデータを交換プロバイダーのネットワークで医療/管理用のアプリケーションによって使用される標準のメッセージングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="14ea1-105"> supports the American National Standards Institute (ANSI)-accredited Health Level Seven (HL7) messaging standard used by clinical and administrative applications in provider networks to exchange medical data in real-time.</span></span>  
  
 <span data-ttu-id="14ea1-106">Accelerator システムを通過する HL7 メッセージは非常に重要となります。</span><span class="sxs-lookup"><span data-stu-id="14ea1-106">The HL7 messages that pass through the accelerator system can be very critical.</span></span> <span data-ttu-id="14ea1-107">たとえば、データは、患者の医療や金融取引可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14ea1-107">For example, the data could be a patient's medical record or a financial transaction.</span></span> <span data-ttu-id="14ea1-108">HL7 のセキュリティとプライバシーの規制に準拠するには、システム管理者は、次の操作できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14ea1-108">To ensure compliance with HL7 security and privacy regulations, system administrators must be able to do the following:</span></span>  
  
-   <span data-ttu-id="14ea1-109">保留メッセージをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="14ea1-109">Debug suspended messages</span></span>  
  
-   <span data-ttu-id="14ea1-110">潜在的な侵入者を検出し、セキュリティ侵害のリスクを低減する継続的にシステムとファイルのアクセスを監視します。</span><span class="sxs-lookup"><span data-stu-id="14ea1-110">Monitor system and file access on an ongoing basis to detect potential intruders and reduce the risk of security breaches</span></span>  
  
 <span data-ttu-id="14ea1-111">このセクションでは、監査を構成して、ログを確認し、監査データおよびイベント ログを解釈することを有効にして、ログに記録されたデータに対してクエリを実行する概念および手順に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="14ea1-111">This section provides conceptual and procedural information to enable you to configure auditing and logging, examine and interpret audit data and event logs, and run queries against the logged data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14ea1-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="14ea1-112">In This Section</span></span>  
  
-   [<span data-ttu-id="14ea1-113">ログ記録処理について</span><span class="sxs-lookup"><span data-stu-id="14ea1-113">About the Logging Process</span></span>](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [<span data-ttu-id="14ea1-114">ログの構成</span><span class="sxs-lookup"><span data-stu-id="14ea1-114">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)