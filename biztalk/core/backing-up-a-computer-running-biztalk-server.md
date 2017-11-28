---
title: "BizTalk Server を実行しているコンピューターのバックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ea40b39ecd35127b62f8d96f0175e98a1f3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-a-computer-running-biztalk-server"></a><span data-ttu-id="c8f03-102">BizTalk Server を実行しているコンピュータのバックアップ</span><span class="sxs-lookup"><span data-stu-id="c8f03-102">Backing Up a Computer Running BizTalk Server</span></span>
<span data-ttu-id="c8f03-103">BizTalk Server を実行しているコンピュータで復旧不可能なハードウェア障害が発生した場合、同等のコンピュータに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8f03-103">If a computer running BizTalk Server suffers an irrecoverable hardware failure, then you must replace that computer with an identical one.</span></span> <span data-ttu-id="c8f03-104">基本プラットフォーム、必要なソフトウェア、BizTalk Server コンポーネント、および同等の構成設定が備わった代替コンピュータをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="c8f03-104">You should set up the replacement computer with the base platform software, software prerequisites, BizTalk Server components, and identical configuration settings.</span></span> <span data-ttu-id="c8f03-105">これらの構成設定は、BizTalk アプリケーションを正しく機能させるために必要な、適切なレジストリ エントリ、ファイル、フォルダ、および関連する Windows サービスで構成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8f03-105">These configuration settings may consist of the appropriate registry entries, files, folders, and related Windows services necessary for the correct operation of your BizTalk applications.</span></span>  
  
 <span data-ttu-id="c8f03-106">BizTalk Server データベースをバックアップするほか、次の BizTalk Server コンポーネントをバックアップして、ハードウェア障害が発生した後 BizTalk Server を復旧できるようにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8f03-106">In addition to backing up the BizTalk Server databases, you should back up the following BizTalk Server components to ensure that you can recover BizTalk Server after a hardware failure:</span></span>  
  
-   <span data-ttu-id="c8f03-107">BizTalk Server 構成</span><span class="sxs-lookup"><span data-stu-id="c8f03-107">BizTalk Server configuration</span></span>  
  
-   <span data-ttu-id="c8f03-108">エンタープライズ シングル サインオン (SSO) マスタ シークレット</span><span class="sxs-lookup"><span data-stu-id="c8f03-108">Enterprise Single Sign-On (SSO) master secret</span></span>  
  
-   <span data-ttu-id="c8f03-109">ビジネス アクティビティ監視 (BAM) ポータル (BAM を使用している場合のみ必要)</span><span class="sxs-lookup"><span data-stu-id="c8f03-109">Business Activity Monitoring (BAM) portal (not required unless you're using BAM)</span></span>  
  
-   <span data-ttu-id="c8f03-110">BizTalk アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8f03-110">BizTalk applications</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8f03-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c8f03-111">In This Section</span></span>  
  
-   [<span data-ttu-id="c8f03-112">BizTalk Server の構成をバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="c8f03-112">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="c8f03-113">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="c8f03-113">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="c8f03-114">BAM ポータルをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="c8f03-114">How to Back Up the BAM Portal</span></span>](../core/how-to-back-up-the-bam-portal.md)  
  
-   [<span data-ttu-id="c8f03-115">BizTalk Server アプリケーションをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="c8f03-115">Backing Up BizTalk Server Applications</span></span>](../core/backing-up-biztalk-server-applications.md)