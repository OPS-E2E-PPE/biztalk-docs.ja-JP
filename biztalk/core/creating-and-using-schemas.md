---
title: 作成し、TIBCO でスキーマの使用 |Microsoft Docs
description: BizTalk エディターを使用して、BizTalk adapter for TIBCO Enterprise Message Service、スキーマを作成して、スキーマの BizTalk Server のターゲットの名前空間を設定
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 151ddefb45afd41c343b43de44786d7d99ff9b94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353671"
---
# <a name="create-and-use-tibco-schemas"></a><span data-ttu-id="8fa95-103">作成し、TIBCO スキーマを使用</span><span class="sxs-lookup"><span data-stu-id="8fa95-103">Create and use TIBCO schemas</span></span>

## <a name="overview"></a><span data-ttu-id="8fa95-104">概要</span><span class="sxs-lookup"><span data-stu-id="8fa95-104">Overview</span></span>
<span data-ttu-id="8fa95-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) は、(オーケストレーションでは、アダプターを使用) 場合のみ、Visual Studio で、XML エディターまたは BizTalk Server のエディターを使って作成するスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) uses schemas that you create using an XML editor or the BizTalk Server Editor in Visual Studio (only when you use the adapter in an orchestration).</span></span> <span data-ttu-id="8fa95-106">スキーマと思われる情報の種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-106">The schema describes the type of information that you expect.</span></span> <span data-ttu-id="8fa95-107">このトピックには、送信と受信ハンドラーの両方の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fa95-107">This topic contains information for both a send and a receive handler.</span></span>  
  
<span data-ttu-id="8fa95-108">スキーマを作成する使用の BizTalk adapter for TIBCO Enterprise Message Service には、ターゲットの名前空間が必要です。</span><span class="sxs-lookup"><span data-stu-id="8fa95-108">The schemas you create for use with BizTalk Adapter for TIBCO Enterprise Message Service must have a target namespace.</span></span> <span data-ttu-id="8fa95-109">BizTalk Server では、特定のメッセージ インスタンスを特定のオーケストレーションに関連付けられるキーのキーであるために、ターゲットの名前空間が必要です。</span><span class="sxs-lookup"><span data-stu-id="8fa95-109">BizTalk Server requires the target namespace because it is the key that associates a given message instance with a given orchestration.</span></span> <span data-ttu-id="8fa95-110">つまり、オーケストレーションを特定のターゲット名前空間を持つメッセージをサブスクライブしをそのターゲット名前空間を持つ受信 XML メッセージは、メッセージをサブスクライブしているすべてのオーケストレーションに与えられます。</span><span class="sxs-lookup"><span data-stu-id="8fa95-110">In other words, an orchestration subscribes to any message that has a specific target namespace, and an incoming XML message that has that target namespace is given to every orchestration that subscribed to the message.</span></span> <span data-ttu-id="8fa95-111">XML ドキュメント スキーマがターゲットの名前空間を持たない場合、BizTalk Server は、キーとしてルート要素の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-111">If an XML document schema does not have a target namespace, BizTalk Server uses the name of the root element as a key.</span></span>  

<span data-ttu-id="8fa95-112">次の手順では、ターゲットの名前空間を設定する方法と、スキーマを生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-112">The following steps show how to generate a schema, and how to set the target namespace.</span></span>  
  
## <a name="generate-a-schema"></a><span data-ttu-id="8fa95-113">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-113">Generate a Schema</span></span>    
 
1.  <span data-ttu-id="8fa95-114">BizTalk エディターでは、プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="8fa95-114">In the BizTalk Editor, open your project.</span></span>  
  
2.  <span data-ttu-id="8fa95-115">右上でソリューション エクスプ ローラーの **追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-115">Under Solution Explorer in the upper-right, select **Add**, and then select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="8fa95-116">**テンプレート**ペインで、**スキーマの生成**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-116">In the **Templates** pane, select **Generate Schemas**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="8fa95-117">**スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[**整形式 XML**します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-117">In the **Generate Schemas** dialog box, in the **Document type** list, select **Well-Formed XML**.</span></span>  
  
5.  <span data-ttu-id="8fa95-118">をクリックして**参照**をクリックして、スキーマを生成する入力ファイルを検索する**OK**。</span><span class="sxs-lookup"><span data-stu-id="8fa95-118">Click **Browse** to locate the input file for which you want to generate a schema, and then click **OK**.</span></span>  
  
<span data-ttu-id="8fa95-119">次に、ターゲットの名前空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-119">Next, set the target namespace.</span></span>  
  
## <a name="set-the-target-namespace"></a><span data-ttu-id="8fa95-120">ターゲットの名前空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-120">Set the target namespace</span></span>  
  
1. <span data-ttu-id="8fa95-121">BizTalk エディターで開き、スキーマ ファイルを右クリックして**\<スキーマ\>**、し、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-121">In BizTalk Editor, open your schema file, right-click **\<schema\>**, and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="8fa95-122">**プロパティ**ウィンドウで、検索、 **Namespace**フィールドし、たとえば、名前を入力`testNameSpace`します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-122">In the **Properties** pane, locate the **Namespace** field and type a name, for example, `testNameSpace`.</span></span>  
  
   <span data-ttu-id="8fa95-123">メッセージを使用してオーケストレーションを続行することができます。</span><span class="sxs-lookup"><span data-stu-id="8fa95-123">You can then continue with your orchestration using messages.</span></span> <span data-ttu-id="8fa95-124">メッセージが取得されて、BizTalk Server で、スキーマ セットのターゲットの名前空間を使用するオーケストレーションを検索し、オーケストレーション プロセスが実行します。</span><span class="sxs-lookup"><span data-stu-id="8fa95-124">When a message is picked up, BizTalk Server finds an orchestration that uses a schema with a set target namespace, and the orchestration process is followed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa95-125">参照</span><span class="sxs-lookup"><span data-stu-id="8fa95-125">See Also</span></span>  
 [<span data-ttu-id="8fa95-126">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="8fa95-126">Developing Applications</span></span>](../core/developing-applications5.md)