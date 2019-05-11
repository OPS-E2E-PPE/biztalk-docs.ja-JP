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
# <a name="logging-configuration"></a><span data-ttu-id="63388-102">ログの構成</span><span class="sxs-lookup"><span data-stu-id="63388-102">Logging Configuration</span></span>
<span data-ttu-id="63388-103">同時に、MicrosoftBizTalk サーバーと[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]病院、診療所、看護の現場自宅などの医療のトランザクションとデジタル エンタープライズ アプリケーション統合 (EAI) 通信をセキュリティで保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="63388-103">Together, MicrosoftBizTalk Server and [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] offer secure transactional and digital Enterprise Application Integration (EAI) communications for health care providers such as hospitals, clinics, and nursing homes.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="63388-104">アプリケーションの動作とトランザクション処理の調整、動的にメッセージをルーティング、検証、およびデータを変換する機能を提供し、さまざまなアダプターのトランスポート。</span><span class="sxs-lookup"><span data-stu-id="63388-104">provides the ability to coordinate application activity and transaction processing, dynamically route messages, validate and transform data, and transport over a variety of adapters.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="63388-105">米国規格協会 ANSI 認定された正常性レベル 7 (HL7) をリアルタイムでの医療データを交換プロバイダーのネットワークで臨床および管理アプリケーションで使用される標準のメッセージングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="63388-105">supports the American National Standards Institute (ANSI)-accredited Health Level Seven (HL7) messaging standard used by clinical and administrative applications in provider networks to exchange medical data in real-time.</span></span>  
  
 <span data-ttu-id="63388-106">アクセラレータのシステムを通過する HL7 メッセージは非常に重要となります。</span><span class="sxs-lookup"><span data-stu-id="63388-106">The HL7 messages that pass through the accelerator system can be very critical.</span></span> <span data-ttu-id="63388-107">たとえば、データには、患者の医療記録または金融取引ができます。</span><span class="sxs-lookup"><span data-stu-id="63388-107">For example, the data could be a patient's medical record or a financial transaction.</span></span> <span data-ttu-id="63388-108">HL7 のセキュリティとプライバシー規制に準拠するため、システム管理者は、以下を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="63388-108">To ensure compliance with HL7 security and privacy regulations, system administrators must be able to do the following:</span></span>  
  
- <span data-ttu-id="63388-109">保留メッセージをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="63388-109">Debug suspended messages</span></span>  
  
- <span data-ttu-id="63388-110">可能性のある侵入者の検知し、セキュリティ侵害のリスクを軽減する継続的にシステムとファイルのアクセスを監視します。</span><span class="sxs-lookup"><span data-stu-id="63388-110">Monitor system and file access on an ongoing basis to detect potential intruders and reduce the risk of security breaches</span></span>  
  
  <span data-ttu-id="63388-111">このセクションでは、監査を構成し、監査データおよびイベント ログを解釈し、確認、ログ記録を有効にして、ログに記録されたデータに対してクエリを実行する概念と手順の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="63388-111">This section provides conceptual and procedural information to enable you to configure auditing and logging, examine and interpret audit data and event logs, and run queries against the logged data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63388-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="63388-112">In This Section</span></span>  
  
-   [<span data-ttu-id="63388-113">ログ処理の概要</span><span class="sxs-lookup"><span data-stu-id="63388-113">About the Logging Process</span></span>](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [<span data-ttu-id="63388-114">ログ記録の構成</span><span class="sxs-lookup"><span data-stu-id="63388-114">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)