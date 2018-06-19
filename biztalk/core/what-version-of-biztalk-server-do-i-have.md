---
title: ご使用の BizTalk Server のバージョンを確認する方法 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb651202-f682-4e5f-8a79-221877af20a7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce5508a3b7c78e52fe5fcbef40e351dce58f2816
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288850"
---
# <a name="what-version-of-biztalk-server-do-i-have"></a><span data-ttu-id="3d985-103">ご使用の BizTalk Server のバージョンを確認する方法</span><span class="sxs-lookup"><span data-stu-id="3d985-103">What Version of BizTalk Server Do I Have?</span></span>
<span data-ttu-id="3d985-104">別のバージョンと異なるエディションを実行して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3d985-104">You may be running different versions and different editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3d985-105">このトピックで説明する方法を決定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールについては、バージョン番号、エディション、およびインストール パスを含むです。</span><span class="sxs-lookup"><span data-stu-id="3d985-105">This topic shows you how to determine [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation information, including the version number, edition, and installation path.</span></span>  
  
## <a name="use-the-registry"></a><span data-ttu-id="3d985-106">レジストリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d985-106">Use the registry</span></span>
  
1.  <span data-ttu-id="3d985-107">選択**開始**、型`regedt32`、し、開きます。</span><span class="sxs-lookup"><span data-stu-id="3d985-107">Select **Start**, type `regedt32`, and then open it.</span></span>  
  
2.  <span data-ttu-id="3d985-108">展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BizTalk Server**、し、 **3.0**です。</span><span class="sxs-lookup"><span data-stu-id="3d985-108">Expand **HKEY_LOCAL_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, expand **BizTalk Server**, and then select **3.0**.</span></span>  
  
3.  <span data-ttu-id="3d985-109">右側のウィンドウに以下のインストール情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d985-109">The right pane displays installation information, including:</span></span>  
  
    |<span data-ttu-id="3d985-110">サブキー</span><span class="sxs-lookup"><span data-stu-id="3d985-110">Sub-key</span></span>|<span data-ttu-id="3d985-111">Description</span><span class="sxs-lookup"><span data-stu-id="3d985-111">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="3d985-112">**インストール パス**</span><span class="sxs-lookup"><span data-stu-id="3d985-112">**InstallPath**</span></span>|<span data-ttu-id="3d985-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしたインストール パスがリストされます。</span><span class="sxs-lookup"><span data-stu-id="3d985-113">Lists the installation path where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
    |<span data-ttu-id="3d985-114">**ProductEdition**</span><span class="sxs-lookup"><span data-stu-id="3d985-114">**ProductEdition**</span></span>|<span data-ttu-id="3d985-115">以下のエディションがリストされます。</span><span class="sxs-lookup"><span data-stu-id="3d985-115">Lists the edition, including:</span></span><br /><br /> <span data-ttu-id="3d985-116">-開発者</span><span class="sxs-lookup"><span data-stu-id="3d985-116">-   Developer</span></span><br /><span data-ttu-id="3d985-117">ブランチ</span><span class="sxs-lookup"><span data-stu-id="3d985-117">-   Branch</span></span><br /><span data-ttu-id="3d985-118">標準</span><span class="sxs-lookup"><span data-stu-id="3d985-118">-   Standard</span></span><br /><span data-ttu-id="3d985-119">-エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="3d985-119">-   Enterprise</span></span>|  
    |<span data-ttu-id="3d985-120">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="3d985-120">**ProductVersion**</span></span>|<span data-ttu-id="3d985-121">基本の製品バージョンがリストされます。</span><span class="sxs-lookup"><span data-stu-id="3d985-121">Lists the base product version.</span></span> <span data-ttu-id="3d985-122">サービス パックおよび累積更新プログラムを含め、特定の製品バージョンを参照してください。[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="3d985-122">For specific product version, including service packs and cumulative updates, see [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span>|  

## <a name="use-the-control-panel"></a><span data-ttu-id="3d985-123">コントロール パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d985-123">Use the control panel</span></span>

1.  <span data-ttu-id="3d985-124">選択**開始**、型`Programs and Features`、し、開きます。</span><span class="sxs-lookup"><span data-stu-id="3d985-124">Select **Start**, type `Programs and Features`, and then open it.</span></span>  

2. <span data-ttu-id="3d985-125">一覧で、次のように選択します。 **Microsoft BizTalk Server**です。</span><span class="sxs-lookup"><span data-stu-id="3d985-125">In the list, select **Microsoft BizTalk Server**.</span></span> <span data-ttu-id="3d985-126">バージョンおよびエディションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d985-126">The version and edition are listed.</span></span>

<span data-ttu-id="3d985-127">参照してください[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="3d985-127">See [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d985-128">参照</span><span class="sxs-lookup"><span data-stu-id="3d985-128">See Also</span></span>  
 [<span data-ttu-id="3d985-129">開始するには</span><span class="sxs-lookup"><span data-stu-id="3d985-129">Get started</span></span>](../core/getting-started-with-biztalk-server.md)