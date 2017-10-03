---
title: "BizTalk Server で RosettaNet ループバック チュートリアルの前提条件 |Microsoft ドキュメント"
description: "BizTalk Server では、RosettaNet accelerator (BTARN) ループバック チュートリアルの手順の前提条件"
caps.latest.revision: "9"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 9767f7823e80d4de67345ba0fbf59c1435adb8e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-tutorial"></a><span data-ttu-id="f4b61-103">チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="f4b61-103">Prepare for the tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4b61-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="f4b61-104">Prerequisites</span></span>
<span data-ttu-id="f4b61-105">ループバック チュートリアルを開始する前に</span><span class="sxs-lookup"><span data-stu-id="f4b61-105">Before starting the Loopback tutorial:</span></span>
  
-   <span data-ttu-id="f4b61-106">[インストールし、構成](install-configure-biztalk-accelerator-for-rosettanet.md)アクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="f4b61-106">[Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md) the accelerator.</span></span> <span data-ttu-id="f4b61-107">SharePoint サーバーの全体管理で Windows SharePoint の管理パスの除外一覧に btarnhttpreceive 仮想ディレクトリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b61-107">You may have to add the btarnhttpreceive virtual directory to the Windows SharePoint managed path exclusion list in SharePoint Central Administration.</span></span>  
  
-   <span data-ttu-id="f4b61-108">必ず、BizTalkServerIsolatedHost ホストと BizTalkServerApplication ホスト、**認証が信頼済み**オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f4b61-108">Be sure the BizTalkServerIsolatedHost and BizTalkServerApplication hosts have the **Authentication trusted** option enabled.</span></span> <span data-ttu-id="f4b61-109">確認し、BizTalk Server 管理コンソールを開き、展開**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="f4b61-109">To verify, open the BizTalk Server Administration console, and expand **Hosts**.</span></span> <span data-ttu-id="f4b61-110">ホストを右クリックし、選択**プロパティ**、し確認**信頼されている認証**が有効になっていない場合。</span><span class="sxs-lookup"><span data-stu-id="f4b61-110">Right-click the host, select **Properties**, and check **Authentication Trusted** if it's not enabled.</span></span>  

    <span data-ttu-id="f4b61-111">1 つ以上のホスト インスタンスがある場合は、1 つを除くすべてのホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="f4b61-111">If you have more than one host instance, then delete all but one host instance.</span></span> <span data-ttu-id="f4b61-112">たとえば、BizTalk Server 分離ホスト インスタンスを削除と、BizTalkServerApplication ホスト インスタンス)。</span><span class="sxs-lookup"><span data-stu-id="f4b61-112">For example, delete the BizTalk Server Isolated Host instance, and keep the BizTalkServerApplication host instance).</span></span> <span data-ttu-id="f4b61-113">これにより、選択した**信頼されている認証**に関連付けられているホストのインスタンス、およびその他のホスト インスタンスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="f4b61-113">This lets you select **Authentication Trusted** on the host associated with that instance, and then re-create the additional host instances.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f4b61-114">次の手順</span><span class="sxs-lookup"><span data-stu-id="f4b61-114">Next step</span></span>
 [<span data-ttu-id="f4b61-115">手順 1: ホーム組織を作成します。</span><span class="sxs-lookup"><span data-stu-id="f4b61-115">Step 1: Create the Home Organization</span></span>](step-1-create-the-home-organization.md)