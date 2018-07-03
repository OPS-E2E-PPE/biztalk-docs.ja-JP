---
title: Power BI を有効にする |Microsoft Docs
description: Power BI テンプレートを BizTalk Server の Feature Pack のインストールします。
ms.custom: fp1
ms.date: 6/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bfe842e3b131e6b0fcde75485c1d472320644c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994179"
---
# <a name="configure-the-power-bi-operational-data-feed-in-biztalk-server"></a><span data-ttu-id="f0c24-103">Power BI にオペレーション データ フィードでは、BizTalk Server の構成します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-103">Configure the Power BI operational data feed in BizTalk Server</span></span>

<span data-ttu-id="f0c24-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 追跡を指定すると、Power BI テンプレートを使用して Power BI に送信します。 または、独自に作成します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, send tracking to Power BI using the Power BI template provided, or create your own.</span></span> 

## <a name="what-is-operational-data"></a><span data-ttu-id="f0c24-105">オペレーション データとは</span><span class="sxs-lookup"><span data-stu-id="f0c24-105">What is operational data</span></span>
<span data-ttu-id="f0c24-106">オペレーション データは、インスタンスとで転送されるメッセージについては、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="f0c24-106">Operational data is information on the instances and messages flowing through your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="f0c24-107">オペレーション データ フィードは、同じデータのグループのハブを見て取得[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-107">The operational data feed is the same data you get looking at Group Hub in [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="f0c24-108">データにアクセスし、Power BI などの視覚化ツールを使用してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-108">The data is accessed and queried using visualization tools, including Power BI.</span></span> 

<span data-ttu-id="f0c24-109">フィードには、次のデータ テーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0c24-109">The feed includes the following data tables:</span></span>
* <span data-ttu-id="f0c24-110">アプリケーション データ</span><span class="sxs-lookup"><span data-stu-id="f0c24-110">Application data</span></span>
* <span data-ttu-id="f0c24-111">AS2 状態レコード</span><span class="sxs-lookup"><span data-stu-id="f0c24-111">AS2 Status Records</span></span>
* <span data-ttu-id="f0c24-112">バッチ処理の情報</span><span class="sxs-lookup"><span data-stu-id="f0c24-112">Batching information</span></span>
* <span data-ttu-id="f0c24-113">インスタンス情報</span><span class="sxs-lookup"><span data-stu-id="f0c24-113">Instance information</span></span>
* <span data-ttu-id="f0c24-114">インターチェンジの集計レコード</span><span class="sxs-lookup"><span data-stu-id="f0c24-114">Interchange Aggregations Records</span></span>
* <span data-ttu-id="f0c24-115">インターチェンジの状態レコード</span><span class="sxs-lookup"><span data-stu-id="f0c24-115">Interchange Status Records</span></span>
* <span data-ttu-id="f0c24-116">メッセージ</span><span class="sxs-lookup"><span data-stu-id="f0c24-116">Messages</span></span>
* <span data-ttu-id="f0c24-117">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="f0c24-117">Subscriptions</span></span>
* <span data-ttu-id="f0c24-118">追跡したイベント</span><span class="sxs-lookup"><span data-stu-id="f0c24-118">Tracked Events</span></span>
* <span data-ttu-id="f0c24-119">トランザクションのレポート</span><span class="sxs-lookup"><span data-stu-id="f0c24-119">Transaction reports</span></span>
* <span data-ttu-id="f0c24-120">トランザクション セット</span><span class="sxs-lookup"><span data-stu-id="f0c24-120">Transaction sets</span></span>

> [!TIP]
> <span data-ttu-id="f0c24-121">[PowerBI.com](http://powerbi.microsoft.com)優れたリソースを理解し、Power BI の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-121">[PowerBI.com](http://powerbi.microsoft.com) is a great resource to understand and learn more about Power BI.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0c24-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="f0c24-122">Prerequisites</span></span>
* <span data-ttu-id="f0c24-123">ダウンロードしてインストール[Power BI Desktop](https://powerbi.microsoft.com/desktop/)にネットワーク アクセス権を持つ任意のコンピューターで、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c24-123">Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on any computer that has network access to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="f0c24-124">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)、またはそれ以降の機能パックを [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c24-124">Install [Feature Pack 2](https://aka.ms/bts2016fp2), or newer feature pack, on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="f0c24-125">IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-125">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f0c24-126">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f0c24-126">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="f0c24-127">参照してください[BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-127">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> <span data-ttu-id="f0c24-128">開くことで IIS がインストールされていることを確認します。**インターネット インフォメーション サービス マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-128">Confirm IIS is installed by opening **Internet Information Services Manager**.</span></span> 
* <span data-ttu-id="f0c24-129">任意。</span><span class="sxs-lookup"><span data-stu-id="f0c24-129">Optional.</span></span> <span data-ttu-id="f0c24-130">インストールし、構成、 [Power BI Gateway](https://powerbi.microsoft.com/gateway/)接続[PowerBI.com](http://powerbi.microsoft.com)オンプレミスの BizTalk Server とします。</span><span class="sxs-lookup"><span data-stu-id="f0c24-130">Install and configure a [Power BI Gateway](https://powerbi.microsoft.com/gateway/) to connect [PowerBI.com](http://powerbi.microsoft.com) with your on-premises BizTalk Server.</span></span> <span data-ttu-id="f0c24-131">オンプレミスの BizTalk Server を使用していない場合は、ゲートウェイを必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f0c24-131">If you're not using an on-premises BizTalk Server, then you don't need the gateway.</span></span>

## <a name="step-1-enable-operational-data"></a><span data-ttu-id="f0c24-132">手順 1: オペレーション データを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0c24-132">Step 1: Enable operational data</span></span>

1. <span data-ttu-id="f0c24-133">Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、を右クリックしてし選択、**管理者として実行**)。</span><span class="sxs-lookup"><span data-stu-id="f0c24-133">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="f0c24-134">BizTalk インストール フォルダーに移動して (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。</span><span class="sxs-lookup"><span data-stu-id="f0c24-134">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="f0c24-135">次のテキストで置換`Default Web Site`、 `operationalDataServiceAppPool`、 `domain\user`、 `password`、および`domain\group`の値。</span><span class="sxs-lookup"><span data-stu-id="f0c24-135">In the following text, replace `Default Web Site`, `operationalDataServiceAppPool`, `domain\user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user\> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1\>, <domain>\<group2\>, <domain>\<user\>, <domain>\<user2\>'
    ```

   * <span data-ttu-id="f0c24-136">**サービス**: サービスを構成できます (**OperationalData** Power BI 用)</span><span class="sxs-lookup"><span data-stu-id="f0c24-136">**Service**: The service to be configured (**OperationalData** for Power BI)</span></span>
   * <span data-ttu-id="f0c24-137">**WebSiteName**: サービスをホストする既存の IIS web サイト。</span><span class="sxs-lookup"><span data-stu-id="f0c24-137">**WebSiteName**: The existing IIS web site that hosts the service.</span></span> <span data-ttu-id="f0c24-138">既定値は**既定の Web サイト**します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-138">The default value is **Default Web Site**.</span></span>
   * <span data-ttu-id="f0c24-139">**ApplicationPool**: アプリケーション プールがサービスで使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-139">**ApplicationPool**: The Application Pool used by the service.</span></span> <span data-ttu-id="f0c24-140">存在する場合、新しいものは作成されません。</span><span class="sxs-lookup"><span data-stu-id="f0c24-140">If it exists, a new one is not created.</span></span> <span data-ttu-id="f0c24-141">既定値は**DefaultAppPool**します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-141">The default value is **DefaultAppPool**.</span></span>
   * <span data-ttu-id="f0c24-142">**ApplicationPoolUser**: このユーザー id として実行するアプリケーション プールを構成します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-142">**ApplicationPoolUser**: Configures the application pool to run as this user identity.</span></span> <span data-ttu-id="f0c24-143">BizTalk Server Operator、またはより高い権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0c24-143">Must have BizTalk Server Operator, or higher privileges.</span></span>
   * <span data-ttu-id="f0c24-144">**ApplicationPoolUserPassword**: ApplicationPoolUser のパスワード</span><span class="sxs-lookup"><span data-stu-id="f0c24-144">**ApplicationPoolUserPassword**: Password for the ApplicationPoolUser</span></span>
   * <span data-ttu-id="f0c24-145">**AuthorizationAccount**: 承認済みのグループまたはこのサービスを使用できるユーザーの一覧</span><span class="sxs-lookup"><span data-stu-id="f0c24-145">**AuthorizationAccount**: List of authorized Groups or Users that can use this service</span></span>

     <span data-ttu-id="f0c24-146">次の例では使用して、 `Default Web Site`、という名前のアプリケーション プールを作成`PowerBIAppPool`、として appPool を実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`し、ユーザー アカウントのパスワードとして、`BizTalk Server Administrators`アクセス許可をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-146">In the following example, we use the `Default Web Site`, create an application pool named `PowerBIAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the `BizTalk Server Administrators` group permissions.</span></span> <span data-ttu-id="f0c24-147">次を入力してください、周囲の値にスペースが引用符など、1 つ。</span><span class="sxs-lookup"><span data-stu-id="f0c24-147">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

     ```Powershell
     FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
     ```

     <span data-ttu-id="f0c24-148">完了したら、IIS 内で BizTalkOperationalDataService アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0c24-148">When complete, the BizTalkOperationalDataService application is created within IIS:</span></span>  
     ![BizTalkMOperationalDataServer アプリケーション](../core/media/biztalkmanagementservice-apppool.png)


4. <span data-ttu-id="f0c24-150">参照するには、動作していることを確認するに`http://localhost/BizTalkOperationalDataService`します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-150">To confirm it’s working, browse to `http://localhost/BizTalkOperationalDataService`.</span></span> 

    <span data-ttu-id="f0c24-151">サインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインを求められるかどうか (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。</span><span class="sxs-lookup"><span data-stu-id="f0c24-151">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

    <span data-ttu-id="f0c24-152">開くか保存 BizTalkOperationalDataService.json メッセージが表示されたら、インストールが完了します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-152">If you are prompted to open or save BizTalkOperationalDataService.json, then your install completed.</span></span> <span data-ttu-id="f0c24-153">ローカルに保存してメモ帳などの内容を表示する Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="f0c24-153">You can save it locally, and then open it in notepad or Visual Studio to see the contents.</span></span> 

> [!WARNING]
> <span data-ttu-id="f0c24-154">IIS で BizTalkOperationalDataService アプリケーションでは、web.config ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-154">The BizTalkOperationalDataService application in IIS uses a web.config file.</span></span> <span data-ttu-id="f0c24-155">Web.config 内の要素**大文字と小文字は**します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-155">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="f0c24-156">Windows PowerShell スクリプトを実行するときに必ずに正しい文字を入力する`-AuthorizationRoles`値。</span><span class="sxs-lookup"><span data-stu-id="f0c24-156">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="f0c24-157">ケースのことを確認していない場合は、次に確認する簡単な方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-157">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="f0c24-158">開いている**コンピュータの管理**、展開と**ローカル ユーザーとグループ**します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-158">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="f0c24-159">選択**グループ**、まで下へスクロールし、 **SQLServer.**</span><span class="sxs-lookup"><span data-stu-id="f0c24-159">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="f0c24-160">グループ。</span><span class="sxs-lookup"><span data-stu-id="f0c24-160">groups.</span></span> 
> 3. <span data-ttu-id="f0c24-161">次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。</span><span class="sxs-lookup"><span data-stu-id="f0c24-161">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="f0c24-162">すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-162">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![すべて大文字でコンピューター名には](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a><span data-ttu-id="f0c24-164">手順 2: Power BI でテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-164">Step 2: Use the template in Power BI</span></span>

1. <span data-ttu-id="f0c24-165">ダウンロードしてインストール、 [Power BI Desktop](https://powerbi.microsoft.com/desktop/) BizTalk Server にします。</span><span class="sxs-lookup"><span data-stu-id="f0c24-165">Download and install the [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on your BizTalk Server.</span></span> <span data-ttu-id="f0c24-166">これは省略可能なを開くを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f0c24-166">You can select to open it, which is optional.</span></span> <span data-ttu-id="f0c24-167">職場または学校のアカウントがあれば、Power BI へのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="f0c24-167">If you have a work or school account, you may have access to Power BI.</span></span> <span data-ttu-id="f0c24-168">そのアカウントでサインインしてみてください。</span><span class="sxs-lookup"><span data-stu-id="f0c24-168">Try signing in with that account.</span></span> <span data-ttu-id="f0c24-169">またはへのサインアップ後に無料で試すことができます。</span><span class="sxs-lookup"><span data-stu-id="f0c24-169">Or, you can try it for free after signing up.</span></span> 
2. <span data-ttu-id="f0c24-170">開く、`\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService`フォルダー、およびオープン、`BizTalkOperationalData.pbit`ファイル。</span><span class="sxs-lookup"><span data-stu-id="f0c24-170">Open the `\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService` folder, and open the `BizTalkOperationalData.pbit` file:</span></span>  
<span data-ttu-id="f0c24-171">![開いている pbit ファイル](../core/media/operational-data-pbit.png)</span><span class="sxs-lookup"><span data-stu-id="f0c24-171">![Open pbit file](../core/media/operational-data-pbit.png)</span></span>

3. <span data-ttu-id="f0c24-172">Power BI desktop が開き、URL が要求されます。</span><span class="sxs-lookup"><span data-stu-id="f0c24-172">Power BI desktop opens, and you are prompted for a URL.</span></span> <span data-ttu-id="f0c24-173">入力、 `http://localhost/<yourWebSite>` OData フィード用に作成した URL。</span><span class="sxs-lookup"><span data-stu-id="f0c24-173">Enter the `http://localhost/<yourWebSite>` URL that you created for your OData feed.</span></span> <span data-ttu-id="f0c24-174">たとえば、入力`http://localhost/BizTalkOperationalDataService`します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-174">For example, enter `http://localhost/BizTalkOperationalDataService`.</span></span> <span data-ttu-id="f0c24-175">URL は、次のような検索します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-175">Your URL looks similar to the following:</span></span>  
<span data-ttu-id="f0c24-176">![URL を入力します](../core/media/operational-data-url.png)</span><span class="sxs-lookup"><span data-stu-id="f0c24-176">![Enter the URL](../core/media/operational-data-url.png)</span></span>

4. <span data-ttu-id="f0c24-177">選択**ロード**します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-177">Select **Load**.</span></span> <span data-ttu-id="f0c24-178">ウィンドウは、読み込みを BizTalkOperationalDataService.json ファイル内の別の oData ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-178">The window loads and connects to the different oData sources in the BizTalkOperationalDataService.json file.</span></span> <span data-ttu-id="f0c24-179">完了したら、ダッシュ ボードは、環境に関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-179">When it completes, the dashboard shows details about your environment.</span></span>

## <a name="couldnt-authenticate"></a><span data-ttu-id="f0c24-180">認証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f0c24-180">Couldn't authenticate</span></span>
<span data-ttu-id="f0c24-181">表示された場合`couldn't authenticate with the credentials provided`メッセージは次のように、アプリケーション プール id は、BizTalk Server データベースに十分なアクセスがない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0c24-181">If you get `couldn't authenticate with the credentials provided` message similar to the following, then it’s possible your application pool identity doesn’t have enough access to the BizTalk Server databases.</span></span> <span data-ttu-id="f0c24-182">変更できます IIS 内でアプリケーション プール id 多くの特権を持つアカウントに可能性があります (これは、ローカル管理者特権を持つ) サインイン ユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="f0c24-182">You can change the appPool identity within IIS to an account with more privileges, maybe your signed-in user account (which has local admin privileges).</span></span> 

![指定された資格情報で認証できませんでした。](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a><span data-ttu-id="f0c24-184">さらに活用します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-184">Do more</span></span>
<span data-ttu-id="f0c24-185">これは、ほんの始まりにすぎません。</span><span class="sxs-lookup"><span data-stu-id="f0c24-185">This is just the beginning.</span></span> <span data-ttu-id="f0c24-186">Power BI では、オンプレミスの BizTalk Server にインストールできるゲートウェイもあります。</span><span class="sxs-lookup"><span data-stu-id="f0c24-186">Power BI also has a gateway that can be installed on an on-premises BizTalk Server.</span></span> <span data-ttu-id="f0c24-187">ゲートウェイを使用して、ダッシュ ボードを発行することができます、リアルタイムのデータを取得、ダッシュ ボードを更新するスケジュールを作成および。</span><span class="sxs-lookup"><span data-stu-id="f0c24-187">Using the gateway, you can publish your dashboard, get real-time data, and create a schedule to refresh the dashboard.</span></span> <span data-ttu-id="f0c24-188">次のブログは、次の手順の詳細を示す良い仕事をします。</span><span class="sxs-lookup"><span data-stu-id="f0c24-188">The following blog does a great job detailing these steps:</span></span> 

* [<span data-ttu-id="f0c24-189">Power BI – 詳細な構成手順で BizTalk のオペレーション データを発行する方法</span><span class="sxs-lookup"><span data-stu-id="f0c24-189">How to publish BizTalk operational data on Power BI – Step-by-step configuration</span></span>](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

<span data-ttu-id="f0c24-190">[ガイド付き学習](https://powerbi.microsoft.com/guided-learning/)も甲斐の Power BI に関する詳細、およびすべてのことを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f0c24-190">The [Guided Learning](https://powerbi.microsoft.com/guided-learning/) is also a great place to learn more about Power BI, and all the things you can do.</span></span> 

## <a name="see-also"></a><span data-ttu-id="f0c24-191">参照</span><span class="sxs-lookup"><span data-stu-id="f0c24-191">See also</span></span>

[<span data-ttu-id="f0c24-192">Power BI を詳細します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-192">Learn more about Power BI</span></span>](https://www.powerbi.com)  
[<span data-ttu-id="f0c24-193">Feature Pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0c24-193">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)
