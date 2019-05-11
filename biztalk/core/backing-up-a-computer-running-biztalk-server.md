---
title: BizTalk Server を実行しているコンピューターのバックアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04f8a0073ffd4117da1d5cf5d92dd969b9a0abfc
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528573"
---
# <a name="backing-up-a-computer-running-biztalk-server"></a><span data-ttu-id="17de1-102">BizTalk Server を実行しているコンピューターのバックアップ</span><span class="sxs-lookup"><span data-stu-id="17de1-102">Backing Up a Computer Running BizTalk Server</span></span>
<span data-ttu-id="17de1-103">BizTalk Server を実行しているコンピューターに、回復不可能なハードウェア障害が低下した場合は、同一の 1 つでそのコンピューターを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="17de1-103">If a computer running BizTalk Server suffers an irrecoverable hardware failure, then you must replace that computer with an identical one.</span></span> <span data-ttu-id="17de1-104">基本プラットフォームのソフトウェア、ソフトウェアの前提条件、BizTalk Server コンポーネント、および同等の構成設定で、代替コンピューターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17de1-104">You should set up the replacement computer with the base platform software, software prerequisites, BizTalk Server components, and identical configuration settings.</span></span> <span data-ttu-id="17de1-105">これらの構成設定は、適切なレジストリ エントリ、ファイル、フォルダー、および BizTalk アプリケーションの適切な操作に必要な関連する Windows サービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="17de1-105">These configuration settings may consist of the appropriate registry entries, files, folders, and related Windows services necessary for the correct operation of your BizTalk applications.</span></span>  
  
 <span data-ttu-id="17de1-106">BizTalk Server データベースをバックアップするだけでなくは、ハードウェア障害の後、BizTalk Server を回復できることを確認するのには、次の BizTalk Server コンポーネントをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17de1-106">In addition to backing up the BizTalk Server databases, you should back up the following BizTalk Server components to ensure that you can recover BizTalk Server after a hardware failure:</span></span>  
  
-   <span data-ttu-id="17de1-107">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="17de1-107">BizTalk Server configuration</span></span>  
  
-   <span data-ttu-id="17de1-108">エンタープライズ シングル サインオン (SSO) マスター シークレット</span><span class="sxs-lookup"><span data-stu-id="17de1-108">Enterprise Single Sign-On (SSO) master secret</span></span>  
  
-   <span data-ttu-id="17de1-109">(BAM を使用している場合を除きは必要ありません)、ビジネス アクティビティ監視 (BAM) ポータル</span><span class="sxs-lookup"><span data-stu-id="17de1-109">Business Activity Monitoring (BAM) portal (not required unless you're using BAM)</span></span>  
  
-   <span data-ttu-id="17de1-110">BizTalk アプリケーション</span><span class="sxs-lookup"><span data-stu-id="17de1-110">BizTalk applications</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17de1-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="17de1-111">In This Section</span></span>  
  
-   [<span data-ttu-id="17de1-112">BizTalk Server の構成をバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="17de1-112">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="17de1-113">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="17de1-113">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="17de1-114">BAM ポータルをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="17de1-114">How to Back Up the BAM Portal</span></span>](../core/how-to-back-up-the-bam-portal.md)  
  
-   [<span data-ttu-id="17de1-115">BizTalk Server アプリケーションのバックアップ</span><span class="sxs-lookup"><span data-stu-id="17de1-115">Backing Up BizTalk Server Applications</span></span>](../core/backing-up-biztalk-server-applications.md)