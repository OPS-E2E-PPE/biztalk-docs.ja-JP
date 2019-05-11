---
title: サーバー スナップインを使用する方法 |Microsoft Docs
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
ms.openlocfilehash: 094bf6ac21aff4d65528db4ae105cb3081405210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383196"
---
# <a name="how-to-use-the-servers-snap-in"></a><span data-ttu-id="83170-102">サーバー スナップインを使用する方法</span><span class="sxs-lookup"><span data-stu-id="83170-102">How to Use the Servers Snap-in</span></span>
<span data-ttu-id="83170-103">このバージョン エンタープライズ シングル サインオン (SSO) にはは、ENTSSO サーバー スナップインで、表示、監視、および Windows のインターフェイスを使用して ENTSSO サーバー上の特定のアクションを実行することが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83170-103">This version of Enterprise Single Sign-On (SSO) includes the ENTSSO Servers Snap-In, which allows you to view, monitor, and perform certain actions on your ENTSSO Server through the Windows interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83170-104">場合は、システムにファイアウォールがあり、サーバー名は FQDN 形式を使用して、サーバーに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="83170-104">If your system has a firewall and your server name uses the FQDN format, you may not be able to contact the server.</span></span> <span data-ttu-id="83170-105">代わりに、NetBIOS 名または関連付けられている IP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83170-105">Instead, you must specify the NetBIOS name or the associated IP address.</span></span>  
  
### <a name="to-use-the-entsso-servers-snap-in"></a><span data-ttu-id="83170-106">ENTSSO サーバー スナップインを使用するには</span><span class="sxs-lookup"><span data-stu-id="83170-106">To use the ENTSSO Servers Snap-In</span></span>  
  
1.  <span data-ttu-id="83170-107">エンタープライズ シングル サインオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="83170-107">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="83170-108">スコープ ウィンドウで、**サーバー**ノード。</span><span class="sxs-lookup"><span data-stu-id="83170-108">In the Scope pane, click the **Servers** node.</span></span>  
  
     <span data-ttu-id="83170-109">次の情報は、結果ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="83170-109">The following information is displayed in the Results pane.</span></span>  
  
    -   <span data-ttu-id="83170-110">**[名前]**:指定された名前です。</span><span class="sxs-lookup"><span data-stu-id="83170-110">**Name**: Name specified.</span></span>  
  
    -   <span data-ttu-id="83170-111">**状態**: (オンライン、オフライン、保留中、開始、停止、開始待ち、停止待ち)、ENTSSO サービスの状態です。</span><span class="sxs-lookup"><span data-stu-id="83170-111">**Status**: Status of the ENTSSO service (Online, Offline, Pending, Started, Stopped, Start Pending, Stop Pending).</span></span>  
  
    -   <span data-ttu-id="83170-112">**日付**:情報が取得された日付。</span><span class="sxs-lookup"><span data-stu-id="83170-112">**Date**: Date when information was obtained.</span></span>  
  
    -   <span data-ttu-id="83170-113">**時間**:情報が取得された時刻。</span><span class="sxs-lookup"><span data-stu-id="83170-113">**Time**: Time when information was obtained.</span></span>  
  
    -   <span data-ttu-id="83170-114">**SSO サーバー**:サーバーの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="83170-114">**SSO Server**: Fully qualified name of server.</span></span>  
  
    -   <span data-ttu-id="83170-115">**サービス アカウント**:ENTSSO サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="83170-115">**Service Account**: ENTSSO service account.</span></span>  
  
    -   <span data-ttu-id="83170-116">**SSO データベース**:このサーバーと通信している ENTSSO データベースです。</span><span class="sxs-lookup"><span data-stu-id="83170-116">**SSO Database**: ENTSSO Database with which this server is communicating.</span></span>  
  
    -   <span data-ttu-id="83170-117">**シークレット サーバー**:シークレット サーバー モジュールが実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="83170-117">**Secret Server**: Indicates whether the Secret Server module is running.</span></span>  
  
    -   <span data-ttu-id="83170-118">**パスワード同期**:パスワード同期がインストールされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="83170-118">**Password Sync**: Indicates whether Password Sync is installed.</span></span>  
  
    -   <span data-ttu-id="83170-119">**コンピューター**:コンピューターの NETBIOS 名です。</span><span class="sxs-lookup"><span data-stu-id="83170-119">**Computer**: NETBIOS name of computer.</span></span>  
  
    -   <span data-ttu-id="83170-120">**イベントはカウント**:情報/警告/エラー イベントの数。</span><span class="sxs-lookup"><span data-stu-id="83170-120">**Event counts**: Info/Warning/Errors event count.</span></span> <span data-ttu-id="83170-121">これをリセットすると、カウンターが 0 から開始されます。</span><span class="sxs-lookup"><span data-stu-id="83170-121">Resetting this will start the counter from 0.</span></span>  
  
    -   <span data-ttu-id="83170-122">**バージョンの SSO がインストールされている**:ENTSSO.exe のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="83170-122">**Version of SSO installed**: Version number of ENTSSO.exe.</span></span> <span data-ttu-id="83170-123">また、これは 32 ビット (x86) または 64 ビット (x64) かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="83170-123">Also indicates whether this is 32-bit (x86) or 64-bit (x64).</span></span>  
  
### <a name="to-start-or-stop-the-server-service"></a><span data-ttu-id="83170-124">サーバーのサービス開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="83170-124">To start or stop the server service</span></span>  
  
-   <span data-ttu-id="83170-125">ENTSSO サーバー スナップインで、サーバーを右クリックし、をクリックして**開始**または**停止**します。</span><span class="sxs-lookup"><span data-stu-id="83170-125">In the ENTSSO Servers Snap-In, right-click the server and click **Start** or **Stop**.</span></span>  
  
### <a name="to-display-information-for-one-server"></a><span data-ttu-id="83170-126">1 台のサーバーの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="83170-126">To display information for one server</span></span>  
  
-   <span data-ttu-id="83170-127">サーバー ツリーで、サーバーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="83170-127">In the Server tree, click the server.</span></span>  
  
     <span data-ttu-id="83170-128">情報は、結果ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="83170-128">The information is displayed in the results pane.</span></span>  
  
### <a name="to-add-a-server"></a><span data-ttu-id="83170-129">サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="83170-129">To add a server</span></span>  
  
-   <span data-ttu-id="83170-130">スコープ ペインで右クリックし をクリックし、**サーバーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="83170-130">Right-click in the Scope pane, and then click **Add Server**.</span></span>  
  
     <span data-ttu-id="83170-131">**サーバーの追加** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83170-131">The **Add Server** dialog box appears.</span></span> <span data-ttu-id="83170-132">入力するか、サーバーを追加するを参照します。</span><span class="sxs-lookup"><span data-stu-id="83170-132">Type or browse to the server you want to add.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83170-133">クリックすると、特定のワークグループ環境で、**参照**ボタンをクリックすると、このダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="83170-133">In certain Workgroup environments, clicking the **Browse** button will cause this dialog box to close.</span></span> <span data-ttu-id="83170-134">使用する代わりに、**参照**ボタンに、ボックスで、サーバー名に入力します。</span><span class="sxs-lookup"><span data-stu-id="83170-134">Instead of using the **Browse** button, simply type the server name in the box.</span></span>  
  
### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="83170-135">サーバーのプロパティを表示または変更するには</span><span class="sxs-lookup"><span data-stu-id="83170-135">To view or change server properties</span></span>  
  
-   <span data-ttu-id="83170-136">サーバー ツリーで、サーバーを右クリックし をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="83170-136">In the Server tree, right-click the server, and click **Properties**.</span></span>  
  
     <span data-ttu-id="83170-137">**サーバー プロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83170-137">The **Server Properties** dialog box appears.</span></span> <span data-ttu-id="83170-138">表示または、次のタブの情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="83170-138">You can view or change information in the following tabs:</span></span>  
  
    -   <span data-ttu-id="83170-139">**監査レベル**</span><span class="sxs-lookup"><span data-stu-id="83170-139">**Audit Levels**</span></span>  
  
    -   <span data-ttu-id="83170-140">**SSO データベース**</span><span class="sxs-lookup"><span data-stu-id="83170-140">**SSO Database**</span></span>  
  
    -   <span data-ttu-id="83170-141">**SSO サービス**</span><span class="sxs-lookup"><span data-stu-id="83170-141">**SSO Service**</span></span>  
  
    -   <span data-ttu-id="83170-142">**パスワード同期**</span><span class="sxs-lookup"><span data-stu-id="83170-142">**Password Sync**</span></span>  
  
    -   <span data-ttu-id="83170-143">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="83170-143">**Advanced**</span></span>