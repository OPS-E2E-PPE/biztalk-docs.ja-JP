---
title: "Power BI を有効にする |Microsoft ドキュメント"
description: "BizTalk server 機能パックに Power BI テンプレートをインストールします。"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d3b3dde09351b9a0aa021ef28645cb114495152
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="configure-the-operational-data-feed-for-power-bi-with-biztalk-server"></a><span data-ttu-id="1d027-103">BizTalk Server で Power BI にフィード オペレーション データを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d027-103">Configure the operational data feed for Power BI with BizTalk Server</span></span>

<span data-ttu-id="1d027-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**追跡を指定すると、Power BI テンプレートを使用して Power BI に送信します。 または、独自に作成します。</span><span class="sxs-lookup"><span data-stu-id="1d027-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, send tracking to Power BI using the Power BI template provided, or create your own.</span></span> 

## <a name="what-is-operational-data"></a><span data-ttu-id="1d027-105">オペレーション データとは</span><span class="sxs-lookup"><span data-stu-id="1d027-105">What is operational data</span></span>
<span data-ttu-id="1d027-106">オペレーション データは、インスタンスおよび経由でやり取りされるメッセージに関する情報、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="1d027-106">Operational data is information on the instances and messages flowing through your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="1d027-107">オペレーション データ フィードは、同じデータのグループ ハブを見て取得[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1d027-107">The operational data feed is the same data you get looking at Group Hub in [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="1d027-108">データにアクセスされ、Power BI を含む、視覚化ツールを使用してクエリします。</span><span class="sxs-lookup"><span data-stu-id="1d027-108">The data is accessed and queried using visualization tools, including Power BI.</span></span> 

<span data-ttu-id="1d027-109">フィードには、次のデータ テーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d027-109">The feed includes the following data tables:</span></span>
* <span data-ttu-id="1d027-110">アプリケーション データ</span><span class="sxs-lookup"><span data-stu-id="1d027-110">Application data</span></span>
* <span data-ttu-id="1d027-111">AS2 状態レコード</span><span class="sxs-lookup"><span data-stu-id="1d027-111">AS2 Status Records</span></span>
* <span data-ttu-id="1d027-112">バッチ処理の情報</span><span class="sxs-lookup"><span data-stu-id="1d027-112">Batching information</span></span>
* <span data-ttu-id="1d027-113">インスタンス情報</span><span class="sxs-lookup"><span data-stu-id="1d027-113">Instance information</span></span>
* <span data-ttu-id="1d027-114">インターチェンジの集計レコード</span><span class="sxs-lookup"><span data-stu-id="1d027-114">Interchange Aggregations Records</span></span>
* <span data-ttu-id="1d027-115">インターチェンジの状態レコード</span><span class="sxs-lookup"><span data-stu-id="1d027-115">Interchange Status Records</span></span>
* <span data-ttu-id="1d027-116">メッセージ</span><span class="sxs-lookup"><span data-stu-id="1d027-116">Messages</span></span>
* <span data-ttu-id="1d027-117">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="1d027-117">Subscriptions</span></span>
* <span data-ttu-id="1d027-118">追跡イベント</span><span class="sxs-lookup"><span data-stu-id="1d027-118">Tracked Events</span></span>
* <span data-ttu-id="1d027-119">トランザクションのレポート</span><span class="sxs-lookup"><span data-stu-id="1d027-119">Transaction reports</span></span>
* <span data-ttu-id="1d027-120">トランザクション セット</span><span class="sxs-lookup"><span data-stu-id="1d027-120">Transaction sets</span></span>

> [!TIP]
> <span data-ttu-id="1d027-121">[PowerBI.com](http://powerbi.microsoft.com)を理解し、Power BI の詳細です。</span><span class="sxs-lookup"><span data-stu-id="1d027-121">[PowerBI.com](http://powerbi.microsoft.com) is a great resource to understand and learn more about Power BI.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d027-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="1d027-122">Prerequisites</span></span>
* <span data-ttu-id="1d027-123">ダウンロードしてインストール[Power BI Desktop](https://powerbi.microsoft.com/desktop/)ネットワーク アクセス権を持つ任意のコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d027-123">Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on any computer that has network access to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="1d027-124">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d027-124">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="1d027-125">IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1d027-125">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1d027-126">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="1d027-126">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="1d027-127">参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d027-127">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> <span data-ttu-id="1d027-128">開くことによって IIS がインストールされていることを確認**インターネット インフォメーション サービス マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="1d027-128">Confirm IIS is installed by opening **Internet Information Services Manager**.</span></span> 

## <a name="step-1-enable-operational-data"></a><span data-ttu-id="1d027-129">手順 1: オペレーション データを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d027-129">Step 1: Enable operational data</span></span>

1. <span data-ttu-id="1d027-130">Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。</span><span class="sxs-lookup"><span data-stu-id="1d027-130">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="1d027-131">BizTalk のインストール フォルダーに移動 (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。</span><span class="sxs-lookup"><span data-stu-id="1d027-131">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="1d027-132">次のテキストで置き換えます`Default Web Site`、 `operationalDataServiceAppPool`、 `domain\user`、 `password`、および`domain\group`実際の値にします。</span><span class="sxs-lookup"><span data-stu-id="1d027-132">In the following text, replace `Default Web Site`, `operationalDataServiceAppPool`, `domain\user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>'
    ```

    <span data-ttu-id="1d027-133">次の例では使用して、 `Default Web Site`、というアプリケーション プールを作成`PowerBIAppPool`、として、アプリケーション プールを実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`により、ユーザー アカウントのパスワードとして、`BizTalk Server Administrators`アクセス許可をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="1d027-133">In the following example, we use the `Default Web Site`, create an application pool named `PowerBIAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the `BizTalk Server Administrators` group permissions.</span></span> <span data-ttu-id="1d027-134">次を入力するようにし、スペースを含む周囲の値を引用符で、1 つを含みます。</span><span class="sxs-lookup"><span data-stu-id="1d027-134">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    <span data-ttu-id="1d027-135">完了したら、IIS 内で BizTalkOperationalDataService アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d027-135">When complete, the BizTalkOperationalDataService application is created within IIS:</span></span>  
    ![BizTalkMOperationalDataServer アプリケーション](../core/media/biztalkmanagementservice-apppool.png)


4. <span data-ttu-id="1d027-137">動作していることを確認する」を参照`http://localhost/OperationalDataService`です。</span><span class="sxs-lookup"><span data-stu-id="1d027-137">To confirm it’s working, browse to `http://localhost/OperationalDataService`.</span></span> 

    <span data-ttu-id="1d027-138">かどうかサインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインするように求められます (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。</span><span class="sxs-lookup"><span data-stu-id="1d027-138">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

    <span data-ttu-id="1d027-139">開くか BizTalkOperationalDataService.json を保存するメッセージが表示されたら、インストールが完了しました。</span><span class="sxs-lookup"><span data-stu-id="1d027-139">If you are prompted to open or save BizTalkOperationalDataService.json, then your install completed.</span></span> <span data-ttu-id="1d027-140">ローカルに保存してメモ帳または内容を表示する Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="1d027-140">You can save it locally, and then open it in notepad or Visual Studio to see the contents.</span></span> 

> [!WARNING]
> <span data-ttu-id="1d027-141">IIS で BizTalkOperationalDataService アプリケーションは、web.config ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d027-141">The BizTalkOperationalDataService application in IIS uses a web.config file.</span></span> <span data-ttu-id="1d027-142">Web.config 内の要素**大文字と小文字は**します。</span><span class="sxs-lookup"><span data-stu-id="1d027-142">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="1d027-143">ので、Windows PowerShell スクリプトを実行するときに、必ずに正しい文字を入力する`-AuthorizationRoles`値。</span><span class="sxs-lookup"><span data-stu-id="1d027-143">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="1d027-144">ケースのことを確認していない場合は、確認する簡単な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d027-144">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="1d027-145">開いている**コンピューターの管理**、展開と**ローカル ユーザーとグループ**です。</span><span class="sxs-lookup"><span data-stu-id="1d027-145">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="1d027-146">選択**グループ**、下方向にスクロールし、 **SQLServer.**</span><span class="sxs-lookup"><span data-stu-id="1d027-146">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="1d027-147">グループ。</span><span class="sxs-lookup"><span data-stu-id="1d027-147">groups.</span></span> 
> 3. <span data-ttu-id="1d027-148">次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。</span><span class="sxs-lookup"><span data-stu-id="1d027-148">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="1d027-149">すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d027-149">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![すべて大文字では、コンピューター名です。](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a><span data-ttu-id="1d027-151">手順 2: Power BI でのテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d027-151">Step 2: Use the template in Power BI</span></span>

1. <span data-ttu-id="1d027-152">ダウンロードしてインストール、 [Power BI Desktop](https://powerbi.microsoft.com/desktop/) BizTalk Server にします。</span><span class="sxs-lookup"><span data-stu-id="1d027-152">Download and install the [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on your BizTalk Server.</span></span> <span data-ttu-id="1d027-153">開くには、これはオプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1d027-153">You can select to open it, which is optional.</span></span> <span data-ttu-id="1d027-154">職場または学校のアカウントを使っている場合は、Power BI へのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="1d027-154">If you have a work or school account, you may have access to Power BI.</span></span> <span data-ttu-id="1d027-155">そのアカウントでサインインしてください。</span><span class="sxs-lookup"><span data-stu-id="1d027-155">Try signing in with that account.</span></span> <span data-ttu-id="1d027-156">または、サインアップ後無料試用できます。</span><span class="sxs-lookup"><span data-stu-id="1d027-156">Or, you can try it for free after signing up.</span></span> 
2. <span data-ttu-id="1d027-157">開く、`\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService`フォルダーを開き、`BizTalkOperationalData.pbit`ファイル。</span><span class="sxs-lookup"><span data-stu-id="1d027-157">Open the `\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService` folder, and open the `BizTalkOperationalData.pbit` file:</span></span>  
<span data-ttu-id="1d027-158">![開いている pbit ファイル](../core/media/operational-data-pbit.png)</span><span class="sxs-lookup"><span data-stu-id="1d027-158">![Open pbit file](../core/media/operational-data-pbit.png)</span></span>

3. <span data-ttu-id="1d027-159">Power BI desktop が開き、URL のメッセージが表示されたら、します。</span><span class="sxs-lookup"><span data-stu-id="1d027-159">Power BI desktop opens, and you are prompted for a URL.</span></span> <span data-ttu-id="1d027-160">入力、 `http://localhost/<yourWebSite>` OData フィード用に作成した URL です。</span><span class="sxs-lookup"><span data-stu-id="1d027-160">Enter the `http://localhost/<yourWebSite>` URL that you created for your OData feed.</span></span> <span data-ttu-id="1d027-161">たとえば、入力`http://localhost/OperationalDataService`です。</span><span class="sxs-lookup"><span data-stu-id="1d027-161">For example, enter `http://localhost/OperationalDataService`.</span></span> <span data-ttu-id="1d027-162">URL は、次のようにはなります。</span><span class="sxs-lookup"><span data-stu-id="1d027-162">Your URL looks similar to the following:</span></span>  
<span data-ttu-id="1d027-163">![URL を入力します](../core/media/operational-data-url.png)</span><span class="sxs-lookup"><span data-stu-id="1d027-163">![Enter the URL](../core/media/operational-data-url.png)</span></span>

5. <span data-ttu-id="1d027-164">選択**ロード**です。</span><span class="sxs-lookup"><span data-stu-id="1d027-164">Select **Load**.</span></span> <span data-ttu-id="1d027-165">ウィンドウを読み込んで BizTalkOperationalDataService.json ファイル内の別の oData ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="1d027-165">The window loads and connects to the different oData sources in the BizTalkOperationalDataService.json file.</span></span> <span data-ttu-id="1d027-166">これが完了すると、ダッシュ ボードは、環境に関する詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="1d027-166">When it completes, the dashboard shows details about your environment.</span></span>

## <a name="couldnt-authenticate"></a><span data-ttu-id="1d027-167">認証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1d027-167">Couldn't authenticate</span></span>
<span data-ttu-id="1d027-168">表示された場合`couldn't authenticate with the credentials provided`メッセージは次のように、アプリケーション プール id は、BizTalk Server データベースへの十分なアクセスを持っていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d027-168">If you get `couldn't authenticate with the credentials provided` message similar to the following, then it’s possible your application pool identity doesn’t have enough access to the BizTalk Server databases.</span></span> <span data-ttu-id="1d027-169">変更できます IIS 内の appPool id 多くの特権を持つアカウントになる可能性があります (をローカルの管理者特権を持つ) サインイン ユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="1d027-169">You can change the appPool identity within IIS to an account with more privileges, maybe your signed-in user account (which has local admin privileges).</span></span> 

![指定された資格情報で認証できませんでした。](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a><span data-ttu-id="1d027-171">複数の操作を行います</span><span class="sxs-lookup"><span data-stu-id="1d027-171">Do more</span></span>
<span data-ttu-id="1d027-172">これは、始まりにすぎません。</span><span class="sxs-lookup"><span data-stu-id="1d027-172">This is just the beginning.</span></span> <span data-ttu-id="1d027-173">Power BI では、BizTalk Server にインストールできるゲートウェイもあります。</span><span class="sxs-lookup"><span data-stu-id="1d027-173">Power BI also has a gateway that can be installed on the BizTalk Server.</span></span> <span data-ttu-id="1d027-174">ゲートウェイを使用するには、ダッシュ ボードを発行、リアルタイムのデータを取得でき、ダッシュ ボードの更新スケジュールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1d027-174">Using the gateway, you can publish your dashboard, get real-time data, and create a schedule to refresh the dashboard.</span></span> <span data-ttu-id="1d027-175">次のブログに大変これらの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="1d027-175">The following blog does a great job detailing these steps:</span></span> 

[<span data-ttu-id="1d027-176">Power BI – 構成手順で BizTalk のオペレーション データを公開する方法</span><span class="sxs-lookup"><span data-stu-id="1d027-176">How to publish BizTalk operational data on Power BI – Step-by-step configuration</span></span>](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

<span data-ttu-id="1d027-177">[ガイド付き学習](https://powerbi.microsoft.com/guided-learning/)はでも、最適な場所に Power BI に関する詳細、およびすべての処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1d027-177">The [Guided Learning](https://powerbi.microsoft.com/guided-learning/) is also a great place to learn more about Power BI, and all the things you can do.</span></span> 

## <a name="see-also"></a><span data-ttu-id="1d027-178">参照</span><span class="sxs-lookup"><span data-stu-id="1d027-178">See also</span></span>

[<span data-ttu-id="1d027-179">Power BI を詳細します。</span><span class="sxs-lookup"><span data-stu-id="1d027-179">Learn more about Power BI</span></span>](https://www.powerbi.com)  
[<span data-ttu-id="1d027-180">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d027-180">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)