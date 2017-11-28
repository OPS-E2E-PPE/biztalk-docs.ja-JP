---
title: "インストールし、管理 REST Api の構成 |Microsoft ドキュメント"
description: "BizTalk server 機能パック 1 で管理データの REST Api を使用して BizTalk 環境内の成果物の状態をクエリします。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 009b3b0bb333b8f92f6235da57b0c3e9f5daca96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a><span data-ttu-id="0aa66-103">インストールし、BizTalk Server での管理 REST Api の構成</span><span class="sxs-lookup"><span data-stu-id="0aa66-103">Install and configure the management REST APIs in BizTalk Server</span></span>
<span data-ttu-id="0aa66-104">リモートで管理 REST Api を有効にする、Windows PowerShell スクリプトを使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0aa66-104">Use a Windows PowerShell script to enable REST APIs that remotely manage your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="what-are-management-data-apis"></a><span data-ttu-id="0aa66-105">管理データ Api とは</span><span class="sxs-lookup"><span data-stu-id="0aa66-105">What are Management data APIs</span></span>
<span data-ttu-id="0aa66-106">管理データの Api は、エンドポイントでのリモート更新、追加、および内の各アイテムの状態を照会することのできる、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="0aa66-106">Management data APIs are the endpoints that let you remotely update, add, and query the status of different artifacts in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="0aa66-107">エンドポイントは追加され、残りの部分を使用して Swagger 定義が付属します。</span><span class="sxs-lookup"><span data-stu-id="0aa66-107">The endpoints are added using REST, and come with a Swagger definition.</span></span> 

<span data-ttu-id="0aa66-108">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、これらの REST Api とその swagger 定義をインストールする Windows PowerShell スクリプトがあります。</span><span class="sxs-lookup"><span data-stu-id="0aa66-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, there's a Windows PowerShell script that installs these REST APIs, and their swagger definitions.</span></span> <span data-ttu-id="0aa66-109">これらの Api は、ポート、オーケストレーション、パートナー、契約、パイプライン、および詳細をリモートで管理する REST 呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="0aa66-109">These APIs make REST calls to remotely manage ports, orchestrations, partners, agreements, pipelines, and more.</span></span> 

<span data-ttu-id="0aa66-110">このトピックでは、REST Api をインストールする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0aa66-110">This topic shows you how to install the REST APIs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0aa66-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="0aa66-111">Prerequisites</span></span>
* <span data-ttu-id="0aa66-112">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aa66-112">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

* <span data-ttu-id="0aa66-113">IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0aa66-113">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0aa66-114">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0aa66-114">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="0aa66-115">参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。</span><span class="sxs-lookup"><span data-stu-id="0aa66-115">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>

## <a name="enable-the-rest-apis"></a><span data-ttu-id="0aa66-116">REST Api を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0aa66-116">Enable the REST APIs</span></span>

1. <span data-ttu-id="0aa66-117">Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。</span><span class="sxs-lookup"><span data-stu-id="0aa66-117">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="0aa66-118">BizTalk フォルダーに移動**Program Files (x86)/microsoft BizTalk Server 2016**</span><span class="sxs-lookup"><span data-stu-id="0aa66-118">Browse to the BizTalk folder under **Program Files (x86)/Microsoft BizTalk Server 2016**</span></span>
3. <span data-ttu-id="0aa66-119">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0aa66-119">Run the following command.</span></span> <span data-ttu-id="0aa66-120">更新してください、 `website`、 `domain/user`、 `password`、および`domain\group`実際の値にします。</span><span class="sxs-lookup"><span data-stu-id="0aa66-120">Be sure to update your `website`, `domain/user`, `password`, and `domain\group` with your values:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```
4. <span data-ttu-id="0aa66-121">スクリプトを実行した後は、新しい IIS アプリケーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0aa66-121">After you run the script, browse the new IIS application:</span></span>  
    1. <span data-ttu-id="0aa66-122">Web ブラウザーを開きます</span><span class="sxs-lookup"><span data-stu-id="0aa66-122">Open your web browser</span></span>
    2. <span data-ttu-id="0aa66-123">参照**http://localhost/OperationalDataService/swagger**</span><span class="sxs-lookup"><span data-stu-id="0aa66-123">Browse to **http://localhost/OperationalDataService/swagger**</span></span>

5. <span data-ttu-id="0aa66-124">Swagger 定義ロードします。</span><span class="sxs-lookup"><span data-stu-id="0aa66-124">The Swagger definitions loads.</span></span> <span data-ttu-id="0aa66-125">更新することによってアクセスを持っているユーザーを変更することも、 **web.config**管理アプリケーションのルート フォルダー内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="0aa66-125">You can also change who has access by updating the **web.config** file in the root folder of the Management Application.</span></span>

<span data-ttu-id="0aa66-126">REST Api は、マシンを介して公開されますと、アクセスして他のアプリケーションで実行できることができます。</span><span class="sxs-lookup"><span data-stu-id="0aa66-126">The REST APIs are exposed through the machine, and can be accessed and executed by other applications.</span></span> 


## <a name="see-also"></a><span data-ttu-id="0aa66-127">参照</span><span class="sxs-lookup"><span data-stu-id="0aa66-127">See also</span></span>
 [<span data-ttu-id="0aa66-128">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="0aa66-128">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)