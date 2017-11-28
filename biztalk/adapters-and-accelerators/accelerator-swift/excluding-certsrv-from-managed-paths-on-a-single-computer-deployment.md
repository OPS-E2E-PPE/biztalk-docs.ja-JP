---
title: "1 台のコンピューター展開上のパスを管理から CertSrv を除く |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c77fc1733859cd903bafcebc26162323feff82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a><span data-ttu-id="ae33c-102">1 台のコンピューター展開の管理パスから CertSrv の除外</span><span class="sxs-lookup"><span data-stu-id="ae33c-102">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>
<span data-ttu-id="ae33c-103">展開した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]1 台のコンピューターにも証明書サーバーをインストールし、同じコンピューター上での管理パスから証明書サーバー (CertSrv) を除外する必要があります。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint サーバーのサーバーの全体管理。</span><span class="sxs-lookup"><span data-stu-id="ae33c-103">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer and also installed the certificate server on the same computer, you need to exclude the certificate server (CertSrv) from the managed paths in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint Server Central Administration.</span></span>  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a><span data-ttu-id="ae33c-104">管理パスから CertSrv を除外するには</span><span class="sxs-lookup"><span data-stu-id="ae33c-104">To exclude CertSrv from the managed paths</span></span>  
  
1.  <span data-ttu-id="ae33c-105">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="ae33c-105">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="ae33c-106">ウィンドウで、サーバーの全体管理で、**仮想サーバーの構成**セクションで、**仮想サーバーの設定を構成する**です。</span><span class="sxs-lookup"><span data-stu-id="ae33c-106">In the Central Administration window, in the **Virtual Server Configuration** section, click **Configure virtual server settings**.</span></span>  
  
3.  <span data-ttu-id="ae33c-107">仮想サーバーの一覧] ウィンドウで、[ **Default Web Site**です。</span><span class="sxs-lookup"><span data-stu-id="ae33c-107">In the Virtual Server List window, click **Default Web Site**.</span></span>  
  
4.  <span data-ttu-id="ae33c-108">仮想サーバーの設定] ウィンドウで、**仮想サーバーの管理**セクションで、[**管理パスの定義**です。</span><span class="sxs-lookup"><span data-stu-id="ae33c-108">In the Virtual Server Settings window, in the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
5.  <span data-ttu-id="ae33c-109">管理パスの定義] ウィンドウで、[、**新しいパスを追加**セクションで、入力**CertSrv**で、**パス**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="ae33c-109">In the Define Managed Paths window, in the **Add a New Path** section, enter **CertSrv** in the **Path** text box.</span></span> <span data-ttu-id="ae33c-110">**型**セクションで、**エクスクルード パス**です。</span><span class="sxs-lookup"><span data-stu-id="ae33c-110">In the **Type** section, click **Excluded Path**.</span></span> <span data-ttu-id="ae33c-111">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae33c-111">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="ae33c-112">管理パスの定義ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ae33c-112">Close the Define Managed Paths window.</span></span>