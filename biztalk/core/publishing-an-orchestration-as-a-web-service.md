---
title: Web サービスとしてのオーケストレーションの公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- orchestrations, Web services
- Web services, orchestrations
- BizTalk Web Services Publishing Wizard, orchestrations
- BizTalk Web Services Publishing Wizard, prerequisites
- orchestrations, publishing
ms.assetid: f209310d-c265-4c37-8424-c9b287e713ca
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35f54c6aa850416029ad54b49de59178bcefd34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398385"
---
# <a name="publishing-an-orchestration-as-a-web-service"></a><span data-ttu-id="32030-102">Web サービスとしてのオーケストレーションの公開</span><span class="sxs-lookup"><span data-stu-id="32030-102">Publishing an Orchestration as a Web Service</span></span>
<span data-ttu-id="32030-103">BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開することができます。</span><span class="sxs-lookup"><span data-stu-id="32030-103">You use the BizTalk Web Services Publishing Wizard to publish an orchestration as a Web service.</span></span> <span data-ttu-id="32030-104">ウィザードでは、BizTalk アセンブリ内のオーケストレーションに基づいた Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="32030-104">The wizard creates a Web service based on an orchestration in a BizTalk assembly.</span></span> <span data-ttu-id="32030-105">ウィザードを使用して、オーケストレーションを選択し、受信ポートを Web サービスを公開します。</span><span class="sxs-lookup"><span data-stu-id="32030-105">Using the wizard, you select orchestrations and receive ports to publish Web services.</span></span> <span data-ttu-id="32030-106">ターゲットの名前空間、SOAP ヘッダーの要件、およびウィザードで生成する Web サービス プロジェクトの場所を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="32030-106">You can define target namespaces, SOAP header requirements, and locations for the Web service project the wizard generates.</span></span>  
  
 <span data-ttu-id="32030-107">ウィザードを実行する前に、オーケストレーションと Web サービスとして公開するスキーマを含む BizTalk アセンブリをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32030-107">Before you run the wizard, you must compile your BizTalk assemblies that contain the orchestrations and schemas that you intend to publish as a Web service.</span></span>  
  
 <span data-ttu-id="32030-108">BizTalk Web サービス公開ウィザードを実行する前に、Web サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32030-108">Prior to running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="32030-109">お使いのシステムの Web サービスを有効にする方法の詳細については、次を参照してください。 [Web サービスを有効にする](../core/enabling-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="32030-109">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32030-110">インストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]前に、Web サービスとして、オーケストレーションを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="32030-110">You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before you can publish an orchestration as a Web service.</span></span> <span data-ttu-id="32030-111">Microsoft をインストールする必要はありません[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="32030-111">You don't need to install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32030-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="32030-112">In This Section</span></span>  
  
-   [<span data-ttu-id="32030-113">Web サービスにオーケストレーションをマップする方法</span><span class="sxs-lookup"><span data-stu-id="32030-113">How to Map Orchestrations to Web Services</span></span>](../core/how-to-map-orchestrations-to-web-services.md)  
  
-   [<span data-ttu-id="32030-114">BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="32030-114">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)  
  
-   [<span data-ttu-id="32030-115">Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法</span><span class="sxs-lookup"><span data-stu-id="32030-115">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>](../core/how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service.md)