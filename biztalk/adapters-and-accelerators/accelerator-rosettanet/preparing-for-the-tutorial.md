---
title: BizTalk Server で RosettaNet Loopback チュートリアルの前提条件 |Microsoft Docs
description: BizTalk Server では、RosettaNet アクセラレータの (BTARN) Loopback チュートリアルの手順の前提条件
caps.latest.revision: 9
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 807aa4002f08c9cb9f40f2bc6dad216bc2d730a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282626"
---
# <a name="prepare-for-the-tutorial"></a><span data-ttu-id="ff362-103">チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="ff362-103">Prepare for the tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ff362-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="ff362-104">Prerequisites</span></span>
<span data-ttu-id="ff362-105">前に、Loopback のチュートリアルを開始するには。</span><span class="sxs-lookup"><span data-stu-id="ff362-105">Before starting the Loopback tutorial:</span></span>
  
-   <span data-ttu-id="ff362-106">[インストールし、構成](install-configure-biztalk-accelerator-for-rosettanet.md)アクセラレータ。</span><span class="sxs-lookup"><span data-stu-id="ff362-106">[Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md) the accelerator.</span></span> <span data-ttu-id="ff362-107">SharePoint サーバーの全体管理で Windows SharePoint の管理パスの除外一覧に btarnhttpreceive 仮想ディレクトリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff362-107">You may have to add the btarnhttpreceive virtual directory to the Windows SharePoint managed path exclusion list in SharePoint Central Administration.</span></span>  
  
-   <span data-ttu-id="ff362-108">必ず、BizTalkServerIsolatedHost ホストと BizTalkServerApplication ホスト、**認証が信頼済み**オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ff362-108">Be sure the BizTalkServerIsolatedHost and BizTalkServerApplication hosts have the **Authentication trusted** option enabled.</span></span> <span data-ttu-id="ff362-109">確認する、BizTalk Server 管理コンソールを開き、展開**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="ff362-109">To verify, open the BizTalk Server Administration console, and expand **Hosts**.</span></span> <span data-ttu-id="ff362-110">ホストを右クリックして**プロパティ**、確認と**信頼されている認証**が有効になっていない場合。</span><span class="sxs-lookup"><span data-stu-id="ff362-110">Right-click the host, select **Properties**, and check **Authentication Trusted** if it's not enabled.</span></span>  

    <span data-ttu-id="ff362-111">1 つ以上のホスト インスタンスがある場合は、すべてが 1 つのホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="ff362-111">If you have more than one host instance, then delete all but one host instance.</span></span> <span data-ttu-id="ff362-112">たとえば、BizTalk Server 分離ホスト インスタンスを削除および、BizTalkServerApplication ホスト インスタンスを保持)。</span><span class="sxs-lookup"><span data-stu-id="ff362-112">For example, delete the BizTalk Server Isolated Host instance, and keep the BizTalkServerApplication host instance).</span></span> <span data-ttu-id="ff362-113">これにより、選択した**信頼されている認証**に関連付けられているホスト インスタンス、およびその他のホスト インスタンスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="ff362-113">This lets you select **Authentication Trusted** on the host associated with that instance, and then re-create the additional host instances.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ff362-114">次の手順</span><span class="sxs-lookup"><span data-stu-id="ff362-114">Next step</span></span>
 [<span data-ttu-id="ff362-115">ステップ 1: ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="ff362-115">Step 1: Create the Home Organization</span></span>](step-1-create-the-home-organization.md)