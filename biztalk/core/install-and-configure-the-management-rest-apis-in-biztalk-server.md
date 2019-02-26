---
title: インストールし、管理 REST Api の構成 |Microsoft Docs
description: BizTalk Server の Feature pack の管理データ REST Api を使用して、BizTalk 環境のアイテムをクエリします。
ms.custom: fp1
ms.date: 02/25/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 680b7390462a7a64d3064f621b2011952ba2551c
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56828567"
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="4a123-103">インストールし、BizTalk Server での管理 REST Api の構成</span><span class="sxs-lookup"><span data-stu-id="4a123-103">Install and configure the management REST APIs in BizTalk Server</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="4a123-104">管理データ Api とは</span><span class="sxs-lookup"><span data-stu-id="4a123-104">What are management data APIs</span></span>
<span data-ttu-id="4a123-105">管理データの Api は、リモートで更新、追加、および内の各アイテムの状態を照会できるエンドポイント、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="4a123-105">Management data APIs are endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="4a123-106">エンドポイントは、REST を使用して、swagger 定義に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4a123-106">The endpoints are added using REST, and come with a swagger definition.</span></span> 

<span data-ttu-id="4a123-107">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、これらの REST Api とその swagger 定義をインストールする Windows PowerShell スクリプトがあります。</span><span class="sxs-lookup"><span data-stu-id="4a123-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="4a123-108">これらの Api は、ポート、オーケストレーション、パートナー、契約、パイプライン、および詳細をリモートで管理する REST 呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="4a123-108">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

<span data-ttu-id="4a123-109">利用可能な Api、および実行できる内容を確認するを参照してください[機能パックの REST API リファレンス](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)します。</span><span class="sxs-lookup"><span data-stu-id="4a123-109">To see the available APIs, and what you can do, see [Feature Pack REST API reference](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4a123-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="4a123-110">Prerequisites</span></span>
* <span data-ttu-id="4a123-111">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a123-111">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="4a123-112">IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4a123-112">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4a123-113">開き、BizTalk Server で IIS がインストールされていることを確認します。**インターネット インフォメーション サービス マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="4a123-113">Confirm IIS is installed on the BizTalk Server by opening **Internet Information Services Manager**.</span></span> 

  <span data-ttu-id="4a123-114">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="4a123-114">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="4a123-115">参照してください[BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a123-115">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> 

## <a name="step-1-install-the-rest-apis"></a><span data-ttu-id="4a123-116">手順 1:REST Api をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a123-116">Step 1: Install the REST APIs</span></span>

1. <span data-ttu-id="4a123-117">Windows PowerShell を管理者として実行 (**開始**メニュー > 型**PowerShell** > を右クリックして >**管理者として実行**)。</span><span class="sxs-lookup"><span data-stu-id="4a123-117">Run Windows PowerShell as Administrator (**Start** menu > type **PowerShell** > right click > **Run as administrator**).</span></span> 
2. <span data-ttu-id="4a123-118">BizTalk インストール フォルダーに移動して (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。</span><span class="sxs-lookup"><span data-stu-id="4a123-118">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="4a123-119">次のテキストで置換`Default Web Site`、 `mgmtServiceAppPool`、 `domain/user`、 `password`、および`domain\group`の値。</span><span class="sxs-lookup"><span data-stu-id="4a123-119">In the following text, replace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    <span data-ttu-id="4a123-120">次の例では使用して、 `Default Web Site`、という名前のアプリケーション プールを作成`RESTAppPool`、として appPool を実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`し、ユーザー アカウントのパスワードとして、BizTalk Server 管理者グループのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="4a123-120">In the following example, we use the `Default Web Site`, create an application pool named `RESTAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the BizTalk Server Administrators group permissions.</span></span> <span data-ttu-id="4a123-121">次を入力してください、周囲の値にスペースが引用符など、1 つ。</span><span class="sxs-lookup"><span data-stu-id="4a123-121">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    <span data-ttu-id="4a123-122">完了すると、 **BizTalkManagementService** IIS 内でアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a123-122">When complete, the **BizTalkManagementService** application is created within IIS:</span></span>  
    <span data-ttu-id="4a123-123">![BizTalkManagementService アプリケーション](../core/media/biztalkmanagementservice-apppool.png)</span><span class="sxs-lookup"><span data-stu-id="4a123-123">![BizTalkManagementService application](../core/media/biztalkmanagementservice-apppool.png)</span></span>

4. <span data-ttu-id="4a123-124">参照するには、動作していることを確認するに`http://localhost/BizTalkManagementService/swagger`します。</span><span class="sxs-lookup"><span data-stu-id="4a123-124">To confirm it’s working, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span> <span data-ttu-id="4a123-125">サインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインを求められるかどうか (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。</span><span class="sxs-lookup"><span data-stu-id="4a123-125">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

> [!WARNING]
> <span data-ttu-id="4a123-126">IIS で BizTalkManagementService アプリケーションでは、web.config ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a123-126">The BizTalkManagementService application in IIS uses a web.config file.</span></span> <span data-ttu-id="4a123-127">Web.config 内の要素**大文字と小文字は**します。</span><span class="sxs-lookup"><span data-stu-id="4a123-127">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="4a123-128">Windows PowerShell スクリプトを実行するときに必ずに正しい文字を入力する`-AuthorizationRoles`値。</span><span class="sxs-lookup"><span data-stu-id="4a123-128">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="4a123-129">ケースのことを確認していない場合は、次に確認する簡単な方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4a123-129">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="4a123-130">開いている**コンピュータの管理**、展開と**ローカル ユーザーとグループ**します。</span><span class="sxs-lookup"><span data-stu-id="4a123-130">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="4a123-131">選択**グループ**、まで下へスクロールし、 **SQLServer.**</span><span class="sxs-lookup"><span data-stu-id="4a123-131">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="4a123-132">グループ。</span><span class="sxs-lookup"><span data-stu-id="4a123-132">groups.</span></span> 
> 3. <span data-ttu-id="4a123-133">次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。</span><span class="sxs-lookup"><span data-stu-id="4a123-133">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="4a123-134">すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a123-134">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![すべて大文字でコンピューター名には](../core/media/groups-case.png)

<span data-ttu-id="4a123-136">できたので、REST Api は、IIS を介して公開される、これらは、アクセスし、その他のアプリケーションによって実行されることができます。</span><span class="sxs-lookup"><span data-stu-id="4a123-136">Now that the REST APIs are exposed through IIS, they can be accessed and executed by other applications.</span></span> <span data-ttu-id="4a123-137">[機能パックの REST API リファレンス](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)Api を一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a123-137">[Feature Pack REST API reference](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016) lists the APIs.</span></span>

<span data-ttu-id="4a123-138">手動で更新することでアクセスを持っているユーザーを変更することができます、 **web.config**ファイル。 これは、管理アプリケーションのルート フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="4a123-138">You can change who has access by manually updating the **web.config** file, which is in the root folder of the management application.</span></span> <span data-ttu-id="4a123-139">たとえば、すべてのユーザーを許可するのには、次のアクセス、swagger を使用して出力。</span><span class="sxs-lookup"><span data-stu-id="4a123-139">For example, use the following to allow anyone access to the swagger output:</span></span> 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a><span data-ttu-id="4a123-140">手順 2:Api をテストします。</span><span class="sxs-lookup"><span data-stu-id="4a123-140">Step 2: Test the APIs</span></span>

1. <span data-ttu-id="4a123-141">BizTalk Server を参照`http://localhost/BizTalkManagementService/swagger`します。</span><span class="sxs-lookup"><span data-stu-id="4a123-141">On the BizTalk Server, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span>

2. <span data-ttu-id="4a123-142">スクロールして**ホスト**を選択し、**表示/非表示**します。</span><span class="sxs-lookup"><span data-stu-id="4a123-142">Scroll to **Hosts**, and select **Show/Hide**.</span></span> <span data-ttu-id="4a123-143">Get-command; があります。この行をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a123-143">There is a GET command; click this row:</span></span>  
<span data-ttu-id="4a123-144">![すべてのホストを取得します。](../core/media/managment-rest-apis-hosts-get.png)</span><span class="sxs-lookup"><span data-stu-id="4a123-144">![GET all hosts](../core/media/managment-rest-apis-hosts-get.png)</span></span>

3. <span data-ttu-id="4a123-145">詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a123-145">It shows the details.</span></span> <span data-ttu-id="4a123-146">選択**試して**:</span><span class="sxs-lookup"><span data-stu-id="4a123-146">Select **Try it out**:</span></span>  
<span data-ttu-id="4a123-147">![お試しください](../core/media/managment-rest-apis-hosts-tryitout.png)</span><span class="sxs-lookup"><span data-stu-id="4a123-147">![Try it out](../core/media/managment-rest-apis-hosts-tryitout.png)</span></span>

4. <span data-ttu-id="4a123-148">応答本文には、すべてのホストが返されます。</span><span class="sxs-lookup"><span data-stu-id="4a123-148">The Response Body returns all the hosts:</span></span>  
![応答](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> <span data-ttu-id="4a123-150">参照する場合`http://localhost/BizTalkManagementService`、500 エラーが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a123-150">If you browse to `http://localhost/BizTalkManagementService`, you should get a 500 error.</span></span> <span data-ttu-id="4a123-151">これは良いことです。</span><span class="sxs-lookup"><span data-stu-id="4a123-151">That’s a good thing.</span></span> <span data-ttu-id="4a123-152">追加するだけで`/swagger`URL の末尾に利用可能な REST Api が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a123-152">Just add `/swagger` to the end of URL, and you’ll see the available REST APIs.</span></span> 


## <a name="see-also"></a><span data-ttu-id="4a123-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a123-153">See also</span></span>
 [<span data-ttu-id="4a123-154">Feature Pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="4a123-154">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)