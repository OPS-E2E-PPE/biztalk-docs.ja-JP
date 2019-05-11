---
title: EDI スキーマの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a8fbf3d-ebc7-47f6-87fa-e45722651262
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c87b3bd95fa6a58837a377b1454cdb6963312e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351070"
---
# <a name="developing-edi-schemas"></a><span data-ttu-id="c22d2-102">EDI スキーマの開発</span><span class="sxs-lookup"><span data-stu-id="c22d2-102">Developing EDI Schemas</span></span>
<span data-ttu-id="c22d2-103">このセクションのトピックで使用するため、EDI スキーマを変更する方法を説明する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c22d2-103">The topics in this section describe how to modify EDI Schemas for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c22d2-104">ソリューションでドキュメント スキーマを使用する BizTalk プロジェクトに追加することによって、スキーマを展開する必要があります。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ビルドすると、プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="c22d2-104">To use a document schema in your solution, you need to deploy the schema by adding it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and then building and deploying the project.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="c22d2-105">既定の BizTalk アプリケーション 1 でプロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="c22d2-105">will deploy the project in the default BizTalk Application 1.</span></span> <span data-ttu-id="c22d2-106">開くことで展開されているスキーマを参照してください、**スキーマ**ノードの下**BizTalk アプリケーション 1**ノード、**アプリケーション**内のノード、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c22d2-106">You can see the schemas that are deployed by opening the **Schemas** node under **BizTalk Application 1** node the **Applications** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="c22d2-107">コマンドライン展開ツールを使用して、別のアプリケーションにアセンブリを展開することができます`BTSTask`します。</span><span class="sxs-lookup"><span data-stu-id="c22d2-107">You can deploy an assembly into a different application by using the command-line deployment tool `BTSTask`.</span></span>  
  
 <span data-ttu-id="c22d2-108">サービスおよび管理スキーマはによって自動的に展開、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ウィザード。</span><span class="sxs-lookup"><span data-stu-id="c22d2-108">The service and control schemas are automatically deployed by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration wizard.</span></span> <span data-ttu-id="c22d2-109">これらを参照する をクリックして、**スキーマ**内のノード、 **BizTalk EDI アプリケーション**管理コンソール内のノード。</span><span class="sxs-lookup"><span data-stu-id="c22d2-109">To see them, click the **Schemas** node in the **BizTalk EDI Application** node in the Administration Console.</span></span> <span data-ttu-id="c22d2-110">これらのスキーマの詳細については、次を参照してください。 [EDI サービスと管理スキーマ](../core/edi-service-and-control-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="c22d2-110">For more information about these schemas, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c22d2-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c22d2-111">In This Section</span></span>  
  
-   [<span data-ttu-id="c22d2-112">EDI スキーマの変更</span><span class="sxs-lookup"><span data-stu-id="c22d2-112">Modifying EDI Schemas</span></span>](../core/modifying-edi-schemas.md)  
  
-   [<span data-ttu-id="c22d2-113">エンベロープ スキーマでの列挙のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c22d2-113">Customizing Enumerations in the Envelope Schema</span></span>](../core/customizing-enumerations-in-the-envelope-schema.md)  
  
-   [<span data-ttu-id="c22d2-114">クロスフィールド検証の構成</span><span class="sxs-lookup"><span data-stu-id="c22d2-114">Configuring Cross-Field Validation</span></span>](../core/configuring-cross-field-validation.md)  
  
## <a name="see-also"></a><span data-ttu-id="c22d2-115">参照</span><span class="sxs-lookup"><span data-stu-id="c22d2-115">See Also</span></span>  
 [<span data-ttu-id="c22d2-116">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="c22d2-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)