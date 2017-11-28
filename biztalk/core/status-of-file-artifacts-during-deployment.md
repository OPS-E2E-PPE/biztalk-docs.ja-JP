---
title: "配置時にファイルのアイテムの状態 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1f57716741bb61c7a9f6f012aed14ec04c8e250
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="status-of-file-artifacts-during-deployment"></a><span data-ttu-id="8030f-102">展開中のファイル アイテムの状態</span><span class="sxs-lookup"><span data-stu-id="8030f-102">Status of File Artifacts During Deployment</span></span>
<span data-ttu-id="8030f-103">処理前または処理後のスクリプトの実行時に、ファイル システム上にどのようなファイルベースのアイテムが存在するかを知ることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8030f-103">You may need to know what file-based artifacts exist on the file system when a pre- or post-processing script executes.</span></span> <span data-ttu-id="8030f-104">たとえば、アンインストール時に処理後のスクリプトを実行して、特定のアイテム ファイルをファイル システムから削除する場合です。</span><span class="sxs-lookup"><span data-stu-id="8030f-104">For example, you might want a post-processing script to run during uninstallation and delete a certain artifact file from the file system.</span></span> <span data-ttu-id="8030f-105">ファイルベースのアイテムは、BizTalk データベース内の表現に加えて、ローカル ファイル システムにもファイルとして存在することができるアイテムです。</span><span class="sxs-lookup"><span data-stu-id="8030f-105">File-based artifacts are artifacts that can exist as files on the local file system, in addition to their representation in the BizTalk databases.</span></span> <span data-ttu-id="8030f-106">ファイルベースのアイテムの例としては、COM コンポーネント、.NET アセンブリ、BizTalk アセンブリ、BAM アイテム、アドホック ファイル、スクリプト、およびバインド ファイルが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="8030f-106">Examples of file-based artifacts are COM components, .NET assemblies, BizTalk assemblies, BAM artifacts, ad hoc files, scripts, and binding files.</span></span>  
  
 <span data-ttu-id="8030f-107">次の表は、展開プロセスの各時点における、アイテム ファイルの状態をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8030f-107">The following table summarizes the status of the artifact files at each point in the deployment process.</span></span>  
  
|<span data-ttu-id="8030f-108">展開プロセスの時点</span><span class="sxs-lookup"><span data-stu-id="8030f-108">Point in the Deployment Process</span></span>|<span data-ttu-id="8030f-109">アプリケーション アイテム ファイルの状態</span><span class="sxs-lookup"><span data-stu-id="8030f-109">Status of Application Artifact Files</span></span>|  
|-------------------------------------|------------------------------------------|  
|<span data-ttu-id="8030f-110">インストール前</span><span class="sxs-lookup"><span data-stu-id="8030f-110">Pre-installation</span></span>|<span data-ttu-id="8030f-111">ローカル ファイル システムには、種類が System.BizTalk.File であるファイルだけが存在します。*</span><span class="sxs-lookup"><span data-stu-id="8030f-111">Only files of the type System.BizTalk.File exist on the local file system.*</span></span>|  
|<span data-ttu-id="8030f-112">インストール後</span><span class="sxs-lookup"><span data-stu-id="8030f-112">Post-installation</span></span>|<span data-ttu-id="8030f-113">ローカル ファイル システムには、すべてのファイルが存在します。*</span><span class="sxs-lookup"><span data-stu-id="8030f-113">All files exist on the local file system.*</span></span>|  
|<span data-ttu-id="8030f-114">アンインストール前</span><span class="sxs-lookup"><span data-stu-id="8030f-114">Pre-uninstallation</span></span>|<span data-ttu-id="8030f-115">ローカル ファイル システムには、すべてのファイルが存在します。*</span><span class="sxs-lookup"><span data-stu-id="8030f-115">All files exist on the local file system.*</span></span>|  
|<span data-ttu-id="8030f-116">アンインストール後</span><span class="sxs-lookup"><span data-stu-id="8030f-116">Post-uninstallation</span></span>|<span data-ttu-id="8030f-117">ローカル ファイル システムからはすべてのファイルが削除されています。</span><span class="sxs-lookup"><span data-stu-id="8030f-117">All files have been deleted from the local file system.</span></span>|  
|<span data-ttu-id="8030f-118">インポート前</span><span class="sxs-lookup"><span data-stu-id="8030f-118">Pre-import</span></span>|<span data-ttu-id="8030f-119">アプリケーションがローカル コンピューターにインストールされていない限り、ローカル ファイル システムにファイルは存在しません。</span><span class="sxs-lookup"><span data-stu-id="8030f-119">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
|<span data-ttu-id="8030f-120">インポート後</span><span class="sxs-lookup"><span data-stu-id="8030f-120">Post-import</span></span>|<span data-ttu-id="8030f-121">アプリケーションがローカル コンピューターにインストールされていない限り、ローカル ファイル システムにファイルは存在しません。</span><span class="sxs-lookup"><span data-stu-id="8030f-121">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
  
 <span data-ttu-id="8030f-122">\*ファイルは、有効なコピー先の場所は、ファイルがアプリケーションに追加したときに指定されていた場合にのみ、ローカル ファイル システムに存在します。</span><span class="sxs-lookup"><span data-stu-id="8030f-122">\* Files exist on the local file system only if a valid destination location was specified when the file was added to the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8030f-123">参照</span><span class="sxs-lookup"><span data-stu-id="8030f-123">See Also</span></span>  
 [<span data-ttu-id="8030f-124">前処理および後処理のスクリプトを使用したアプリケーションの展開のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8030f-124">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)