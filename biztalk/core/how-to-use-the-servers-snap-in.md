---
title: サーバー スナップインを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f520692-9606-41f5-98ed-5a4962bd1f09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12eb72323a6dcd1132f03febc9b4d9bd75316c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256562"
---
# <a name="how-to-use-the-servers-snap-in"></a><span data-ttu-id="9585a-102">サーバー スナップインの使用方法</span><span class="sxs-lookup"><span data-stu-id="9585a-102">How to Use the Servers Snap-in</span></span>
<span data-ttu-id="9585a-103">このバージョンのエンタープライズ シングル サインオン (SSO) には、ENTSSO サーバー スナップインが含まれています。これにより、Windows インターフェイスを使用して ENTSSO サーバー上で、特定のアクションを表示、監視、および実行できます。</span><span class="sxs-lookup"><span data-stu-id="9585a-103">This version of Enterprise Single Sign-On (SSO) includes the ENTSSO Servers Snap-In, which allows you to view, monitor, and perform certain actions on your ENTSSO Server through the Windows interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9585a-104">システムにファイアウォールがあり、サーバー名に FQDN 形式が使用されている場合、サーバーに接続できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="9585a-104">If your system has a firewall and your server name uses the FQDN format, you may not be able to contact the server.</span></span> <span data-ttu-id="9585a-105">代わりに、NetBIOS 名または関連する IP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9585a-105">Instead, you must specify the NetBIOS name or the associated IP address.</span></span>  
  
### <a name="to-use-the-entsso-servers-snap-in"></a><span data-ttu-id="9585a-106">ENTSSO サーバー スナップインを使用するには</span><span class="sxs-lookup"><span data-stu-id="9585a-106">To use the ENTSSO Servers Snap-In</span></span>  
  
1.  <span data-ttu-id="9585a-107">エンタープライズ シングル サインオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="9585a-107">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="9585a-108">スコープ ペインで、をクリックして、**サーバー**ノード。</span><span class="sxs-lookup"><span data-stu-id="9585a-108">In the Scope pane, click the **Servers** node.</span></span>  
  
     <span data-ttu-id="9585a-109">結果ペインに次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9585a-109">The following information is displayed in the Results pane.</span></span>  
  
    -   <span data-ttu-id="9585a-110">**名前**: 指定された名前です。</span><span class="sxs-lookup"><span data-stu-id="9585a-110">**Name**: Name specified.</span></span>  
  
    -   <span data-ttu-id="9585a-111">**ステータス**: (オンライン、オフライン、保留中の開始、停止、開始待ち、停止待ち)、ENTSSO サービスの状態。</span><span class="sxs-lookup"><span data-stu-id="9585a-111">**Status**: Status of the ENTSSO service (Online, Offline, Pending, Started, Stopped, Start Pending, Stop Pending).</span></span>  
  
    -   <span data-ttu-id="9585a-112">**日付**: 情報が取得した日付。</span><span class="sxs-lookup"><span data-stu-id="9585a-112">**Date**: Date when information was obtained.</span></span>  
  
    -   <span data-ttu-id="9585a-113">**時間**: 情報が取得された時刻。</span><span class="sxs-lookup"><span data-stu-id="9585a-113">**Time**: Time when information was obtained.</span></span>  
  
    -   <span data-ttu-id="9585a-114">**SSO サーバー**: サーバーの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="9585a-114">**SSO Server**: Fully qualified name of server.</span></span>  
  
    -   <span data-ttu-id="9585a-115">**サービス アカウント**: ENTSSO サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="9585a-115">**Service Account**: ENTSSO service account.</span></span>  
  
    -   <span data-ttu-id="9585a-116">**SSO データベース**: このサーバーと通信している ENTSSO データベースです。</span><span class="sxs-lookup"><span data-stu-id="9585a-116">**SSO Database**: ENTSSO Database with which this server is communicating.</span></span>  
  
    -   <span data-ttu-id="9585a-117">**シークレット サーバー**: シークレット サーバー モジュールが実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9585a-117">**Secret Server**: Indicates whether the Secret Server module is running.</span></span>  
  
    -   <span data-ttu-id="9585a-118">**パスワード同期**: パスワード同期がインストールされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9585a-118">**Password Sync**: Indicates whether Password Sync is installed.</span></span>  
  
    -   <span data-ttu-id="9585a-119">**コンピューター**: コンピューターの NETBIOS 名。</span><span class="sxs-lookup"><span data-stu-id="9585a-119">**Computer**: NETBIOS name of computer.</span></span>  
  
    -   <span data-ttu-id="9585a-120">**イベントはカウント**: 情報/警告/エラー イベントの数。</span><span class="sxs-lookup"><span data-stu-id="9585a-120">**Event counts**: Info/Warning/Errors event count.</span></span> <span data-ttu-id="9585a-121">リセットすると、カウンタは 0 から開始されます。</span><span class="sxs-lookup"><span data-stu-id="9585a-121">Resetting this will start the counter from 0.</span></span>  
  
    -   <span data-ttu-id="9585a-122">**インストールされている SSO のバージョン**: ENTSSO.exe のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="9585a-122">**Version of SSO installed**: Version number of ENTSSO.exe.</span></span> <span data-ttu-id="9585a-123">また、これが 32 ビット (x86) か 64 ビット (x64) かも示します。</span><span class="sxs-lookup"><span data-stu-id="9585a-123">Also indicates whether this is 32-bit (x86) or 64-bit (x64).</span></span>  
  
### <a name="to-start-or-stop-the-server-service"></a><span data-ttu-id="9585a-124">サーバー サービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="9585a-124">To start or stop the server service</span></span>  
  
-   <span data-ttu-id="9585a-125">ENTSSO サーバー スナップインで、サーバーを右クリックし、をクリックして**開始**または**停止**です。</span><span class="sxs-lookup"><span data-stu-id="9585a-125">In the ENTSSO Servers Snap-In, right-click the server and click **Start** or **Stop**.</span></span>  
  
### <a name="to-display-information-for-one-server"></a><span data-ttu-id="9585a-126">1 台のサーバーの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="9585a-126">To display information for one server</span></span>  
  
-   <span data-ttu-id="9585a-127">サーバー ツリーでサーバーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9585a-127">In the Server tree, click the server.</span></span>  
  
     <span data-ttu-id="9585a-128">結果ペインに情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9585a-128">The information is displayed in the results pane.</span></span>  
  
### <a name="to-add-a-server"></a><span data-ttu-id="9585a-129">サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="9585a-129">To add a server</span></span>  
  
-   <span data-ttu-id="9585a-130">スコープ ペインで右クリックし、をクリックして**サーバーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="9585a-130">Right-click in the Scope pane, and then click **Add Server**.</span></span>  
  
     <span data-ttu-id="9585a-131">**サーバーの追加** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9585a-131">The **Add Server** dialog box appears.</span></span> <span data-ttu-id="9585a-132">追加するサーバーを入力または参照します。</span><span class="sxs-lookup"><span data-stu-id="9585a-132">Type or browse to the server you want to add.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9585a-133">クリックすると、特定のワークグループ環境で、**参照**ボタンをクリックすると、このダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9585a-133">In certain Workgroup environments, clicking the **Browse** button will cause this dialog box to close.</span></span> <span data-ttu-id="9585a-134">使用する代わりに、**参照**ボタン、単にボックスに、サーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9585a-134">Instead of using the **Browse** button, simply type the server name in the box.</span></span>  
  
### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="9585a-135">サーバーのプロパティを表示または変更するには</span><span class="sxs-lookup"><span data-stu-id="9585a-135">To view or change server properties</span></span>  
  
-   <span data-ttu-id="9585a-136">サーバー ツリーで、サーバーを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="9585a-136">In the Server tree, right-click the server, and click **Properties**.</span></span>  
  
     <span data-ttu-id="9585a-137">**サーバー プロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9585a-137">The **Server Properties** dialog box appears.</span></span> <span data-ttu-id="9585a-138">次のタブで情報を表示または変更できます。</span><span class="sxs-lookup"><span data-stu-id="9585a-138">You can view or change information in the following tabs:</span></span>  
  
    -   <span data-ttu-id="9585a-139">**監査レベル**</span><span class="sxs-lookup"><span data-stu-id="9585a-139">**Audit Levels**</span></span>  
  
    -   <span data-ttu-id="9585a-140">**SSO データベース**</span><span class="sxs-lookup"><span data-stu-id="9585a-140">**SSO Database**</span></span>  
  
    -   <span data-ttu-id="9585a-141">**SSO サービス**</span><span class="sxs-lookup"><span data-stu-id="9585a-141">**SSO Service**</span></span>  
  
    -   <span data-ttu-id="9585a-142">**パスワード同期**</span><span class="sxs-lookup"><span data-stu-id="9585a-142">**Password Sync**</span></span>  
  
    -   <span data-ttu-id="9585a-143">**[詳細設定]**</span><span class="sxs-lookup"><span data-stu-id="9585a-143">**Advanced**</span></span>