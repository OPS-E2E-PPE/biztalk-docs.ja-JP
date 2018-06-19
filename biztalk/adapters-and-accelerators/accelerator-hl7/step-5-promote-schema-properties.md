---
title: '手順 5: スキーマのプロパティを昇格させる |Microsoft ドキュメント'
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
ms.openlocfilehash: 91d68ece5bedf7ec46a6d5ede7efc6878fa972fc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004475"
---
# <a name="step-5-promote-schema-properties"></a><span data-ttu-id="89cdb-102">手順 5: スキーマのプロパティを昇格させる</span><span class="sxs-lookup"><span data-stu-id="89cdb-102">Step 5: Promote Schema Properties</span></span>
<span data-ttu-id="89cdb-103">このステップでは、スキーマ プロパティを昇格できるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、後の手順で作成するこれらのプロパティ値を参照できます。</span><span class="sxs-lookup"><span data-stu-id="89cdb-103">In this step, you promote schema properties so that a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration can reference those property values that you create in later steps.</span></span> <span data-ttu-id="89cdb-104">プロモーションはメッセージのインスタンス内で特定の値を参照しにアクセスできるようにするために使用メカニズム[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンポーネントやオーケストレーションなど、コンテンツ ベース ルーティングの目的。</span><span class="sxs-lookup"><span data-stu-id="89cdb-104">Promotion is a mechanism that you use to reference a specific value within a message instance and make it accessible to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] components such as orchestration or for content-based routing purposes.</span></span> <span data-ttu-id="89cdb-105">さらに、昇格させたプロパティでは表示[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]の式エディターでの IntelliSense[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="89cdb-105">Additionally, a promoted property is visible by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] IntelliSense in the Expression Editor of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="89cdb-106">監査と BizTalk 状態と動作状況の追跡 (HAT) ツールを使用してログ記録機能は、唯一の昇格させたスキーマ プロパティを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="89cdb-106"> auditing and logging functionality with the BizTalk Health and Activity Tracking (HAT) tool can track only promoted schema properties.</span></span>  
  
### <a name="to-promote-schema-properties"></a><span data-ttu-id="89cdb-107">スキーマ プロパティを昇格するには</span><span class="sxs-lookup"><span data-stu-id="89cdb-107">To promote schema properties</span></span>  
  
1.  <span data-ttu-id="89cdb-108">ソリューション エクスプ ローラーで、 **BTAHL7 プロジェクト**をダブルクリックして、 **DoorBell.xsd**を開くには、スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="89cdb-108">In Solution Explorer, under **BTAHL7 Project**, double-click the **DoorBell.xsd** node to open the schema.</span></span>  
  
2.  <span data-ttu-id="89cdb-109">右クリックし、 **FirstName**要素のフィールドをポイントし、**昇格**、クリックして**クイック昇格**です。</span><span class="sxs-lookup"><span data-stu-id="89cdb-109">Right-click the **FirstName** field element, point to **Promote**, and then click **Quick Promotion**.</span></span>  
  
3.  <span data-ttu-id="89cdb-110">をクリックして**OK**プロパティ スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="89cdb-110">Click **OK** to add the property schema to the project.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="89cdb-111">アイコンにオレンジ色の円を追加、 **FirstName**要素を昇格されていることを示す要素。</span><span class="sxs-lookup"><span data-stu-id="89cdb-111"> adds an orange circle to the icon for the **FirstName** element, indicating that the element has been promoted.</span></span>  
  
4.  <span data-ttu-id="89cdb-112">次のフィールドの要素を昇格させるには、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="89cdb-112">Repeat these steps to promote the following field elements:</span></span>  
  
    -   <span data-ttu-id="89cdb-113">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="89cdb-113">**MiddleName**</span></span>  
  
    -   <span data-ttu-id="89cdb-114">**[氏名]**</span><span class="sxs-lookup"><span data-stu-id="89cdb-114">**LastName**</span></span>  
  
    -   <span data-ttu-id="89cdb-115">**SSN**</span><span class="sxs-lookup"><span data-stu-id="89cdb-115">**SSN**</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="89cdb-116">その昇格患者の ID (PID) 社会保障番号 (SSN) などを確認することが重要[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をシステムからのすべての受信メッセージのプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="89cdb-116">It is important to note that promoting a patient ID (PID) such as a social security number (SSN) causes [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to track that property for every inbound message through the system.</span></span> <span data-ttu-id="89cdb-117">このような状況の副作用は、メッセージの追跡データベースが患者 SSNs のコピーを保持することです。</span><span class="sxs-lookup"><span data-stu-id="89cdb-117">The side effect of this situation is that the message-tracking database keeps a copy of patient SSNs.</span></span> <span data-ttu-id="89cdb-118">これは、重要なセキュリティ上の問題を作成できます。</span><span class="sxs-lookup"><span data-stu-id="89cdb-118">This can create a significant security issue.</span></span> <span data-ttu-id="89cdb-119">このデータ ストアに細心の注意を保護するか、または PID データの昇格を完全に回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89cdb-119">You must either protect this data store with extreme care or avoid the promotion of PID data completely.</span></span>  
  
     <span data-ttu-id="89cdb-120">昇格させたスキーマ要素に基づいてドキュメントの追跡の詳細については、正常性と動作状況の追跡について BizTalk Server ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89cdb-120">For more information about tracking documents based on the schema elements that you promoted, see BizTalk Server Help for information on Health and Activity Tracking.</span></span>  
  
 <span data-ttu-id="89cdb-121">進みます[手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="89cdb-121">Proceed to [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89cdb-122">参照</span><span class="sxs-lookup"><span data-stu-id="89cdb-122">See Also</span></span>  
 [<span data-ttu-id="89cdb-123">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="89cdb-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)