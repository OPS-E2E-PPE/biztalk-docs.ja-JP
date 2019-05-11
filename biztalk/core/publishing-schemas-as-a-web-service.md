---
title: Web サービスとしてのスキーマの公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- schemas, publishing
- Web services, schemas
- schemas, Web services
ms.assetid: 65b5f826-6abf-437f-b2dc-b36e488ba6da
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a48833070fe0983f1884cf5e8e6cd03a123d134
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398375"
---
# <a name="publishing-schemas-as-a-web-service"></a><span data-ttu-id="f7baf-102">Web サービスとしてのスキーマの公開</span><span class="sxs-lookup"><span data-stu-id="f7baf-102">Publishing Schemas as a Web Service</span></span>
<span data-ttu-id="f7baf-103">BizTalk Web サービス公開ウィザードを使用して、既存のスキーマを使用する Web サービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f7baf-103">You use the BizTalk Web Services Publishing Wizard to create Web services that use existing schemas.</span></span> <span data-ttu-id="f7baf-104">公開する Web サービス、Web メソッド、要求スキーマ、および応答スキーマを宣言します。</span><span class="sxs-lookup"><span data-stu-id="f7baf-104">You declare the Web services, Web methods, and request and response schemas that you want to publish.</span></span> <span data-ttu-id="f7baf-105">ウィザードでは、ターゲットの名前空間、SOAP ヘッダーの必要性、および生成される Web サービス プロジェクトの場所を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f7baf-105">Using the wizard, you define the target namespace, SOAP header requirements, and the location of the generated Web service project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7baf-106">スキーマを含む BizTalk アセンブリをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7baf-106">You must compile the BizTalk assemblies containing the schemas.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="f7baf-107">各 Web メソッドには、1 つの要求スキーマと 1 つの応答スキーマを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f7baf-107">Each Web method can have one request schema and one response schema.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="f7baf-108">スキーマを Web サービスとして公開するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7baf-108">To publish schemas as a Web service, you must have [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="f7baf-109">BizTalk Web サービス公開ウィザードを実行する前に、Web サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7baf-109">Prior to running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="f7baf-110">Web サービスを有効にする方法の詳細については、次を参照してください。 [Web サービスを有効にする](../core/enabling-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7baf-110">For more information about enabling Web services, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7baf-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f7baf-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f7baf-112">Web サービスと Web メソッドの作成</span><span class="sxs-lookup"><span data-stu-id="f7baf-112">Creating Web Services and Web Methods</span></span>](../core/creating-web-services-and-web-methods.md)  
  
-   [<span data-ttu-id="f7baf-113">BizTalk Web サービス公開ウィザードを使用してスキーマを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="f7baf-113">How to Use the BizTalk Web Services Publishing Wizard to Publish Schemas as a Web Service</span></span>](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)