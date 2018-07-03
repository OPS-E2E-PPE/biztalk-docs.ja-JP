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
ms.openlocfilehash: e7003f2d3c61345462ca484f627110a6e507e748
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976979"
---
# <a name="what-version-of-biztalk-server-do-i-have"></a><span data-ttu-id="ff295-103">ご使用の BizTalk Server のバージョンを確認する方法</span><span class="sxs-lookup"><span data-stu-id="ff295-103">What Version of BizTalk Server Do I Have?</span></span>
<span data-ttu-id="ff295-104">さまざまなバージョンとのさまざまなエディションを実行して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ff295-104">You may be running different versions and different editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ff295-105">このトピックでは、確認する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールについては、バージョン番号、エディション、およびインストール パスを含むです。</span><span class="sxs-lookup"><span data-stu-id="ff295-105">This topic shows you how to determine [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation information, including the version number, edition, and installation path.</span></span>  

## <a name="use-the-registry"></a><span data-ttu-id="ff295-106">レジストリを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff295-106">Use the registry</span></span>

1. <span data-ttu-id="ff295-107">選択**開始**、型`regedt32`、し、開きます。</span><span class="sxs-lookup"><span data-stu-id="ff295-107">Select **Start**, type `regedt32`, and then open it.</span></span>  

2. <span data-ttu-id="ff295-108">展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BizTalk Server**、し、 **3.0**します。</span><span class="sxs-lookup"><span data-stu-id="ff295-108">Expand **HKEY_LOCAL_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, expand **BizTalk Server**, and then select **3.0**.</span></span>  

3. <span data-ttu-id="ff295-109">右側のウィンドウに以下のインストール情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff295-109">The right pane displays installation information, including:</span></span>  


   |      <span data-ttu-id="ff295-110">サブキー</span><span class="sxs-lookup"><span data-stu-id="ff295-110">Sub-key</span></span>       |                                                                                                         <span data-ttu-id="ff295-111">説明</span><span class="sxs-lookup"><span data-stu-id="ff295-111">Description</span></span>                                                                                                          |
   |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="ff295-112">**インストール パス**</span><span class="sxs-lookup"><span data-stu-id="ff295-112">**InstallPath**</span></span>   |                                             <span data-ttu-id="ff295-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしたインストール パスがリストされます。</span><span class="sxs-lookup"><span data-stu-id="ff295-113">Lists the installation path where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>                                              |
   | <span data-ttu-id="ff295-114">**ProductEdition**</span><span class="sxs-lookup"><span data-stu-id="ff295-114">**ProductEdition**</span></span> |                                                        <span data-ttu-id="ff295-115">以下のエディションがリストされます。</span><span class="sxs-lookup"><span data-stu-id="ff295-115">Lists the edition, including:</span></span><br /><br /> <span data-ttu-id="ff295-116">-開発者</span><span class="sxs-lookup"><span data-stu-id="ff295-116">-   Developer</span></span><br /><span data-ttu-id="ff295-117">ブランチ</span><span class="sxs-lookup"><span data-stu-id="ff295-117">-   Branch</span></span><br /><span data-ttu-id="ff295-118">標準</span><span class="sxs-lookup"><span data-stu-id="ff295-118">-   Standard</span></span><br /><span data-ttu-id="ff295-119">-エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="ff295-119">-   Enterprise</span></span>                                                         |
   | <span data-ttu-id="ff295-120">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="ff295-120">**ProductVersion**</span></span> | <span data-ttu-id="ff295-121">基本の製品バージョンがリストされます。</span><span class="sxs-lookup"><span data-stu-id="ff295-121">Lists the base product version.</span></span> <span data-ttu-id="ff295-122">サービス パックおよび累積更新プログラムを含め、特定の製品バージョンを参照してください。[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="ff295-122">For specific product version, including service packs and cumulative updates, see [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span> |

## <a name="use-the-control-panel"></a><span data-ttu-id="ff295-123">コントロール パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff295-123">Use the control panel</span></span>

1.  <span data-ttu-id="ff295-124">選択**開始**、型`Programs and Features`、し、開きます。</span><span class="sxs-lookup"><span data-stu-id="ff295-124">Select **Start**, type `Programs and Features`, and then open it.</span></span>  

2. <span data-ttu-id="ff295-125">一覧で、次のように選択します。 **Microsoft BizTalk Server**します。</span><span class="sxs-lookup"><span data-stu-id="ff295-125">In the list, select **Microsoft BizTalk Server**.</span></span> <span data-ttu-id="ff295-126">バージョンおよびエディションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff295-126">The version and edition are listed.</span></span>

<span data-ttu-id="ff295-127">参照してください[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="ff295-127">See [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff295-128">参照</span><span class="sxs-lookup"><span data-stu-id="ff295-128">See Also</span></span>  
 [<span data-ttu-id="ff295-129">開始するには</span><span class="sxs-lookup"><span data-stu-id="ff295-129">Get started</span></span>](../core/getting-started-with-biztalk-server.md)