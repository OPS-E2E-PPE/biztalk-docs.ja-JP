---
title: 手順 1:基本プラットフォームのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd3f901e31f0def313f3f8cf5cb3a9b8ea0dd16c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529963"
---
# <a name="step-1-installing-the-base-platform"></a><span data-ttu-id="087f5-102">手順 1:基本プラットフォームのインストール</span><span class="sxs-lookup"><span data-stu-id="087f5-102">Step 1: Installing the Base Platform</span></span>
<span data-ttu-id="087f5-103">基本プラットフォームが、インストールする Microsoft[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]と[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]既定のインストール オプションを使用して各サーバー上の Service Pack 2。</span><span class="sxs-lookup"><span data-stu-id="087f5-103">For the base platform, install Microsoft [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] Service Pack 2 on each server using the default installation options.</span></span> <span data-ttu-id="087f5-104">これらの推奨事項に従います。</span><span class="sxs-lookup"><span data-stu-id="087f5-104">Follow these recommendations:</span></span>  
  
## <a name="pre-installation"></a><span data-ttu-id="087f5-105">インストール前</span><span class="sxs-lookup"><span data-stu-id="087f5-105">Pre-Installation</span></span>  
  
- <span data-ttu-id="087f5-106">ソフトウェアのインストール中に、すべてのウイルス対策ソフトウェアを無効にします。</span><span class="sxs-lookup"><span data-stu-id="087f5-106">Disable all antivirus software during software installation.</span></span> <span data-ttu-id="087f5-107">一部のウイルス対策ソフトウェア プログラムすると、必要なソフトウェア コンポーネントが正しくインストールされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="087f5-107">Some antivirus software programs might prevent required software components from installing properly.</span></span>  
  
- <span data-ttu-id="087f5-108">適切なライセンス情報 (サーバーごとに購入した接続の最大数) を入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="087f5-108">Make sure that you enter the appropriate licensing information (maximum number of connections you have purchased per server).</span></span> <span data-ttu-id="087f5-109">システムのパフォーマンスは、利用可能な接続の数によって影響を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="087f5-109">System performance can be affected by the number of available connections.</span></span>  
  
- <span data-ttu-id="087f5-110">BizTalk Server のインストールに必要なすべてのソフトウェア前提条件がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="087f5-110">Make sure that you have installed all the software prerequisites required for a BizTalk Server installation.</span></span> <span data-ttu-id="087f5-111">詳細についてで BizTalk Server のインストール手順を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)します。</span><span class="sxs-lookup"><span data-stu-id="087f5-111">For more information, see the BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span> <span data-ttu-id="087f5-112">[BizTalk 2013 R2 Accelerator for SWIFT のインストール ガイド](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)します。</span><span class="sxs-lookup"><span data-stu-id="087f5-112">[Installation Guide for BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1).</span></span>  
  
- <span data-ttu-id="087f5-113">オフライン環境で実稼働サーバーにインストールする前にすべての重要な更新プログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="087f5-113">Test all critical updates in an offline environment before installing them on your production servers.</span></span>  
  
- <span data-ttu-id="087f5-114">配置の一部としてインストールするすべての製品の該当するすべての修正プログラムをインストールすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="087f5-114">Make sure that you install all the applicable hotfixes for all the products that you install as part of your deployment.</span></span> <span data-ttu-id="087f5-115">詳細については、次のソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="087f5-115">For more information, see the following sources:</span></span>  
  
  - <span data-ttu-id="087f5-116">Microsoft BizTalk Server のオンライン ヘルプ</span><span class="sxs-lookup"><span data-stu-id="087f5-116">Microsoft BizTalk Server Online Help</span></span>  
  
  - <span data-ttu-id="087f5-117">BizTalk Server のインストール」の手順に[ http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)します。</span><span class="sxs-lookup"><span data-stu-id="087f5-117">BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span>  
  
  - <span data-ttu-id="087f5-118">Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web サイトで[ http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685)します。</span><span class="sxs-lookup"><span data-stu-id="087f5-118">Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web site at [http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685).</span></span>  
  
  - <span data-ttu-id="087f5-119">Microsoft ダウンロード センター Web サイトで[ http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686)します。</span><span class="sxs-lookup"><span data-stu-id="087f5-119">Microsoft Download Center Web site at [http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686).</span></span>  
  
  - [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)] <span data-ttu-id="087f5-120">Web サイトで[ http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687)します。</span><span class="sxs-lookup"><span data-stu-id="087f5-120">Web site at [http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687).</span></span>  
  
- <span data-ttu-id="087f5-121">ウイルスの攻撃を避けるためには、CD から、プラットフォームのインストールし、すべてのケーブルを取り外すと、任意のネットワーク アダプターを無効にすると、各サーバーをインターネットから切断します。</span><span class="sxs-lookup"><span data-stu-id="087f5-121">To avoid virus attacks, install the platform from a CD and disconnect each server from the Internet by unplugging any cables and disabling any network adapters.</span></span>  
  
- <span data-ttu-id="087f5-122">クリーンなパーティションを使用して、書式設定、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS ファイル システム。</span><span class="sxs-lookup"><span data-stu-id="087f5-122">Format a clean partition using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS file system.</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="087f5-123">Active Directory</span><span class="sxs-lookup"><span data-stu-id="087f5-123">Active Directory</span></span>  
  
-   <span data-ttu-id="087f5-124">というドメイン ユーザーを作成**管理者**とローカルへの追加**管理者**配置内のすべてのコンピューターでグループ化します。</span><span class="sxs-lookup"><span data-stu-id="087f5-124">Create a domain user called **Admin** and add it to the local **Administrators** group on every computer in your deployment.</span></span> <span data-ttu-id="087f5-125">インストール時に、このドメイン アカウントを使用して、展開サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="087f5-125">At installation time, log on to the deployment servers using this domain account.</span></span>  
  
-   <span data-ttu-id="087f5-126">任意のネットワーク アダプターを構成したり、この時点で任意のドメインに参加しないでください。</span><span class="sxs-lookup"><span data-stu-id="087f5-126">Do not configure any network adapters or join any domains at this time.</span></span> <span data-ttu-id="087f5-127">このガイドでは、展開プロセスを開始するときに、後でこれらの設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="087f5-127">This guide describes how to configure these settings later when you begin the deployment process.</span></span>  
  
## <a name="internal-web-servers-mrsr-site"></a><span data-ttu-id="087f5-128">内部 Web サーバー (MRSR サイト)</span><span class="sxs-lookup"><span data-stu-id="087f5-128">Internal Web Servers (MRSR site)</span></span>  
  
-   <span data-ttu-id="087f5-129">MRSR サイト サーバーでのみ、インターネット インフォメーション サービス (IIS) がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="087f5-129">Make sure that Internet Information Services (IIS) is installed only on the MRSR site Servers.</span></span>  
  
-   <span data-ttu-id="087f5-130">インターネット インフォメーション サービス (IIS) が Internet Security and Acceleration (ISA) Server にインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="087f5-130">Make sure that Internet Information Services (IIS) is not installed on the Internet Security and Acceleration (ISA) Server.</span></span>  
  
-   <span data-ttu-id="087f5-131">MRSR サイト サーバーでのみ、メッセージ キュー (MSMQ) サービスがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="087f5-131">Make sure that the Message Queuing (MSMQ) service is installed only on the MRSR site Servers.</span></span> <span data-ttu-id="087f5-132">BizTalk メッセージング サーバーも MRSR サイト サーバーとして使用する場合は、これらのサーバーで MSMQ をインストールしません。</span><span class="sxs-lookup"><span data-stu-id="087f5-132">If the BizTalk Messaging servers will also be used as the MRSR site Servers, do not install MSMQ on those servers.</span></span>