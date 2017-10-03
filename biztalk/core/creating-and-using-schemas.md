---
title: "作成して、スキーマを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas
- creating schemas
- schemas, generating
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f10275c5ed0b887907c7b26b7d1ce8ad5003b099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-using-schemas"></a><span data-ttu-id="4afcd-102">作成して、スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="4afcd-102">Creating and Using Schemas</span></span>
<span data-ttu-id="4afcd-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) で使用するスキーマは、XML エディターまたは Visual Studio の BizTalk Server エディター (オーケストレーションでアダプターを使用する場合のみ) を使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="4afcd-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) uses schemas that you create using an XML editor or the BizTalk Server Editor in Visual Studio (only when you use the adapter in an orchestration).</span></span> <span data-ttu-id="4afcd-104">スキーマには、想定している情報の種類を記述します。</span><span class="sxs-lookup"><span data-stu-id="4afcd-104">The schema describes the type of information that you expect.</span></span> <span data-ttu-id="4afcd-105">このトピックの情報は、送信ハンドラーと受信ハンドラーの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4afcd-105">This topic contains information for both a send and a receive handler.</span></span>  
  
 <span data-ttu-id="4afcd-106">BizTalk Adapter for TIBCO Enterprise Message Service で使用するスキーマを作成するときは、ターゲットの名前空間を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afcd-106">The schemas you create for use with BizTalk Adapter for TIBCO Enterprise Message Service must have a target namespace.</span></span> <span data-ttu-id="4afcd-107">BizTalk Server でターゲットの名前空間が必要なのは、特定のメッセージ インスタンスを特定のオーケストレーションに関連付けるキーとなるからです。</span><span class="sxs-lookup"><span data-stu-id="4afcd-107">BizTalk Server requires the target namespace because it is the key that associates a given message instance with a given orchestration.</span></span> <span data-ttu-id="4afcd-108">つまり、オーケストレーションでは特定のターゲットの名前空間を持つメッセージをサブスクライブし、そのターゲットの名前空間を持つ受信 XML メッセージが、メッセージをサブスクライブしたすべてのオーケストレーションに配信されます。</span><span class="sxs-lookup"><span data-stu-id="4afcd-108">In other words, an orchestration subscribes to any message that has a specific target namespace, and an incoming XML message that has that target namespace is given to every orchestration that subscribed to the message.</span></span> <span data-ttu-id="4afcd-109">XML ドキュメント スキーマにターゲットの名前空間がない場合は、ルート要素の名前がキーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="4afcd-109">If an XML document schema does not have a target namespace, BizTalk Server uses the name of the root element as a key.</span></span>  
  
## <a name="generating-a-schema"></a><span data-ttu-id="4afcd-110">スキーマの生成</span><span class="sxs-lookup"><span data-stu-id="4afcd-110">Generating a Schema</span></span>  
 <span data-ttu-id="4afcd-111">スキーマを生成する手順とターゲットの名前空間を設定する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4afcd-111">The following procedures show how to generate a schema and how to set the target namespace.</span></span>  
  
#### <a name="to-generate-a-schema-using-biztalk-editor"></a><span data-ttu-id="4afcd-112">BizTalk エディターを使用してスキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="4afcd-112">To generate a schema using BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="4afcd-113">BizTalk エディターで、プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="4afcd-113">In the BizTalk Editor, open your project.</span></span>  
  
2.  <span data-ttu-id="4afcd-114">ソリューション エクスプ ローラーで右上で、で **追加**、し、**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="4afcd-114">Under Solution Explorer in the upper-right, select **Add**, and then select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="4afcd-115">**テンプレート**ペインで、**スキーマの生成**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="4afcd-115">In the **Templates** pane, select **Generate Schemas**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="4afcd-116">**スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[**整形式 XML**です。</span><span class="sxs-lookup"><span data-stu-id="4afcd-116">In the **Generate Schemas** dialog box, in the **Document type** list, select **Well-Formed XML**.</span></span>  
  
5.  <span data-ttu-id="4afcd-117">をクリックして**参照**をクリックして、スキーマを生成する入力ファイルを検索する**OK**。</span><span class="sxs-lookup"><span data-stu-id="4afcd-117">Click **Browse** to locate the input file for which you want to generate a schema, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4afcd-118">次に、ターゲットの名前空間を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afcd-118">Next, you must set the target namespace.</span></span>  
  
#### <a name="to-set-the-target-namespace"></a><span data-ttu-id="4afcd-119">ターゲットの名前空間を設定するには</span><span class="sxs-lookup"><span data-stu-id="4afcd-119">To set the target namespace</span></span>  
  
1.  <span data-ttu-id="4afcd-120">BizTalk エディターで開き、スキーマ ファイルを右クリックして**\<スキーマ >**、し、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="4afcd-120">In BizTalk Editor, open your schema file, right-click **\<schema>**, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4afcd-121">**プロパティ** ウィンドウで、検索、 **Namespace**フィールド名を入力、たとえば、`testNameSpace`です。</span><span class="sxs-lookup"><span data-stu-id="4afcd-121">In the **Properties** pane, locate the **Namespace** field and type a name, for example, `testNameSpace`.</span></span>  
  
 <span data-ttu-id="4afcd-122">これで、メッセージを使用してオーケストレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="4afcd-122">You can then continue with your orchestration using messages.</span></span> <span data-ttu-id="4afcd-123">メッセージが取得されると、ターゲットの名前空間が設定されたスキーマを使用するオーケストレーションが BizTalk Server で検索され、オーケストレーション プロセスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4afcd-123">When a message is picked up, BizTalk Server finds an orchestration that uses a schema with a set target namespace, and the orchestration process is followed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afcd-124">参照</span><span class="sxs-lookup"><span data-stu-id="4afcd-124">See Also</span></span>  
 [<span data-ttu-id="4afcd-125">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="4afcd-125">Developing Applications</span></span>](../core/developing-applications5.md)