---
title: "EDI スキーマの開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a8fbf3d-ebc7-47f6-87fa-e45722651262
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b241b5d0477d7aa477511c43b642e4e312f2651a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="developing-edi-schemas"></a><span data-ttu-id="568b2-102">EDI スキーマの開発</span><span class="sxs-lookup"><span data-stu-id="568b2-102">Developing EDI Schemas</span></span>
<span data-ttu-id="568b2-103">このセクションの各トピックでは、EDI スキーマを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用できるように変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="568b2-103">The topics in this section describe how to modify EDI Schemas for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="568b2-104">ソリューションでドキュメント スキーマを使用するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で BizTalk プロジェクトにスキーマを追加して展開した後、プロジェクトをビルドおよび展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="568b2-104">To use a document schema in your solution, you need to deploy the schema by adding it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and then building and deploying the project.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="568b2-105">既定の BizTalk アプリケーション 1 でプロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="568b2-105"> will deploy the project in the default BizTalk Application 1.</span></span> <span data-ttu-id="568b2-106">開くことによって展開されているスキーマを表示、**スキーマ**ノードの下**BizTalk アプリケーション 1**ノード、**アプリケーション**内のノード、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="568b2-106">You can see the schemas that are deployed by opening the **Schemas** node under **BizTalk Application 1** node the **Applications** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="568b2-107">コマンド ライン展開ツール `BTSTask` を使用すると、アセンブリをさまざまなアプリケーションに展開できます。</span><span class="sxs-lookup"><span data-stu-id="568b2-107">You can deploy an assembly into a different application by using the command-line deployment tool `BTSTask`.</span></span>  
  
 <span data-ttu-id="568b2-108">サービスおよび管理スキーマは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードによって自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="568b2-108">The service and control schemas are automatically deployed by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration wizard.</span></span> <span data-ttu-id="568b2-109">これらを参照する をクリックして、**スキーマ**内のノード、 **BizTalk EDI アプリケーション**管理コンソール内のノードです。</span><span class="sxs-lookup"><span data-stu-id="568b2-109">To see them, click the **Schemas** node in the **BizTalk EDI Application** node in the Administration Console.</span></span> <span data-ttu-id="568b2-110">これらのスキーマの詳細については、次を参照してください。 [EDI サービスと管理スキーマ](../core/edi-service-and-control-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="568b2-110">For more information about these schemas, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="568b2-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="568b2-111">In This Section</span></span>  
  
-   [<span data-ttu-id="568b2-112">EDI スキーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="568b2-112">Modifying EDI Schemas</span></span>](../core/modifying-edi-schemas.md)  
  
-   [<span data-ttu-id="568b2-113">エンベロープ スキーマで列挙をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="568b2-113">Customizing Enumerations in the Envelope Schema</span></span>](../core/customizing-enumerations-in-the-envelope-schema.md)  
  
-   [<span data-ttu-id="568b2-114">クロス フィールド検証の構成</span><span class="sxs-lookup"><span data-stu-id="568b2-114">Configuring Cross-Field Validation</span></span>](../core/configuring-cross-field-validation.md)  
  
## <a name="see-also"></a><span data-ttu-id="568b2-115">参照</span><span class="sxs-lookup"><span data-stu-id="568b2-115">See Also</span></span>  
 [<span data-ttu-id="568b2-116">開発および BizTalk Server EDI ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="568b2-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)