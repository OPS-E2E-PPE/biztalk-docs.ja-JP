---
title: '手順 5: スキーマのプロパティの昇格 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60aa8681e9647e592af3173295c3d32e216f1f2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003219"
---
# <a name="step-5-promote-schema-properties"></a><span data-ttu-id="307a8-102">手順 5: スキーマのプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="307a8-102">Step 5: Promote Schema Properties</span></span>
<span data-ttu-id="307a8-103">この手順でスキーマのプロパティを昇格するように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、後の手順で作成したこれらのプロパティ値を参照できます。</span><span class="sxs-lookup"><span data-stu-id="307a8-103">In this step, you promote schema properties so that a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration can reference those property values that you create in later steps.</span></span> <span data-ttu-id="307a8-104">プロモーションは、メッセージ インスタンス内の特定の値を参照しにアクセスできるようにするために使用するメカニズム[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンポーネントやオーケストレーションなど、コンテンツ ベース ルーティングを行うのためです。</span><span class="sxs-lookup"><span data-stu-id="307a8-104">Promotion is a mechanism that you use to reference a specific value within a message instance and make it accessible to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] components such as orchestration or for content-based routing purposes.</span></span> <span data-ttu-id="307a8-105">さらに、昇格させたプロパティがで Microsoft IntelliSense の式エディターに表示される[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="307a8-105">Additionally, a promoted property is visible by Microsoft IntelliSense in the Expression Editor of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="307a8-106"> 監査と BizTalk 状態と動作状況の追跡 (HAT) ツールを使用してログ記録機能は、唯一の昇格させたスキーマ プロパティを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="307a8-106"> auditing and logging functionality with the BizTalk Health and Activity Tracking (HAT) tool can track only promoted schema properties.</span></span>  
  
### <a name="to-promote-schema-properties"></a><span data-ttu-id="307a8-107">スキーマのプロパティを昇格するには</span><span class="sxs-lookup"><span data-stu-id="307a8-107">To promote schema properties</span></span>  
  
1. <span data-ttu-id="307a8-108">ソリューション エクスプ ローラーで  **BTAHL7 プロジェクト**をダブルクリック、 **DoorBell.xsd**ノードがスキーマを開きます。</span><span class="sxs-lookup"><span data-stu-id="307a8-108">In Solution Explorer, under **BTAHL7 Project**, double-click the **DoorBell.xsd** node to open the schema.</span></span>  
  
2. <span data-ttu-id="307a8-109">右クリックし、 **FirstName**要素のフィールドをポイントして、**昇格**、 をクリックし、**クイック昇格**します。</span><span class="sxs-lookup"><span data-stu-id="307a8-109">Right-click the **FirstName** field element, point to **Promote**, and then click **Quick Promotion**.</span></span>  
  
3. <span data-ttu-id="307a8-110">クリックして**OK**プロパティ スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="307a8-110">Click **OK** to add the property schema to the project.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="307a8-111"> アイコンにオレンジ色の円を追加、 **FirstName**要素が昇格されていることを示す要素。</span><span class="sxs-lookup"><span data-stu-id="307a8-111"> adds an orange circle to the icon for the **FirstName** element, indicating that the element has been promoted.</span></span>  
  
4. <span data-ttu-id="307a8-112">次のフィールドの要素を昇格させる手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="307a8-112">Repeat these steps to promote the following field elements:</span></span>  
  
   -   <span data-ttu-id="307a8-113">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="307a8-113">**MiddleName**</span></span>  
  
   -   <span data-ttu-id="307a8-114">**LastName**</span><span class="sxs-lookup"><span data-stu-id="307a8-114">**LastName**</span></span>  
  
   -   <span data-ttu-id="307a8-115">**SSN**</span><span class="sxs-lookup"><span data-stu-id="307a8-115">**SSN**</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="307a8-116">その昇格患者 ID (PID) など、社会保障番号 (SSN) と、注意することが重要[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システムからのすべての受信メッセージのプロパティを追跡するためにします。</span><span class="sxs-lookup"><span data-stu-id="307a8-116">It is important to note that promoting a patient ID (PID) such as a social security number (SSN) causes [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to track that property for every inbound message through the system.</span></span> <span data-ttu-id="307a8-117">このような状況の副作用は、メッセージの追跡データベースが患者 SSNs のコピーを保持することです。</span><span class="sxs-lookup"><span data-stu-id="307a8-117">The side effect of this situation is that the message-tracking database keeps a copy of patient SSNs.</span></span> <span data-ttu-id="307a8-118">これは、重大なセキュリティの問題を作成できます。</span><span class="sxs-lookup"><span data-stu-id="307a8-118">This can create a significant security issue.</span></span> <span data-ttu-id="307a8-119">細心の注意とこのデータ ストアを保護するか、または PID データの昇格を完全に回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="307a8-119">You must either protect this data store with extreme care or avoid the promotion of PID data completely.</span></span>  
  
    <span data-ttu-id="307a8-120">昇格させたスキーマ要素に基づいてドキュメントの追跡の詳細については、正常性と動作状況の追跡について BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="307a8-120">For more information about tracking documents based on the schema elements that you promoted, see BizTalk Server Help for information on Health and Activity Tracking.</span></span>  
  
   <span data-ttu-id="307a8-121">続行する[手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="307a8-121">Proceed to [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307a8-122">参照</span><span class="sxs-lookup"><span data-stu-id="307a8-122">See Also</span></span>  
 [<span data-ttu-id="307a8-123">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="307a8-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)