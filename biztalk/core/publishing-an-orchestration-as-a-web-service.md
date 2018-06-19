---
title: オーケストレーションを Web サービスとして公開 |Microsoft ドキュメント
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
ms.openlocfilehash: 6b6d36f6c56851bfedcd522f96d01a8256232826
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269066"
---
# <a name="publishing-an-orchestration-as-a-web-service"></a><span data-ttu-id="35ecb-102">Web サービスとしてのオーケストレーションの公開</span><span class="sxs-lookup"><span data-stu-id="35ecb-102">Publishing an Orchestration as a Web Service</span></span>
<span data-ttu-id="35ecb-103">BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開することができます。</span><span class="sxs-lookup"><span data-stu-id="35ecb-103">You use the BizTalk Web Services Publishing Wizard to publish an orchestration as a Web service.</span></span> <span data-ttu-id="35ecb-104">ウィザードでは、BizTalk アセンブリ内のオーケストレーションに基づいて、Web サービスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="35ecb-104">The wizard creates a Web service based on an orchestration in a BizTalk assembly.</span></span> <span data-ttu-id="35ecb-105">このウィザードを使用して、Web サービスを公開するオーケストレーションと受信ポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="35ecb-105">Using the wizard, you select orchestrations and receive ports to publish Web services.</span></span> <span data-ttu-id="35ecb-106">ターゲットの名前空間、SOAP ヘッダーの要件、およびウィザードで生成される Web サービス プロジェクトの場所を定義できます。</span><span class="sxs-lookup"><span data-stu-id="35ecb-106">You can define target namespaces, SOAP header requirements, and locations for the Web service project the wizard generates.</span></span>  
  
 <span data-ttu-id="35ecb-107">ウィザードを実行する前に、Web サービスとして公開するオーケストレーションとスキーマを含む BizTalk アセンブリをコンパイルすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="35ecb-107">Before you run the wizard, you must compile your BizTalk assemblies that contain the orchestrations and schemas that you intend to publish as a Web service.</span></span>  
  
 <span data-ttu-id="35ecb-108">BizTalk Web サービス公開ウィザードを実行する前に、Web サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ecb-108">Prior to running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="35ecb-109">詳細については、システム用の Web サービスを有効にすると、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="35ecb-109">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35ecb-110">オーケストレーションを Web サービスとして公開するには、事前に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ecb-110">You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before you can publish an orchestration as a Web service.</span></span> <span data-ttu-id="35ecb-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のインストールは不要です。</span><span class="sxs-lookup"><span data-stu-id="35ecb-111">You don't need to install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35ecb-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="35ecb-112">In This Section</span></span>  
  
-   [<span data-ttu-id="35ecb-113">オーケストレーションを Web サービスにマップする方法</span><span class="sxs-lookup"><span data-stu-id="35ecb-113">How to Map Orchestrations to Web Services</span></span>](../core/how-to-map-orchestrations-to-web-services.md)  
  
-   [<span data-ttu-id="35ecb-114">BizTalk Web サービス公開ウィザードを使用してオーケストレーションを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="35ecb-114">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)  
  
-   [<span data-ttu-id="35ecb-115">Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法</span><span class="sxs-lookup"><span data-stu-id="35ecb-115">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>](../core/how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service.md)