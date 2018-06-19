---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2aa74be2d86bcb8f32661fdcf06727eb6391861d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710709"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="262a9-101">MQSeries アダプターを使用して、アダプターの以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="262a9-101">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="262a9-102">MQSeries アダプターの異なるバージョンの BizTalk Server のすべてで、作業できる、同じリモートの WebSphere MQ Server Windows です。</span><span class="sxs-lookup"><span data-stu-id="262a9-102">The different BizTalk Server versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="262a9-103">このことが可能なのは、MQSeries アダプタで使用されている次のバージョンの COM+ アプリケーションを、同一の WebSphere MQSeries コンピュータ上に共存させることができるためです。</span><span class="sxs-lookup"><span data-stu-id="262a9-103">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="262a9-104">**MQSAgent (MQSAgent2) COM + アプリケーション**MQSeries アダプター (BizTalk Server 2006) の使用</span><span class="sxs-lookup"><span data-stu-id="262a9-104">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter (BizTalk Server 2006)</span></span> 
  
-   <span data-ttu-id="262a9-105">**MQSAgent COM + アプリケーション**MQSeries アダプター (BizTalk Server 2004) と使用</span><span class="sxs-lookup"><span data-stu-id="262a9-105">**MQSAgent COM+ application** used with the MQSeries Adapter (BizTalk Server 2004)</span></span>  
  
-   <span data-ttu-id="262a9-106">**MQHelper COM + アプリケーション**MQSeries アダプター (BizTalk Server 2002) の使用</span><span class="sxs-lookup"><span data-stu-id="262a9-106">**MQHelper COM+ application** used with the MQSeries Adapter (BizTalk Server 2002)</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="262a9-107">上記の COM+ アプリケーションの並列インストールを構成する場合は、各 COM+ アプリケーションが別の MQSeries キューを使用するように構成してください。</span><span class="sxs-lookup"><span data-stu-id="262a9-107">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="262a9-108">MQSeries アダプタ COM + アプリケーションの以前のバージョンで、MQSeries アダプタ COM + アプリケーションの BizTalk Server 2006 バージョンをサイド バイ サイド インストールは、WebSphere に BizTalk Server の以前のバージョンがインストールされていない場合にのみサポートします。MQSeries コンピュータ。</span><span class="sxs-lookup"><span data-stu-id="262a9-108">Side-by-side installation of the BizTalk Server 2006 version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="262a9-109">以前のバージョンの MQSeries アダプタ COM+ アプリケーションを実行している WebSphere MQSeries コンピュータに MQSeries アダプタ COM+ アプリケーションの BizTalk Server 2006 バージョンをインストールするには</span><span class="sxs-lookup"><span data-stu-id="262a9-109">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="262a9-110">依存関係ファイル MSVCR80.dll および MSVCP80.dll を WebSphere MQSeries コンピュータにコピーするには、BizTalk Server 2006 CD の \Platform\BootStrap\ ディレクトリから Bootstrap.msi を実行します。</span><span class="sxs-lookup"><span data-stu-id="262a9-110">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the BizTalk Server 2006 CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="262a9-111">WebSphere MQSeries コンピュータに BizTalk Server 2006 CD 上の \Msi\Program Files\ ディレクトリから MQSAgent.dll ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="262a9-111">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the BizTalk Server 2006 CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="262a9-112">MQSAgent トレース ユーティリティを使用する予定がある場合は、このディレクトリから MQSTrace.cmd ファイルも WebSphere MQSeries コンピュータにコピーします。</span><span class="sxs-lookup"><span data-stu-id="262a9-112">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="262a9-113">詳細については、MQSAgent トレース ユーティリティを参照してください[トレース ツールを使用して MQSeries アダプター エラーを分析する](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)です。</span><span class="sxs-lookup"><span data-stu-id="262a9-113">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="262a9-114">次の手順に従い、WebSphere MQSeries コンピュータで regsvr32 mqsagent.dll を実行し、MQSAgent.dll にコンポーネントを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="262a9-114">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="262a9-115">MQSAgent.dll のコピー先と同じディレクトリからこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="262a9-115">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="262a9-116">次の手順に従い、MQSAgent コンポーネント用の新しい COM+ アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="262a9-116">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="262a9-117">COM + アプリケーションを右クリックし、クリックして **新規**, 、**アプリケーション** を表示する、 **COM + アプリケーション インストール ウィザード**  をクリック **次**します。</span><span class="sxs-lookup"><span data-stu-id="262a9-117">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="262a9-118">クリックして **空のアプリケーションを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="262a9-118">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="262a9-119">名前を入力します **MQSAgent2**, の既定のオプションのままにして **サーバー アプリケーション** 有効になっており、クリックして **次**します。</span><span class="sxs-lookup"><span data-stu-id="262a9-119">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="262a9-120">オプションを選択する **このユーザー**, 、適切なアカウント情報を入力し、クリックして **次**します。</span><span class="sxs-lookup"><span data-stu-id="262a9-120">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="262a9-121">このアカウントは、適切な IBM WebSphere MQ キューに対し、CONNECT 権限と、PUT または GET (あるいはその両方) の権限を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="262a9-121">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="262a9-122">をクリックして **次** 追加 **アプリケーション ロール**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="262a9-122">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="262a9-123">をクリックして **次** 上、 **にユーザー ロールを追加**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="262a9-123">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="262a9-124">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="262a9-124">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="262a9-125">次の手順に従い、MQSAgent.dll コンポーネントを MQSAgent2 COM+ アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="262a9-125">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="262a9-126">クリックして展開し、 **MQSAgent2** COM + アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="262a9-126">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="262a9-127">右クリック **コンポーネント**  をクリック **新規**, 、**コンポーネント** を COM + コンポーネント インストール ウィザードを起動し、をクリックし、 **次**します。</span><span class="sxs-lookup"><span data-stu-id="262a9-127">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="262a9-128">クリックして **新しいコンポーネントのインストール**, を MQSAgent.dll ファイルを参照してクリックして **開く**します。</span><span class="sxs-lookup"><span data-stu-id="262a9-128">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="262a9-129">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="262a9-129">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262a9-130">参照</span><span class="sxs-lookup"><span data-stu-id="262a9-130">See Also</span></span>  
 [<span data-ttu-id="262a9-131">MQSeries アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="262a9-131">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)