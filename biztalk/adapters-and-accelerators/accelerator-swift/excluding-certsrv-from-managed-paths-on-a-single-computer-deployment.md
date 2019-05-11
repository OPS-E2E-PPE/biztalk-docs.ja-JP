---
title: 1 台のコンピューター展開上のパスを管理から CertSrv を除外する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61ecb2f72dc3b9f1eb6e9898398b976f788a1421
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377914"
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a><span data-ttu-id="bdb72-102">1 台のコンピューターの展開の管理パスから CertSrv を除外します。</span><span class="sxs-lookup"><span data-stu-id="bdb72-102">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>
<span data-ttu-id="bdb72-103">デプロイした場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]1 台のコンピューターに証明書サーバーをインストールすることも、同じコンピューターにする必要がある証明書サーバー (/certsrv を指定します) を除外する Microsoft SharePoint Server のサーバーの全体管理の管理パスから。</span><span class="sxs-lookup"><span data-stu-id="bdb72-103">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer and also installed the certificate server on the same computer, you need to exclude the certificate server (CertSrv) from the managed paths in Microsoft SharePoint Server Central Administration.</span></span>  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a><span data-ttu-id="bdb72-104">管理パスから CertSrv を除外するには</span><span class="sxs-lookup"><span data-stu-id="bdb72-104">To exclude CertSrv from the managed paths</span></span>  
  
1.  <span data-ttu-id="bdb72-105">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint Central Administration**。</span><span class="sxs-lookup"><span data-stu-id="bdb72-105">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="bdb72-106">サーバーの全体管理] ウィンドウで、**仮想サーバーの構成**セクションで、[**仮想サーバー設定を構成**します。</span><span class="sxs-lookup"><span data-stu-id="bdb72-106">In the Central Administration window, in the **Virtual Server Configuration** section, click **Configure virtual server settings**.</span></span>  
  
3.  <span data-ttu-id="bdb72-107">仮想サーバーの一覧] ウィンドウで、[**既定の Web サイト**します。</span><span class="sxs-lookup"><span data-stu-id="bdb72-107">In the Virtual Server List window, click **Default Web Site**.</span></span>  
  
4.  <span data-ttu-id="bdb72-108">仮想サーバーの設定] ウィンドウで、**仮想サーバーの管理**セクションで、[**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="bdb72-108">In the Virtual Server Settings window, in the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
5.  <span data-ttu-id="bdb72-109">管理パスの定義 ウィンドウで、**新しいパスを追加**セクションに、入力**CertSrv**で、**パス**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="bdb72-109">In the Define Managed Paths window, in the **Add a New Path** section, enter **CertSrv** in the **Path** text box.</span></span> <span data-ttu-id="bdb72-110">**型**セクションで、**エクスクルード パス**します。</span><span class="sxs-lookup"><span data-stu-id="bdb72-110">In the **Type** section, click **Excluded Path**.</span></span> <span data-ttu-id="bdb72-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdb72-111">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="bdb72-112">管理パスの定義ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bdb72-112">Close the Define Managed Paths window.</span></span>