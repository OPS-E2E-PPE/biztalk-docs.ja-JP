---
title: BizTalk Server のバージョンがあるでしょうか。 | Microsoft Docs
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
ms.openlocfilehash: 974999da3d74075fa218e078d1a757a83dbd325e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395148"
---
# <a name="what-version-of-biztalk-server-do-i-have"></a><span data-ttu-id="f9f66-103">BizTalk Server のバージョンがあるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="f9f66-103">What Version of BizTalk Server Do I Have?</span></span>
<span data-ttu-id="f9f66-104">さまざまなバージョンとのさまざまなエディションを実行して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-104">You may be running different versions and different editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f9f66-105">このトピックでは、確認する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールについては、バージョン番号、エディション、およびインストール パスを含むです。</span><span class="sxs-lookup"><span data-stu-id="f9f66-105">This topic shows you how to determine [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation information, including the version number, edition, and installation path.</span></span>  

## <a name="use-the-registry"></a><span data-ttu-id="f9f66-106">レジストリを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-106">Use the registry</span></span>

1. <span data-ttu-id="f9f66-107">選択**開始**、型`regedt32`、し、開きます。</span><span class="sxs-lookup"><span data-stu-id="f9f66-107">Select **Start**, type `regedt32`, and then open it.</span></span>  

2. <span data-ttu-id="f9f66-108">展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BizTalk Server**、し、 **3.0**します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-108">Expand **HKEY_LOCAL_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, expand **BizTalk Server**, and then select **3.0**.</span></span>  

3. <span data-ttu-id="f9f66-109">右側のウィンドウには、インストール情報が表示されます。 など。</span><span class="sxs-lookup"><span data-stu-id="f9f66-109">The right pane displays installation information, including:</span></span>  


   |      <span data-ttu-id="f9f66-110">サブ キー</span><span class="sxs-lookup"><span data-stu-id="f9f66-110">Sub-key</span></span>       |                                                                                                         <span data-ttu-id="f9f66-111">説明</span><span class="sxs-lookup"><span data-stu-id="f9f66-111">Description</span></span>                                                                                                          |
   |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="f9f66-112">**InstallPath**</span><span class="sxs-lookup"><span data-stu-id="f9f66-112">**InstallPath**</span></span>   |                                             <span data-ttu-id="f9f66-113">インストールしたインストール パスを一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-113">Lists the installation path where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>                                              |
   | <span data-ttu-id="f9f66-114">**ProductEdition**</span><span class="sxs-lookup"><span data-stu-id="f9f66-114">**ProductEdition**</span></span> |                                                        <span data-ttu-id="f9f66-115">エディションの一覧を含みます。</span><span class="sxs-lookup"><span data-stu-id="f9f66-115">Lists the edition, including:</span></span><br /><br /> <span data-ttu-id="f9f66-116">-開発者</span><span class="sxs-lookup"><span data-stu-id="f9f66-116">-   Developer</span></span><br /><span data-ttu-id="f9f66-117">ブランチ</span><span class="sxs-lookup"><span data-stu-id="f9f66-117">-   Branch</span></span><br /><span data-ttu-id="f9f66-118">標準</span><span class="sxs-lookup"><span data-stu-id="f9f66-118">-   Standard</span></span><br /><span data-ttu-id="f9f66-119">-エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="f9f66-119">-   Enterprise</span></span>                                                         |
   | <span data-ttu-id="f9f66-120">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="f9f66-120">**ProductVersion**</span></span> | <span data-ttu-id="f9f66-121">基本の製品バージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-121">Lists the base product version.</span></span> <span data-ttu-id="f9f66-122">サービス パックおよび累積更新プログラムを含め、特定の製品バージョンを参照してください。[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-122">For specific product version, including service packs and cumulative updates, see [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span> |

## <a name="use-the-control-panel"></a><span data-ttu-id="f9f66-123">コントロール パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-123">Use the control panel</span></span>

1.  <span data-ttu-id="f9f66-124">選択**開始**、型`Programs and Features`、し、開きます。</span><span class="sxs-lookup"><span data-stu-id="f9f66-124">Select **Start**, type `Programs and Features`, and then open it.</span></span>  

2. <span data-ttu-id="f9f66-125">一覧で、次のように選択します。 **Microsoft BizTalk Server**します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-125">In the list, select **Microsoft BizTalk Server**.</span></span> <span data-ttu-id="f9f66-126">バージョンおよびエディションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9f66-126">The version and edition are listed.</span></span>

<span data-ttu-id="f9f66-127">参照してください[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="f9f66-127">See [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9f66-128">参照</span><span class="sxs-lookup"><span data-stu-id="f9f66-128">See Also</span></span>  
 [<span data-ttu-id="f9f66-129">開始するには</span><span class="sxs-lookup"><span data-stu-id="f9f66-129">Get started</span></span>](../core/getting-started-with-biztalk-server.md)