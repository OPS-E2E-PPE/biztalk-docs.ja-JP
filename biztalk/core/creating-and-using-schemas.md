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
ms.openlocfilehash: a9c3ba874f7db3b1aff77c9377ea27874de8501d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969521"
---
# <a name="create-and-use-tibco-schemas"></a><span data-ttu-id="0951b-103">作成し、TIBCO スキーマを使用</span><span class="sxs-lookup"><span data-stu-id="0951b-103">Create and use TIBCO schemas</span></span>

## <a name="overview"></a><span data-ttu-id="0951b-104">概要</span><span class="sxs-lookup"><span data-stu-id="0951b-104">Overview</span></span>
<span data-ttu-id="0951b-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) で使用するスキーマは、XML エディターまたは Visual Studio の BizTalk Server エディター (オーケストレーションでアダプターを使用する場合のみ) を使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="0951b-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) uses schemas that you create using an XML editor or the BizTalk Server Editor in Visual Studio (only when you use the adapter in an orchestration).</span></span> <span data-ttu-id="0951b-106">スキーマには、想定している情報の種類を記述します。</span><span class="sxs-lookup"><span data-stu-id="0951b-106">The schema describes the type of information that you expect.</span></span> <span data-ttu-id="0951b-107">このトピックの情報は、送信ハンドラーと受信ハンドラーの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0951b-107">This topic contains information for both a send and a receive handler.</span></span>  
  
<span data-ttu-id="0951b-108">BizTalk Adapter for TIBCO Enterprise Message Service で使用するスキーマを作成するときは、ターゲットの名前空間を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0951b-108">The schemas you create for use with BizTalk Adapter for TIBCO Enterprise Message Service must have a target namespace.</span></span> <span data-ttu-id="0951b-109">BizTalk Server でターゲットの名前空間が必要なのは、特定のメッセージ インスタンスを特定のオーケストレーションに関連付けるキーとなるからです。</span><span class="sxs-lookup"><span data-stu-id="0951b-109">BizTalk Server requires the target namespace because it is the key that associates a given message instance with a given orchestration.</span></span> <span data-ttu-id="0951b-110">つまり、オーケストレーションでは特定のターゲットの名前空間を持つメッセージをサブスクライブし、そのターゲットの名前空間を持つ受信 XML メッセージが、メッセージをサブスクライブしたすべてのオーケストレーションに配信されます。</span><span class="sxs-lookup"><span data-stu-id="0951b-110">In other words, an orchestration subscribes to any message that has a specific target namespace, and an incoming XML message that has that target namespace is given to every orchestration that subscribed to the message.</span></span> <span data-ttu-id="0951b-111">XML ドキュメント スキーマにターゲットの名前空間がない場合は、ルート要素の名前がキーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0951b-111">If an XML document schema does not have a target namespace, BizTalk Server uses the name of the root element as a key.</span></span>  

<span data-ttu-id="0951b-112">次の手順では、ターゲットの名前空間を設定する方法と、スキーマを生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0951b-112">The following steps show how to generate a schema, and how to set the target namespace.</span></span>  
  
## <a name="generate-a-schema"></a><span data-ttu-id="0951b-113">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="0951b-113">Generate a Schema</span></span>    
 
1.  <span data-ttu-id="0951b-114">BizTalk エディターで、プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="0951b-114">In the BizTalk Editor, open your project.</span></span>  
  
2.  <span data-ttu-id="0951b-115">右上でソリューション エクスプ ローラーの **追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="0951b-115">Under Solution Explorer in the upper-right, select **Add**, and then select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="0951b-116">**テンプレート**ペインで、**スキーマの生成**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="0951b-116">In the **Templates** pane, select **Generate Schemas**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="0951b-117">**スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[**整形式 XML**します。</span><span class="sxs-lookup"><span data-stu-id="0951b-117">In the **Generate Schemas** dialog box, in the **Document type** list, select **Well-Formed XML**.</span></span>  
  
5.  <span data-ttu-id="0951b-118">をクリックして**参照**をクリックして、スキーマを生成する入力ファイルを検索する**OK**。</span><span class="sxs-lookup"><span data-stu-id="0951b-118">Click **Browse** to locate the input file for which you want to generate a schema, and then click **OK**.</span></span>  
  
<span data-ttu-id="0951b-119">次に、ターゲットの名前空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="0951b-119">Next, set the target namespace.</span></span>  
  
## <a name="set-the-target-namespace"></a><span data-ttu-id="0951b-120">ターゲットの名前空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="0951b-120">Set the target namespace</span></span>  
  
1. <span data-ttu-id="0951b-121">BizTalk エディターで開き、スキーマ ファイルを右クリックして**\<スキーマ\>**、し、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0951b-121">In BizTalk Editor, open your schema file, right-click **\<schema\>**, and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="0951b-122">**プロパティ**ウィンドウで、検索、 **Namespace**フィールドし、たとえば、名前を入力`testNameSpace`します。</span><span class="sxs-lookup"><span data-stu-id="0951b-122">In the **Properties** pane, locate the **Namespace** field and type a name, for example, `testNameSpace`.</span></span>  
  
   <span data-ttu-id="0951b-123">これで、メッセージを使用してオーケストレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="0951b-123">You can then continue with your orchestration using messages.</span></span> <span data-ttu-id="0951b-124">メッセージが取得されると、ターゲットの名前空間が設定されたスキーマを使用するオーケストレーションが BizTalk Server で検索され、オーケストレーション プロセスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0951b-124">When a message is picked up, BizTalk Server finds an orchestration that uses a schema with a set target namespace, and the orchestration process is followed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0951b-125">参照</span><span class="sxs-lookup"><span data-stu-id="0951b-125">See Also</span></span>  
 [<span data-ttu-id="0951b-126">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="0951b-126">Developing Applications</span></span>](../core/developing-applications5.md)