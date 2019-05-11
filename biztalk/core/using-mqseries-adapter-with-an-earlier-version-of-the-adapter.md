---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 38711ace8fd2c1ea328edc2ba8d4ecf83a320070
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396802"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="db200-101">MQSeries アダプターを使用して、アダプターの以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="db200-101">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="db200-102">MQSeries アダプターの異なるバージョンの BizTalk Server のすべてで使用できます、同じリモート WebSphere MQ Server Windows。</span><span class="sxs-lookup"><span data-stu-id="db200-102">The different BizTalk Server versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="db200-103">次のバージョンの MQSeries アダプタで使用される COM + アプリケーションが同じ WebSphere MQSeries コンピュータに共存できるため、このことはできます。</span><span class="sxs-lookup"><span data-stu-id="db200-103">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="db200-104">**MQSAgent (MQSAgent2) COM + アプリケーション**MQSeries アダプター (BizTalk Server 2006) の使用</span><span class="sxs-lookup"><span data-stu-id="db200-104">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter (BizTalk Server 2006)</span></span> 
  
-   <span data-ttu-id="db200-105">**MQSAgent COM + アプリケーション**MQSeries アダプター (BizTalk Server 2004) の使用</span><span class="sxs-lookup"><span data-stu-id="db200-105">**MQSAgent COM+ application** used with the MQSeries Adapter (BizTalk Server 2004)</span></span>  
  
-   <span data-ttu-id="db200-106">**MQHelper COM + アプリケーション**MQSeries アダプター (BizTalk Server 2002) で使用</span><span class="sxs-lookup"><span data-stu-id="db200-106">**MQHelper COM+ application** used with the MQSeries Adapter (BizTalk Server 2002)</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="db200-107">これらの COM + アプリケーションのサイド バイ サイドでインストールを構成する場合は、同じ MQSeries キューを使用してこれらの COM + アプリケーションの構成をされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db200-107">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="db200-108">MQSeries アダプタ COM + アプリケーションの以前のバージョンでは、MQSeries アダプタ COM + アプリケーションの BizTalk Server 2006 バージョンのサイド バイ サイドでインストールが、WebSphere の以前のバージョンの BizTalk Server がインストールされていない場合にのみサポートされていますMQSeries コンピュータ。</span><span class="sxs-lookup"><span data-stu-id="db200-108">Side-by-side installation of the BizTalk Server 2006 version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="db200-109">以前のバージョンの MQSeries アダプタ COM + アプリケーションを実行している WebSphere MQSeries コンピュータに BizTalk Server 2006 バージョンの MQSeries アダプタ COM + アプリケーションをインストールするには</span><span class="sxs-lookup"><span data-stu-id="db200-109">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="db200-110">依存関係ファイル MSVCR80.dll および MSVCP80.dll を WebSphere MQSeries コンピュータにコピーするには、BizTalk Server 2006 CD の \Platform\BootStrap\ ディレクトリから Bootstrap.msi を実行します。</span><span class="sxs-lookup"><span data-stu-id="db200-110">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the BizTalk Server 2006 CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="db200-111">WebSphere MQSeries コンピュータに、BizTalk Server 2006 CD の \Msi\Program Files\ ディレクトリから MQSAgent.dll ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="db200-111">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the BizTalk Server 2006 CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db200-112">MQSTrace.cmd ファイルこのディレクトリからにコピー WebSphere MQSeries コンピュータ MQSAgent トレース ユーティリティを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="db200-112">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="db200-113">詳細については、MQSAgent トレース ユーティリティを参照してください[MQSeries アダプター エラーの分析トレース ツールを使用して](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)します。</span><span class="sxs-lookup"><span data-stu-id="db200-113">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="db200-114">WebSphere MQSeries コンピュータで regsvr32 mqsagent.dll を実行して、MQSAgent.dll にコンポーネントを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="db200-114">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="db200-115">MQSAgent.dll のコピーを同じディレクトリから、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="db200-115">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="db200-116">MQSAgent コンポーネントの新しい COM + アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="db200-116">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="db200-117">COM + アプリケーションを右クリックし、をクリックして**新規**、**アプリケーション**を表示する、 **COM + アプリケーション インストール ウィザード** をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="db200-117">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="db200-118">クリックして**空のアプリケーションを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="db200-118">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="db200-119">名前を入力します**MQSAgent2**の既定のオプションのままに**サーバー アプリケーション**有効になっており、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="db200-119">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="db200-120">オプションを選択**このユーザー**、適切なアカウント情報を入力し、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="db200-120">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="db200-121">このアカウントが必要接続し、配置や適切な IBM WebSphere MQ キューのアクセス許可を取得します。</span><span class="sxs-lookup"><span data-stu-id="db200-121">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="db200-122">クリックして**次**の追加**アプリケーション ロール** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="db200-122">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="db200-123">をクリックして**次へ**上、**ロールにユーザーの追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="db200-123">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="db200-124">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db200-124">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="db200-125">MQSAgent.dll コンポーネントを MQSAgent2 COM + アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="db200-125">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="db200-126">クリックして展開し、 **MQSAgent2** COM + アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="db200-126">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="db200-127">右クリック**コンポーネント** をクリック**新規**、**コンポーネント**を COM + コンポーネント インストール ウィザードを起動し、をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="db200-127">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="db200-128">クリックして**新しいコンポーネントのインストール**MQSAgent.dll ファイルを参照し、をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="db200-128">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="db200-129">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db200-129">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db200-130">参照</span><span class="sxs-lookup"><span data-stu-id="db200-130">See Also</span></span>  
 [<span data-ttu-id="db200-131">MQSeries アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="db200-131">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)