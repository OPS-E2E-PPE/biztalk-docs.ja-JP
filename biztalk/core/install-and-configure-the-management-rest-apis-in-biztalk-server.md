---
title: "インストールし、管理 REST Api の構成 |Microsoft ドキュメント"
description: "BizTalk server 用 Feature Pack の管理データの REST Api を使用して BizTalk 環境内の成果物をクエリします。"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05b122047d7e303ed4e187fec19725cce9ae398
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="3434e-103">インストールし、BizTalk Server での管理 REST Api の構成</span><span class="sxs-lookup"><span data-stu-id="3434e-103">Install and configure the management REST APIs in BizTalk Server</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="3434e-104">管理データ Api とは</span><span class="sxs-lookup"><span data-stu-id="3434e-104">What are management data APIs</span></span>
<span data-ttu-id="3434e-105">管理データの Api は、エンドポイントでのリモート更新、追加、および内の各アイテムの状態を照会することのできる、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="3434e-105">Management data APIs are endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="3434e-106">エンドポイントは追加され、残りの部分を使用して swagger 定義が付属します。</span><span class="sxs-lookup"><span data-stu-id="3434e-106">The endpoints are added using REST, and come with a swagger definition.</span></span> 

<span data-ttu-id="3434e-107">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、これらの REST Api とその swagger 定義をインストールする Windows PowerShell スクリプトがあります。</span><span class="sxs-lookup"><span data-stu-id="3434e-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="3434e-108">これらの Api は、ポート、オーケストレーション、パートナー、契約、パイプライン、および詳細をリモートで管理する REST 呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="3434e-108">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3434e-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="3434e-109">Prerequisites</span></span>
* <span data-ttu-id="3434e-110">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3434e-110">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="3434e-111">IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3434e-111">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3434e-112">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3434e-112">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="3434e-113">参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。</span><span class="sxs-lookup"><span data-stu-id="3434e-113">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> <span data-ttu-id="3434e-114">開き、BizTalk Server で IIS がインストールされていることを確認**インターネット インフォメーション サービス マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="3434e-114">Confirm IIS is installed on the BizTalk Server by opening **Internet Information Services Manager**.</span></span> 

## <a name="step-1-install-the-rest-apis"></a><span data-ttu-id="3434e-115">手順 1: REST Api をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3434e-115">Step 1: Install the REST APIs</span></span>

1. <span data-ttu-id="3434e-116">Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。</span><span class="sxs-lookup"><span data-stu-id="3434e-116">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="3434e-117">BizTalk のインストール フォルダーに移動 (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。</span><span class="sxs-lookup"><span data-stu-id="3434e-117">Go to the BizTalk installation folder (for example, type: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`).</span></span>
3. <span data-ttu-id="3434e-118">次のテキストで置き換えます`Default Web Site`、 `mgmtServiceAppPool`、 `domain/user`、 `password`、および`domain\group`実際の値にします。</span><span class="sxs-lookup"><span data-stu-id="3434e-118">In the following text, replace `Default Web Site`, `mgmtServiceAppPool`, `domain/user`, `password`, and `domain\group` with your values:</span></span>

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    <span data-ttu-id="3434e-119">次の例では使用して、 `Default Web Site`、というアプリケーション プールを作成して`RESTAppPool`、として、アプリケーション プールを実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`BizTalk Server 管理者グループのアクセス許可を与える、ユーザー アカウントのパスワードとして。</span><span class="sxs-lookup"><span data-stu-id="3434e-119">In the following example, we use the `Default Web Site`, create an application pool named `RESTAppPool`, run the appPool as the `bootcampbts2016\btsservice` account, use `BIZTALK-serviceacct` as the user account password, and give the BizTalk Server Administrators group permissions.</span></span> <span data-ttu-id="3434e-120">次を入力するようにし、スペースを含む周囲の値を引用符で、1 つを含みます。</span><span class="sxs-lookup"><span data-stu-id="3434e-120">Be sure to enter the following, including the single quotes surrounding values with spaces:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    <span data-ttu-id="3434e-121">完了すると、 **BizTalkManagementService** IIS 内でアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3434e-121">When complete, the **BizTalkManagementService** application is created within IIS:</span></span>  
    <span data-ttu-id="3434e-122">![BizTalkManagementService アプリケーション](../core/media/biztalkmanagementservice-apppool.png)</span><span class="sxs-lookup"><span data-stu-id="3434e-122">![BizTalkManagementService application](../core/media/biztalkmanagementservice-apppool.png)</span></span>

4. <span data-ttu-id="3434e-123">動作していることを確認する」を参照`http://localhost/BizTalkManagementService/swagger`です。</span><span class="sxs-lookup"><span data-stu-id="3434e-123">To confirm it’s working, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span> <span data-ttu-id="3434e-124">かどうかサインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインするように求められます (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。</span><span class="sxs-lookup"><span data-stu-id="3434e-124">If you are prompted to sign-in, sign in with an account that is member of the domain\group you entered in the previous step (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`).</span></span> 

> [!WARNING]
> <span data-ttu-id="3434e-125">IIS で BizTalkManagementService アプリケーションは、web.config ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3434e-125">The BizTalkManagementService application in IIS uses a web.config file.</span></span> <span data-ttu-id="3434e-126">Web.config 内の要素**大文字と小文字は**します。</span><span class="sxs-lookup"><span data-stu-id="3434e-126">Elements within web.config **are case sensitive**.</span></span> <span data-ttu-id="3434e-127">ので、Windows PowerShell スクリプトを実行するときに、必ずに正しい文字を入力する`-AuthorizationRoles`値。</span><span class="sxs-lookup"><span data-stu-id="3434e-127">So when you execute the Windows PowerShell script, be sure to enter the correct case for `-AuthorizationRoles` value.</span></span> <span data-ttu-id="3434e-128">ケースのことを確認していない場合は、確認する簡単な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3434e-128">If you’re not sure of the case, here’s an easy way to find out:</span></span> 
> 
> 1. <span data-ttu-id="3434e-129">開いている**コンピューターの管理**、展開と**ローカル ユーザーとグループ**です。</span><span class="sxs-lookup"><span data-stu-id="3434e-129">Open **Computer Management**, and expand **Local Users and Groups**.</span></span>
> 2. <span data-ttu-id="3434e-130">選択**グループ**、下方向にスクロールし、 **SQLServer.**</span><span class="sxs-lookup"><span data-stu-id="3434e-130">Select **Groups**, and scroll down to the **SQLServer…**</span></span> <span data-ttu-id="3434e-131">グループ。</span><span class="sxs-lookup"><span data-stu-id="3434e-131">groups.</span></span> 
> 3. <span data-ttu-id="3434e-132">次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。</span><span class="sxs-lookup"><span data-stu-id="3434e-132">In the following example, notice **BOOTCAMPBTS2016** is in all caps.</span></span> <span data-ttu-id="3434e-133">すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3434e-133">If you see all caps, then enter the computer name in all caps.</span></span> 
> 
> ![すべて大文字では、コンピューター名です。](../core/media/groups-case.png)

<span data-ttu-id="3434e-135">これで、REST Api は、IIS を通じて公開される、アクセスおよびできます他のアプリケーションによって実行します。</span><span class="sxs-lookup"><span data-stu-id="3434e-135">Now that the REST APIs are exposed through IIS, they can be accessed and executed by other applications.</span></span> 

<span data-ttu-id="3434e-136">手動で更新することによってアクセスを持っているユーザーを変更することができます、 **web.config**管理アプリケーションのルート フォルダーにあるファイルです。</span><span class="sxs-lookup"><span data-stu-id="3434e-136">You can change who has access by manually updating the **web.config** file, which is in the root folder of the management application.</span></span> <span data-ttu-id="3434e-137">たとえばを使用して、swagger へのアクセスを許可するには、次の出力。</span><span class="sxs-lookup"><span data-stu-id="3434e-137">For example, use the following to allow anyone access to the swagger output:</span></span> 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a><span data-ttu-id="3434e-138">手順 2: テスト Api</span><span class="sxs-lookup"><span data-stu-id="3434e-138">Step 2: Test the APIs</span></span>

1. <span data-ttu-id="3434e-139">BizTalk Server を参照`http://localhost/BizTalkManagementService/swagger`です。</span><span class="sxs-lookup"><span data-stu-id="3434e-139">On the BizTalk Server, browse to `http://localhost/BizTalkManagementService/swagger`.</span></span>

2. <span data-ttu-id="3434e-140">スクロール**ホスト**を選択して**表示/非表示**です。</span><span class="sxs-lookup"><span data-stu-id="3434e-140">Scroll to **Hosts**, and select **Show/Hide**.</span></span> <span data-ttu-id="3434e-141">GET コマンド。この行をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3434e-141">There is a GET command; click this row:</span></span>  
<span data-ttu-id="3434e-142">![すべてのホストを取得します。](../core/media/managment-rest-apis-hosts-get.png)</span><span class="sxs-lookup"><span data-stu-id="3434e-142">![GET all hosts](../core/media/managment-rest-apis-hosts-get.png)</span></span>

3. <span data-ttu-id="3434e-143">詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3434e-143">It shows the details.</span></span> <span data-ttu-id="3434e-144">選択**お試しください**:</span><span class="sxs-lookup"><span data-stu-id="3434e-144">Select **Try it out**:</span></span>  
<span data-ttu-id="3434e-145">![お試しください](../core/media/managment-rest-apis-hosts-tryitout.png)</span><span class="sxs-lookup"><span data-stu-id="3434e-145">![Try it out](../core/media/managment-rest-apis-hosts-tryitout.png)</span></span>

4. <span data-ttu-id="3434e-146">応答本文には、すべてのホストが返されます。</span><span class="sxs-lookup"><span data-stu-id="3434e-146">The Response Body returns all the hosts:</span></span>  
![応答](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> <span data-ttu-id="3434e-148">参照する場合は`http://localhost/BizTalkManagementService`、500 エラーが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3434e-148">If you browse to `http://localhost/BizTalkManagementService`, you should get a 500 error.</span></span> <span data-ttu-id="3434e-149">良いことです。</span><span class="sxs-lookup"><span data-stu-id="3434e-149">That’s a good thing.</span></span> <span data-ttu-id="3434e-150">追加するだけで`/swagger`して、URL の末尾に使用できる REST Api が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3434e-150">Just add `/swagger` to the end of URL, and you’ll see the available REST APIs.</span></span> 


## <a name="see-also"></a><span data-ttu-id="3434e-151">参照</span><span class="sxs-lookup"><span data-stu-id="3434e-151">See also</span></span>
 [<span data-ttu-id="3434e-152">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="3434e-152">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)