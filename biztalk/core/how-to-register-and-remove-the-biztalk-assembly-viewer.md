---
title: 登録および BizTalk アセンブリ ビューアーを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b78aeb8f0ebdbc1a7e05c8cfc45137b991b6eb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384392"
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a><span data-ttu-id="e13bc-102">BizTalk アセンブリ ビューアーを登録および削除する方法</span><span class="sxs-lookup"><span data-stu-id="e13bc-102">How to Register and Remove the BizTalk Assembly Viewer</span></span>
<span data-ttu-id="e13bc-103">BizTalk アセンブリ ビューアーは、BizTalk Server のセットアップ中に自動的に登録されていません。</span><span class="sxs-lookup"><span data-stu-id="e13bc-103">The BizTalk Assembly Viewer is not registered automatically during BizTalk Server setup.</span></span> <span data-ttu-id="e13bc-104">BizTalk アセンブリ ビューアーを削除または登録は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e13bc-104">To register or remove the BizTalk Assembly Viewer, follow these steps.</span></span>  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a><span data-ttu-id="e13bc-105">Windows レジストリにアセンブリ ビューアーを追加するには</span><span class="sxs-lookup"><span data-stu-id="e13bc-105">To add Assembly Viewer to the Windows registry</span></span>  
  
1.  <span data-ttu-id="e13bc-106">**開始** メニューのをクリックして**実行**します。</span><span class="sxs-lookup"><span data-stu-id="e13bc-106">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="e13bc-107">[実行] ダイアログ ボックスで、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="e13bc-107">In the Run dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="e13bc-108">移動しますからコマンド ラインで\< *BizTalk Server のインストール フォルダー*\>\Developer Tools\ BTSAsmExt.dll があります。</span><span class="sxs-lookup"><span data-stu-id="e13bc-108">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="e13bc-109">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e13bc-109">At the command line, type:</span></span>  
  
     <span data-ttu-id="e13bc-110">regsvr32 BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="e13bc-110">regsvr32 BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="e13bc-111">アセンブリ ビューを使用するには、ログオフしてログオンし、コンピューターに戻すにします。</span><span class="sxs-lookup"><span data-stu-id="e13bc-111">To begin using Assembly View, log off and then log back onto the computer.</span></span>  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a><span data-ttu-id="e13bc-112">Windows レジストリからアセンブリ ビューアーを削除するには</span><span class="sxs-lookup"><span data-stu-id="e13bc-112">To remove Assembly Viewer from the Windows registry</span></span>  
  
1.  <span data-ttu-id="e13bc-113">**開始** メニューのをクリックして**実行**します。</span><span class="sxs-lookup"><span data-stu-id="e13bc-113">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="e13bc-114">**実行**ダイアログ ボックスに「 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="e13bc-114">In the **Run** dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="e13bc-115">移動しますからコマンド ラインで\< *BizTalk Server のインストール フォルダー*\>\Developer Tools\ BTSAsmExt.dll があります。</span><span class="sxs-lookup"><span data-stu-id="e13bc-115">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="e13bc-116">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e13bc-116">At the command line, type:</span></span>  
  
     <span data-ttu-id="e13bc-117">regsvr32/u BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="e13bc-117">regsvr32/u BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="e13bc-118">削除を完了するには、ログオフしてログオンし、コンピューターに戻すにします。</span><span class="sxs-lookup"><span data-stu-id="e13bc-118">To complete the removal, log off and then log back onto the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13bc-119">参照</span><span class="sxs-lookup"><span data-stu-id="e13bc-119">See Also</span></span>  
 [<span data-ttu-id="e13bc-120">BizTalk アセンブリ ビューアーを使用したアセンブリの表示</span><span class="sxs-lookup"><span data-stu-id="e13bc-120">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)