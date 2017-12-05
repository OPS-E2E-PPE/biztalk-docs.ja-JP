---
title: "手順 1: 基本プラットフォームをインストールする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e0884ff97e9981129f63c9bc425e86dfeaafc9a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-1-installing-the-base-platform"></a><span data-ttu-id="13b9c-102">手順 1: 基本プラットフォームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b9c-102">Step 1: Installing the Base Platform</span></span>
<span data-ttu-id="13b9c-103">ベースのプラットフォームでは、インストール[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]と[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]既定のインストール オプションを使用して、各サーバー上の Service Pack 2 です。</span><span class="sxs-lookup"><span data-stu-id="13b9c-103">For the base platform, install [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] Service Pack 2 on each server using the default installation options.</span></span> <span data-ttu-id="13b9c-104">これらの推奨事項に従います。</span><span class="sxs-lookup"><span data-stu-id="13b9c-104">Follow these recommendations:</span></span>  
  
## <a name="pre-installation"></a><span data-ttu-id="13b9c-105">インストール前</span><span class="sxs-lookup"><span data-stu-id="13b9c-105">Pre-Installation</span></span>  
  
-   <span data-ttu-id="13b9c-106">ソフトウェアのインストール中に、すべてのウイルス対策ソフトウェアを無効にします。</span><span class="sxs-lookup"><span data-stu-id="13b9c-106">Disable all antivirus software during software installation.</span></span> <span data-ttu-id="13b9c-107">一部のウイルス対策ソフトウェア プログラムすると、必要なソフトウェア コンポーネントが正しくインストールできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13b9c-107">Some antivirus software programs might prevent required software components from installing properly.</span></span>  
  
-   <span data-ttu-id="13b9c-108">適切なライセンス情報 (サーバーごとに購入した接続の最大数) を入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-108">Make sure that you enter the appropriate licensing information (maximum number of connections you have purchased per server).</span></span> <span data-ttu-id="13b9c-109">利用可能な接続の数によってシステム パフォーマンスに影響することができます。</span><span class="sxs-lookup"><span data-stu-id="13b9c-109">System performance can be affected by the number of available connections.</span></span>  
  
-   <span data-ttu-id="13b9c-110">BizTalk Server のインストールに必要なすべてのソフトウェア前提条件がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-110">Make sure that you have installed all the software prerequisites required for a BizTalk Server installation.</span></span> <span data-ttu-id="13b9c-111">詳細についてで BizTalk Server のインストール手順を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)です。</span><span class="sxs-lookup"><span data-stu-id="13b9c-111">For more information, see the BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span> <span data-ttu-id="13b9c-112">[BizTalk 2013 R2 Accelerator for SWIFT のインストール ガイド](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)です。</span><span class="sxs-lookup"><span data-stu-id="13b9c-112">[Installation Guide for BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1).</span></span>  
  
-   <span data-ttu-id="13b9c-113">オフラインの環境で、実稼働サーバーにインストールする前にすべての重要な更新プログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="13b9c-113">Test all critical updates in an offline environment before installing them on your production servers.</span></span>  
  
-   <span data-ttu-id="13b9c-114">すべての該当する修正プログラムの展開の一環としてインストールするすべての製品をインストールすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-114">Make sure that you install all the applicable hotfixes for all the products that you install as part of your deployment.</span></span> <span data-ttu-id="13b9c-115">詳細については、次のソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13b9c-115">For more information, see the following sources:</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="13b9c-116">BizTalk Server のオンライン ヘルプ</span><span class="sxs-lookup"><span data-stu-id="13b9c-116"> BizTalk Server Online Help</span></span>  
  
    -   <span data-ttu-id="13b9c-117">BizTalk Server のインストール」の手順に[http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)です。</span><span class="sxs-lookup"><span data-stu-id="13b9c-117">BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="13b9c-118">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web サイトで[http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685)です。</span><span class="sxs-lookup"><span data-stu-id="13b9c-118"> [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web site at [http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685).</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="13b9c-119">ダウンロード センター Web サイトを[http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686)です。</span><span class="sxs-lookup"><span data-stu-id="13b9c-119"> Download Center Web site at [http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686).</span></span>  
  
    -   [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)]<span data-ttu-id="13b9c-120">Web サイトで[http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687)です。</span><span class="sxs-lookup"><span data-stu-id="13b9c-120"> Web site at [http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687).</span></span>  
  
-   <span data-ttu-id="13b9c-121">ウイルスによる攻撃を回避するのには、CD からプラットフォームをインストールし、すべてのケーブルを取り外すと、任意のネットワーク アダプターを無効にすると、各サーバーをインターネットから切断します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-121">To avoid virus attacks, install the platform from a CD and disconnect each server from the Internet by unplugging any cables and disabling any network adapters.</span></span>  
  
-   <span data-ttu-id="13b9c-122">クリーン パーティションを使用して、書式設定、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS ファイル システム。</span><span class="sxs-lookup"><span data-stu-id="13b9c-122">Format a clean partition using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS file system.</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="13b9c-123">Active Directory</span><span class="sxs-lookup"><span data-stu-id="13b9c-123">Active Directory</span></span>  
  
-   <span data-ttu-id="13b9c-124">呼ばれるドメイン ユーザーを作成**Admin**し、ローカルに追加する**管理者**配置内のすべてのコンピューターでグループ化します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-124">Create a domain user called **Admin** and add it to the local **Administrators** group on every computer in your deployment.</span></span> <span data-ttu-id="13b9c-125">インストール時に、このドメイン アカウントを使用して配置サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13b9c-125">At installation time, log on to the deployment servers using this domain account.</span></span>  
  
-   <span data-ttu-id="13b9c-126">任意のネットワーク アダプターを構成したり、この時点で、ドメインに参加しないでください。</span><span class="sxs-lookup"><span data-stu-id="13b9c-126">Do not configure any network adapters or join any domains at this time.</span></span> <span data-ttu-id="13b9c-127">このガイドでは、展開プロセスを開始するときに、後でこれらの設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-127">This guide describes how to configure these settings later when you begin the deployment process.</span></span>  
  
## <a name="internal-web-servers-mrsr-site"></a><span data-ttu-id="13b9c-128">内部の Web サーバー (MRSR サイト)</span><span class="sxs-lookup"><span data-stu-id="13b9c-128">Internal Web Servers (MRSR site)</span></span>  
  
-   <span data-ttu-id="13b9c-129">インターネット インフォメーション サービス (IIS) が、MRSR サイト サーバーにのみインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-129">Make sure that Internet Information Services (IIS) is installed only on the MRSR site Servers.</span></span>  
  
-   <span data-ttu-id="13b9c-130">インターネット インフォメーション サービス (IIS) が Internet Security and Acceleration (ISA) Server にインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-130">Make sure that Internet Information Services (IIS) is not installed on the Internet Security and Acceleration (ISA) Server.</span></span>  
  
-   <span data-ttu-id="13b9c-131">MRSR サイト サーバーにのみ、メッセージ キュー (MSMQ) サービスがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13b9c-131">Make sure that the Message Queuing (MSMQ) service is installed only on the MRSR site Servers.</span></span> <span data-ttu-id="13b9c-132">BizTalk メッセージング サーバーが、MRSR サイト サーバーとしても使用される場合、は、これらのサーバーで MSMQ を取り付けないでください。</span><span class="sxs-lookup"><span data-stu-id="13b9c-132">If the BizTalk Messaging servers will also be used as the MRSR site Servers, do not install MSMQ on those servers.</span></span>