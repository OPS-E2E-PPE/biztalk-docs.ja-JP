---
title: "MQSeries アダプターを使用して、アダプターの以前のバージョンと |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, compatibility
ms.assetid: 278a13ff-8e46-4af4-a76e-b6d4aad5b768
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba635b9bc4569f17418fc925c54c64d0fdc67461
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="a18c8-102">MQSeries アダプターを使用して、アダプターの以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="a18c8-102">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="a18c8-103">[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]、および [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] バージョンの MQSeries アダプタはすべて、Windows 上の同一のリモート WebSphere MQ サーバーで動作します。</span><span class="sxs-lookup"><span data-stu-id="a18c8-103">The [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)], [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)], and [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="a18c8-104">このことが可能なのは、MQSeries アダプタで使用されている次のバージョンの COM+ アプリケーションを、同一の WebSphere MQSeries コンピュータ上に共存させることができるためです。</span><span class="sxs-lookup"><span data-stu-id="a18c8-104">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="a18c8-105">**MQSAgent (MQSAgent2) COM + アプリケーション**の MQSeries アダプタで使用される[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-105">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span></span>  
  
-   <span data-ttu-id="a18c8-106">**MQSAgent COM + アプリケーション**の MQSeries アダプタで使用される[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-106">**MQSAgent COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)].</span></span>  
  
-   <span data-ttu-id="a18c8-107">**MQHelper COM + アプリケーション**の MQSeries アダプタで使用される[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-107">**MQHelper COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a18c8-108">上記の COM+ アプリケーションの並列インストールを構成する場合は、各 COM+ アプリケーションが別の MQSeries キューを使用するように構成してください。</span><span class="sxs-lookup"><span data-stu-id="a18c8-108">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a18c8-109">MQSeries アダプタ COM+ アプリケーションの [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] バージョンと、以前のバージョンの MQSeries アダプタ COM+ アプリケーションの並列インストールは、以前のバージョンの BizTalk Server が WebSphere MQSeries コンピュータにインストールされていない場合にのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a18c8-109">Side-by-side installation of the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="a18c8-110">以前のバージョンの MQSeries アダプタ COM+ アプリケーションを実行している WebSphere MQSeries コンピュータに MQSeries アダプタ COM+ アプリケーションの BizTalk Server 2006 バージョンをインストールするには</span><span class="sxs-lookup"><span data-stu-id="a18c8-110">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="a18c8-111">[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD の \Platform\BootStrap\ ディレクトリから Bootstrap.msi を実行し、依存関係ファイル MSVCR80.dll および MSVCP80.dll を WebSphere MQSeries コンピュータにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a18c8-111">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="a18c8-112">[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD の \Msi\Program Files\ ディレクトリから MQSAgent.dll ファイルを WebSphere MQSeries コンピュータにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a18c8-112">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a18c8-113">MQSAgent トレース ユーティリティを使用する予定がある場合は、このディレクトリから MQSTrace.cmd ファイルも WebSphere MQSeries コンピュータにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a18c8-113">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="a18c8-114">詳細については、MQSAgent トレース ユーティリティを参照してください[トレース ツールを使用して MQSeries アダプター エラーを分析する](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-114">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="a18c8-115">次の手順に従い、WebSphere MQSeries コンピュータで regsvr32 mqsagent.dll を実行し、MQSAgent.dll にコンポーネントを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="a18c8-115">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a18c8-116">MQSAgent.dll のコピー先と同じディレクトリからこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a18c8-116">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="a18c8-117">次の手順に従い、MQSAgent コンポーネント用の新しい COM+ アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a18c8-117">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="a18c8-118">COM + アプリケーションを右クリックし、をクリックして**新規**、**アプリケーション**を表示する、 **COM + アプリケーション インストール ウィザード** をクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-118">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="a18c8-119">をクリックして**空のアプリケーションを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-119">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="a18c8-120">名前を入力します**MQSAgent2**の既定のオプションのままにして**サーバー アプリケーション**有効になっており、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-120">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="a18c8-121">オプションを選択**このユーザー**、適切なアカウント情報を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-121">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a18c8-122">このアカウントは、適切な IBM WebSphere MQ キューに対し、CONNECT 権限と、PUT または GET (あるいはその両方) の権限を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="a18c8-122">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="a18c8-123">をクリックして**次**の追加**アプリケーション ロール** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a18c8-123">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="a18c8-124">をクリックして**次へ**上、**ロールにユーザーの追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a18c8-124">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="a18c8-125">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18c8-125">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="a18c8-126">次の手順に従い、MQSAgent.dll コンポーネントを MQSAgent2 COM+ アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a18c8-126">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="a18c8-127">クリックして展開し、 **MQSAgent2** COM + アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="a18c8-127">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="a18c8-128">右クリック**コンポーネント** をクリック**新規**、**コンポーネント**COM + コンポーネント インストール ウィザードを起動し、をクリックする**次**です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-128">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="a18c8-129">をクリックして**新しいコンポーネントのインストール**MQSAgent.dll ファイルを参照し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="a18c8-129">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="a18c8-130">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18c8-130">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a18c8-131">参照</span><span class="sxs-lookup"><span data-stu-id="a18c8-131">See Also</span></span>  
 [<span data-ttu-id="a18c8-132">MQSeries アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="a18c8-132">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)