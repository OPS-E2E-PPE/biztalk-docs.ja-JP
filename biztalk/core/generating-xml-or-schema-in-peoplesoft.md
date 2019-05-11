---
title: PeopleSoft で XML またはスキーマの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- generating XML
- XML, generating
ms.assetid: adfe2936-0dc2-42d2-b26a-718f8cc57eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3046a6cb3dc90db69d7d113bf08b92d8c4606bab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387754"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="8875a-102">PeopleSoft で XML またはスキーマの生成</span><span class="sxs-lookup"><span data-stu-id="8875a-102">Generating XML or Schema in PeopleSoft</span></span>
<span data-ttu-id="8875a-103">次の手順では、PeopleSoft Enterprise を使用して XML ファイルを作成し、PeopleSoft イベントをトリガーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8875a-103">The following procedure describes how to use PeopleSoft Enterprise to create an XML file and trigger a PeopleSoft event.</span></span> <span data-ttu-id="8875a-104">これを行うには、PeopleSoft 環境で何かを変更します。</span><span class="sxs-lookup"><span data-stu-id="8875a-104">To do this, you change something in the PeopleSoft environment.</span></span> <span data-ttu-id="8875a-105">変更は、監視するために、オーケストレーションで設定ファイルのフォルダーに送信される XML ファイルをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="8875a-105">The change activates an XML file, which is sent to the file folder that you set in your orchestration to be monitored.</span></span> <span data-ttu-id="8875a-106">後で BizTalk server の XML をインポートし、スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="8875a-106">Later, in BizTalk Server, you import the XML and generate a schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8875a-107">場所の値に加えられた変更が XML ドキュメントを生成する場所を MSEXTERNAL ノードに関連付けると、イベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="8875a-107">When you associate the Location with the MSEXTERNAL node, any change made to Location Value generates an XML document—triggering an event.</span></span> <span data-ttu-id="8875a-108">参加と、オーケストレーションの開始、場所の画面に、PeopleSoft の画面間を移動できます。</span><span class="sxs-lookup"><span data-stu-id="8875a-108">After enlisting and starting your orchestration, you can navigate through the PeopleSoft screens to the LOCATION screen.</span></span> <span data-ttu-id="8875a-109">場所の値に変更を加える変更を保存して、対応する XML が \out ディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8875a-109">If you make a change to Location Value and save your change, a corresponding XML appears in your \out directory.</span></span>  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="8875a-110">PeopleSoft で XML またはスキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="8875a-110">To generate XML or Schema in PeopleSoft</span></span>  
  
1. <span data-ttu-id="8875a-111">PeopleSoft アプリケーションでポイントして**Set up Financials**、 をポイント**Supply Chain**、 をポイント**共通定義**、 をポイント**場所**、し、**場所**します。</span><span class="sxs-lookup"><span data-stu-id="8875a-111">In the PeopleSoft application, point to **Set up Financials**, point to **Supply Chain**, point to **Common Definitions**, point to **Location**, and then select **Location**.</span></span>  
  
2. <span data-ttu-id="8875a-112">**場所**画面で、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8875a-112">On the **Location** screen, enter the following information:</span></span>  
  
   - <span data-ttu-id="8875a-113">**ID を設定します。** 入力**共有**します。</span><span class="sxs-lookup"><span data-stu-id="8875a-113">**Set ID:** Enter **SHARE**.</span></span>  
  
   - <span data-ttu-id="8875a-114">**Location Code:** 始まるコードを入力`WKLOC`します。</span><span class="sxs-lookup"><span data-stu-id="8875a-114">**Location Code:** Enter a code that starts with `WKLOC`.</span></span>  
  
     <span data-ttu-id="8875a-115">![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")</span><span class="sxs-lookup"><span data-stu-id="8875a-115">![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")</span></span>  
  
3. <span data-ttu-id="8875a-116">クリックして**検索**、順にクリックします**Correct History**して画面を**編集**モード。</span><span class="sxs-lookup"><span data-stu-id="8875a-116">Click **Search**, and then click **Correct History** to put the screen in **Edit** mode.</span></span>  
  
    <span data-ttu-id="8875a-117">![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")</span><span class="sxs-lookup"><span data-stu-id="8875a-117">![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")</span></span>  
  
4. <span data-ttu-id="8875a-118">クリックして、画面上のフィールドに変更を加える**保存**します。</span><span class="sxs-lookup"><span data-stu-id="8875a-118">Make a change to a field on the screen, and then click **Save**.</span></span>  
  
5. <span data-ttu-id="8875a-119">をポイント**PeopleTools**、 をポイント**Integration Broker**、 をポイント**モニター**、し、**メッセージの監視**します。</span><span class="sxs-lookup"><span data-stu-id="8875a-119">Point to **PeopleTools**, point to **Integration Broker**, point to **Monitor**, and then select **Monitor Message**.</span></span>  
  
    <span data-ttu-id="8875a-120">![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")</span><span class="sxs-lookup"><span data-stu-id="8875a-120">![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")</span></span>  
  
6. <span data-ttu-id="8875a-121">確認します**チャネルの種類**は**メッセージ インスタンス**、 をクリックし、**更新**します。</span><span class="sxs-lookup"><span data-stu-id="8875a-121">Make sure that **Channel Type** is **Message Instance**, and then click **Refresh**.</span></span>  
  
7. <span data-ttu-id="8875a-122">**完了**列番号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8875a-122">In the **Done** column, click the number.</span></span>  
  
8. <span data-ttu-id="8875a-123">リストの一番下までスクロールし、**詳細**リンクを**LOCATION_SYNC**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="8875a-123">Scroll to the bottom of the list and click the **Details** link on a **LOCATION_SYNC** message.</span></span>  
  
    <span data-ttu-id="8875a-124">![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")</span><span class="sxs-lookup"><span data-stu-id="8875a-124">![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")</span></span>  
  
9. <span data-ttu-id="8875a-125">をクリックして**XML を表示**上、 **MSEXTERNAL**ノード。</span><span class="sxs-lookup"><span data-stu-id="8875a-125">Click **View XML** on a **MSEXTERNAL** Node.</span></span>  
  
     <span data-ttu-id="8875a-126">![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")</span><span class="sxs-lookup"><span data-stu-id="8875a-126">![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")</span></span>  
  
     <span data-ttu-id="8875a-127">コピーして、BizTalk Server プロジェクトでアクセスできるファイルに XML の内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8875a-127">Copy and paste the contents of the XML into a file that can be accessed by your BizTalk Server project.</span></span>  
  
     <span data-ttu-id="8875a-128">![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")</span><span class="sxs-lookup"><span data-stu-id="8875a-128">![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")</span></span>  
  
10. <span data-ttu-id="8875a-129">は、ファイルの場所を忘れないでください BizTalk Server で参照します。</span><span class="sxs-lookup"><span data-stu-id="8875a-129">Remember the location of the file;  you reference it in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8875a-130">参照</span><span class="sxs-lookup"><span data-stu-id="8875a-130">See Also</span></span>  
 [<span data-ttu-id="8875a-131">付録 b:PeopleSoft アプリケーションの使用</span><span class="sxs-lookup"><span data-stu-id="8875a-131">Appendix B: Using the PeopleSoft Application</span></span>](../core/appendix-b-using-the-peoplesoft-application.md)