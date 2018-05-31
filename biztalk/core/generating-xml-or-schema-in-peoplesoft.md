---
title: PeopleSoft で XML またはスキーマを生成する |Microsoft ドキュメント
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
ms.openlocfilehash: 1a7fbd164f7c0d380f6ee0c0fda59098203f7585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246690"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="17ada-102">PeopleSoft での XML またはスキーマの生成</span><span class="sxs-lookup"><span data-stu-id="17ada-102">Generating XML or Schema in PeopleSoft</span></span>
<span data-ttu-id="17ada-103">次の手順では、PeopleSoft Enterprise を使用して、XML ファイルを作成し、PeopleSoft イベントをトリガーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="17ada-103">The following procedure describes how to use PeopleSoft Enterprise to create an XML file and trigger a PeopleSoft event.</span></span> <span data-ttu-id="17ada-104">これを行うには、PeopleSoft 環境の一部を変更します。</span><span class="sxs-lookup"><span data-stu-id="17ada-104">To do this, you change something in the PeopleSoft environment.</span></span> <span data-ttu-id="17ada-105">この変更によって XML ファイルがアクティブ化され、オーケストレーションで監視対象に設定したファイル フォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="17ada-105">The change activates an XML file, which is sent to the file folder that you set in your orchestration to be monitored.</span></span> <span data-ttu-id="17ada-106">その後、BizTalk Server で、XML をインポートしてスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="17ada-106">Later, in BizTalk Server, you import the XML and generate a schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17ada-107">この場所を MSEXTERNAL ノードと関連付けると、"Location Value" が変更された場合に、XML ドキュメントが生成され、イベントがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="17ada-107">When you associate the Location with the MSEXTERNAL node, any change made to Location Value generates an XML document—triggering an event.</span></span> <span data-ttu-id="17ada-108">オーケストレーションの参加および開始後は、PeopleSoft の画面から [LOCATION] 画面に移動できます。</span><span class="sxs-lookup"><span data-stu-id="17ada-108">After enlisting and starting your orchestration, you can navigate through the PeopleSoft screens to the LOCATION screen.</span></span> <span data-ttu-id="17ada-109">"Location Value" を変更し、その変更を保存すると、対応する XML が \out ディレクトリに現れます。</span><span class="sxs-lookup"><span data-stu-id="17ada-109">If you make a change to Location Value and save your change, a corresponding XML appears in your \out directory.</span></span>  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="17ada-110">PeopleSoft で XML またはスキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="17ada-110">To generate XML or Schema in PeopleSoft</span></span>  
  
1.  <span data-ttu-id="17ada-111">PeopleSoft アプリケーションをポイント**Set up Financials**、 をポイント**Supply Chain**、 をポイント**共通定義**、 をポイント**場所**、し、**場所**です。</span><span class="sxs-lookup"><span data-stu-id="17ada-111">In the PeopleSoft application, point to **Set up Financials**, point to **Supply Chain**, point to **Common Definitions**, point to **Location**, and then select **Location**.</span></span>  
  
2.  <span data-ttu-id="17ada-112">**場所**画面で、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="17ada-112">On the **Location** screen, enter the following information:</span></span>  
  
    -   <span data-ttu-id="17ada-113">**ID:** 入力**共有**です。</span><span class="sxs-lookup"><span data-stu-id="17ada-113">**Set ID:** Enter **SHARE**.</span></span>  
  
    -   <span data-ttu-id="17ada-114">**Location Code:** で始まるコードを入力`WKLOC`です。</span><span class="sxs-lookup"><span data-stu-id="17ada-114">**Location Code:** Enter a code that starts with `WKLOC`.</span></span>  
  
     ![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")  
  
3.  <span data-ttu-id="17ada-115">をクリックして**検索**、順にクリック**Correct History**に画面を記述する**編集**モード。</span><span class="sxs-lookup"><span data-stu-id="17ada-115">Click **Search**, and then click **Correct History** to put the screen in **Edit** mode.</span></span>  
  
     ![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")  
  
4.  <span data-ttu-id="17ada-116">クリックして、画面上のフィールドに変更を加える**保存**です。</span><span class="sxs-lookup"><span data-stu-id="17ada-116">Make a change to a field on the screen, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="17ada-117">をポイント**PeopleTools**、 をポイント**Integration Broker**、 をポイント**モニター**、し、 **Monitor Message**です。</span><span class="sxs-lookup"><span data-stu-id="17ada-117">Point to **PeopleTools**, point to **Integration Broker**, point to **Monitor**, and then select **Monitor Message**.</span></span>  
  
     ![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")  
  
6.  <span data-ttu-id="17ada-118">確認して**チャネルの種類**は**メッセージ インスタンス**、クリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="17ada-118">Make sure that **Channel Type** is **Message Instance**, and then click **Refresh**.</span></span>  
  
7.  <span data-ttu-id="17ada-119">**実行** 列番号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17ada-119">In the **Done** column, click the number.</span></span>  
  
8.  <span data-ttu-id="17ada-120">一覧の一番下までスクロールし、**詳細**リンクを**LOCATION_SYNC**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="17ada-120">Scroll to the bottom of the list and click the **Details** link on a **LOCATION_SYNC** message.</span></span>  
  
     ![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")  
  
9. <span data-ttu-id="17ada-121">をクリックして**XML を表示**上、 **MSEXTERNAL**ノード。</span><span class="sxs-lookup"><span data-stu-id="17ada-121">Click **View XML** on a **MSEXTERNAL** Node.</span></span>  
  
     ![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")  
  
     <span data-ttu-id="17ada-122">XML の内容をコピーし、BizTalk Server プロジェクトからアクセスできるファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="17ada-122">Copy and paste the contents of the XML into a file that can be accessed by your BizTalk Server project.</span></span>  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. <span data-ttu-id="17ada-123">BizTalk Server から参照することになるので、このファイルの場所を忘れないようにします。</span><span class="sxs-lookup"><span data-stu-id="17ada-123">Remember the location of the file;  you reference it in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17ada-124">参照</span><span class="sxs-lookup"><span data-stu-id="17ada-124">See Also</span></span>  
 [<span data-ttu-id="17ada-125">付録 b: PeopleSoft アプリケーションの使用</span><span class="sxs-lookup"><span data-stu-id="17ada-125">Appendix B: Using the PeopleSoft Application</span></span>](../core/appendix-b-using-the-peoplesoft-application.md)