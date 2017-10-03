---
title: "COM + の修正プログラム ロールアップ パッケージをインストールする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40610c649e00993323adedf0ea29330dd289a0e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-com-hotfix-rollup-packages"></a><span data-ttu-id="ab201-102">COM + の修正プログラム ロールアップ パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab201-102">Installing COM+ Hotfix Rollup Packages</span></span>
> [!NOTE]  
>  <span data-ttu-id="ab201-103">このトピックでは、Windows Server 2003 にのみ適用します。</span><span class="sxs-lookup"><span data-stu-id="ab201-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="ab201-104">最後のバージョンの Windows Server 2003 の COM + の修正プログラム ロールアップ パッケージと分散トランザクション コーディネーター (DTC) のプログラムのロールアップ パッケージの最新バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab201-104">You should install the last version of the Windows Server 2003 COM+ hotfix rollup package and latest version of the Distributed Transaction Coordinator (DTC) rollup package.</span></span> <span data-ttu-id="ab201-105">これは、パッケージには、多くのパフォーマンスや安定性の修正が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="ab201-105">This is because the packages include many performance and stability fixes.</span></span>  
  
 <span data-ttu-id="ab201-106">実行しているすべてのコンピューターにこれらのロールアップをインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とすべてのコンピューターで SQL Server を実行します。</span><span class="sxs-lookup"><span data-stu-id="ab201-106">You should install these rollups on all computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and on all computers running SQL Server.</span></span> <span data-ttu-id="ab201-107">ロールアップは、BizTalk ソリューションを高スループットのシナリオでも実行する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="ab201-107">The rollups are especially important for your BizTalk solution to perform well in high-throughput scenarios.</span></span>  
  
 <span data-ttu-id="ab201-108">修正された DTC の問題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab201-108">The DTC issues that have been fixed are as follows:</span></span>  
  
-   <span data-ttu-id="ab201-109">DTC の予期しないシャット ダウン</span><span class="sxs-lookup"><span data-stu-id="ab201-109">Unexpected DTC shutdown</span></span>  
  
-   <span data-ttu-id="ab201-110">メモリの断片化の問題</span><span class="sxs-lookup"><span data-stu-id="ab201-110">Memory fragmentation issues</span></span>  
  
-   <span data-ttu-id="ab201-111">DTC が負荷の下で応答を停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab201-111">DTC may stop responding under load</span></span>  
  
-   <span data-ttu-id="ab201-112">DTC リークが発生するメモリまたはを使用すると、応答を停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab201-112">DTC may leak memory or stop responding when used with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="ab201-113">負荷の下での DTC のパフォーマンスが改善されました</span><span class="sxs-lookup"><span data-stu-id="ab201-113">Performance of DTC under load has been improved</span></span>  
  
## <a name="installing-the-com-rollup-package"></a><span data-ttu-id="ab201-114">COM + ロールアップ パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab201-114">Installing the COM+ Rollup Package</span></span>  
 <span data-ttu-id="ab201-115">COM + ロールアップ パッケージが不要になったリリースしました。</span><span class="sxs-lookup"><span data-stu-id="ab201-115">COM+ is no longer releasing rollup packages.</span></span> <span data-ttu-id="ab201-116">最後の COM + のパッケージをインストールするには、この情報に従います。</span><span class="sxs-lookup"><span data-stu-id="ab201-116">Follow this information to install the last COM+ package:</span></span>  
  
-   <span data-ttu-id="ab201-117">COM + ロールアップの最終バージョンは、"Windows Server 2003 Service Pack 2 COM + 1.5年修正プログラム ロールアップ パッケージ 12年"です。</span><span class="sxs-lookup"><span data-stu-id="ab201-117">The final version of the COM+ rollup is the “Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12”.</span></span> <span data-ttu-id="ab201-118">この修正プログラムは、任意のバージョンの service pack がインストールされていないものも含め、Windows Server 2003 にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ab201-118">This hotfix will install on any version of Windows Server 2003, even those without a service pack installed.</span></span> <span data-ttu-id="ab201-119">この修正プログラムの詳細については、Microsoft サポート技術情報記事 934016 で参照できます["の可用性の Windows Server 2003 Service Pack 2 COM + 1.5年修正プログラム ロールアップ パッケージ 12年"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756)。</span><span class="sxs-lookup"><span data-stu-id="ab201-119">More information about this hotfix can be found in Microsoft Knowledge Base article 934016, ["Availability of Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).</span></span>  
  
## <a name="installing-the-dtc-rollup-package"></a><span data-ttu-id="ab201-120">DTC ロールアップ パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab201-120">Installing the DTC Rollup Package</span></span>  
 <span data-ttu-id="ab201-121">DTC は、COM + の独立したプログラムのロールアップ パッケージをリリースする予定です。</span><span class="sxs-lookup"><span data-stu-id="ab201-121">DTC will be releasing rollup packages independent of COM+.</span></span> <span data-ttu-id="ab201-122">DTC の最新のパッケージをインストールするためには、この情報に従います。</span><span class="sxs-lookup"><span data-stu-id="ab201-122">Follow this information to install the latest DTC package:</span></span>  
  
-   <span data-ttu-id="ab201-123">このドキュメントの作成時点では、最新の DTC の修正プログラムのロールアップは、「パッケージ 16」です。</span><span class="sxs-lookup"><span data-stu-id="ab201-123">As of this writing, the latest DTC hotfix rollup is “Package 16”.</span></span> <span data-ttu-id="ab201-124">この修正プログラムの詳細については、Microsoft サポート技術情報記事 958013 で参照できます[「は、Windows Server 2003 MS DTC の修正プログラム ロールアップ パッケージ 16 で修正 MS DTC の問題の一覧」](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span><span class="sxs-lookup"><span data-stu-id="ab201-124">More information about this hotfix can be found in Microsoft Knowledge Base article 958013, ["List of the MS DTC issues that are fixed in Windows Server 2003 MS DTC Hotfix Rollup Package 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span></span>  
  
     <span data-ttu-id="ab201-125">最新の DTC の修正プログラム ロールアップ パッケージに関するサポート技術情報の記事を検索によって見つかりますできます[http://support.microsoft.com](http://support.microsoft.com/) (引用符を含む)、句。</span><span class="sxs-lookup"><span data-stu-id="ab201-125">The KB article about the latest DTC hotfix rollup package can be found by searching [http://support.microsoft.com](http://support.microsoft.com/) for the phrase (including the quotes):</span></span>  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     <span data-ttu-id="ab201-126">この検索では、次のクエリ。</span><span class="sxs-lookup"><span data-stu-id="ab201-126">The following query does this search for you.</span></span> <span data-ttu-id="ab201-127">最新のものを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab201-127">Choose the latest one:</span></span>  
  
     [<span data-ttu-id="ab201-128">http://support.microsoft.com/search/default.aspx?query=「MS + DTC + 修正プログラム + ロールアップ + パッケージ」</span><span class="sxs-lookup"><span data-stu-id="ab201-128">http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"</span></span>](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)