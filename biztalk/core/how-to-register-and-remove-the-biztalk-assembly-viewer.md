---
title: 登録および BizTalk アセンブリ ビューアーを削除する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6ad3628f61fec11f135bf2235f5e0d25f52992d3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970032"
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a><span data-ttu-id="c90c4-102">BizTalk アセンブリ ビューアーを登録および削除する方法</span><span class="sxs-lookup"><span data-stu-id="c90c4-102">How to Register and Remove the BizTalk Assembly Viewer</span></span>
<span data-ttu-id="c90c4-103">BizTalk アセンブリ ビューアーは、BizTalk Server のセットアップ時に自動的に登録されません。</span><span class="sxs-lookup"><span data-stu-id="c90c4-103">The BizTalk Assembly Viewer is not registered automatically during BizTalk Server setup.</span></span> <span data-ttu-id="c90c4-104">BizTalk アセンブリ ビューアーを登録または削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c90c4-104">To register or remove the BizTalk Assembly Viewer, follow these steps.</span></span>  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a><span data-ttu-id="c90c4-105">Windows レジストリにアセンブリ ビューアーを追加するには</span><span class="sxs-lookup"><span data-stu-id="c90c4-105">To add Assembly Viewer to the Windows registry</span></span>  
  
1.  <span data-ttu-id="c90c4-106">**開始** メニューのをクリックして**実行**です。</span><span class="sxs-lookup"><span data-stu-id="c90c4-106">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="c90c4-107">[実行] ダイアログ ボックスに入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="c90c4-107">In the Run dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="c90c4-108">コマンド ラインに移動\< *BizTalk Server のインストール フォルダー*\>\Developer Tools\ BTSAsmExt.dll があります。</span><span class="sxs-lookup"><span data-stu-id="c90c4-108">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="c90c4-109">コマンド ラインで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c90c4-109">At the command line, type:</span></span>  
  
     <span data-ttu-id="c90c4-110">regsvr32 BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="c90c4-110">regsvr32 BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="c90c4-111">アセンブリ ビューの使用を開始するには、コンピューターからログオフしてログオンし直します。</span><span class="sxs-lookup"><span data-stu-id="c90c4-111">To begin using Assembly View, log off and then log back onto the computer.</span></span>  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a><span data-ttu-id="c90c4-112">Windows レジストリからアセンブリ ビューアーを削除するには</span><span class="sxs-lookup"><span data-stu-id="c90c4-112">To remove Assembly Viewer from the Windows registry</span></span>  
  
1.  <span data-ttu-id="c90c4-113">**開始** メニューのをクリックして**実行**です。</span><span class="sxs-lookup"><span data-stu-id="c90c4-113">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="c90c4-114">**実行** ダイアログ ボックスで、「 **cmd**です。</span><span class="sxs-lookup"><span data-stu-id="c90c4-114">In the **Run** dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="c90c4-115">コマンド ラインに移動\< *BizTalk Server のインストール フォルダー*\>\Developer Tools\ BTSAsmExt.dll があります。</span><span class="sxs-lookup"><span data-stu-id="c90c4-115">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="c90c4-116">コマンド ラインで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c90c4-116">At the command line, type:</span></span>  
  
     <span data-ttu-id="c90c4-117">regsvr32/u BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="c90c4-117">regsvr32/u BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="c90c4-118">削除を完了するには、コンピューターからログオフしてログオンし直します。</span><span class="sxs-lookup"><span data-stu-id="c90c4-118">To complete the removal, log off and then log back onto the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90c4-119">参照</span><span class="sxs-lookup"><span data-stu-id="c90c4-119">See Also</span></span>  
 [<span data-ttu-id="c90c4-120">BizTalk アセンブリ ビューアーを使用したアセンブリの表示</span><span class="sxs-lookup"><span data-stu-id="c90c4-120">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)