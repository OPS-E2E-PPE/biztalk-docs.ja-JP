---
title: デプロイ時にファイルのアイテムの状態 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4f9abe5de90996d883a0c104985e30782a40188
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392927"
---
# <a name="status-of-file-artifacts-during-deployment"></a><span data-ttu-id="ecb57-102">デプロイ時にファイルのアイテムの状態</span><span class="sxs-lookup"><span data-stu-id="ecb57-102">Status of File Artifacts During Deployment</span></span>
<span data-ttu-id="ecb57-103">前または処理後のスクリプトを実行するときに、どのようなファイル ベースのアイテムがファイル システムに存在するかを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecb57-103">You may need to know what file-based artifacts exist on the file system when a pre- or post-processing script executes.</span></span> <span data-ttu-id="ecb57-104">たとえば、アンインストール中に実行して、特定のアイテムのファイルをファイル システムから削除する処理後のスクリプトをたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="ecb57-104">For example, you might want a post-processing script to run during uninstallation and delete a certain artifact file from the file system.</span></span> <span data-ttu-id="ecb57-105">ファイル ベースのアイテムは、BizTalk データベース内の表現に加えて、ローカル ファイル システム上のファイルとして存在できる成果物です。</span><span class="sxs-lookup"><span data-stu-id="ecb57-105">File-based artifacts are artifacts that can exist as files on the local file system, in addition to their representation in the BizTalk databases.</span></span> <span data-ttu-id="ecb57-106">ファイル ベースのアイテムには、COM コンポーネント、.NET アセンブリ、BizTalk アセンブリ、BAM アイテム、アドホック ファイル、スクリプト、およびバインド ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="ecb57-106">Examples of file-based artifacts are COM components, .NET assemblies, BizTalk assemblies, BAM artifacts, ad hoc files, scripts, and binding files.</span></span>  
  
 <span data-ttu-id="ecb57-107">次の表は、展開プロセスの各ポイントで成果物のファイルの状態をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="ecb57-107">The following table summarizes the status of the artifact files at each point in the deployment process.</span></span>  
  
|<span data-ttu-id="ecb57-108">展開プロセスをポイントします。</span><span class="sxs-lookup"><span data-stu-id="ecb57-108">Point in the Deployment Process</span></span>|<span data-ttu-id="ecb57-109">アプリケーション アイテム ファイルの状態</span><span class="sxs-lookup"><span data-stu-id="ecb57-109">Status of Application Artifact Files</span></span>|  
|-------------------------------------|------------------------------------------|  
|<span data-ttu-id="ecb57-110">インストール前</span><span class="sxs-lookup"><span data-stu-id="ecb57-110">Pre-installation</span></span>|<span data-ttu-id="ecb57-111">System.BizTalk.File の種類のファイルのみがローカル ファイル システムに存在します。</span><span class="sxs-lookup"><span data-stu-id="ecb57-111">Only files of the type System.BizTalk.File exist on the local file system.\*</span></span>|  
|<span data-ttu-id="ecb57-112">インストール後</span><span class="sxs-lookup"><span data-stu-id="ecb57-112">Post-installation</span></span>|<span data-ttu-id="ecb57-113">ローカル ファイル システム上のすべてのファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="ecb57-113">All files exist on the local file system.\*</span></span>|  
|<span data-ttu-id="ecb57-114">アンインストール前</span><span class="sxs-lookup"><span data-stu-id="ecb57-114">Pre-uninstallation</span></span>|<span data-ttu-id="ecb57-115">ローカル ファイル システム上のすべてのファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="ecb57-115">All files exist on the local file system.\*</span></span>|  
|<span data-ttu-id="ecb57-116">後のアンインストール</span><span class="sxs-lookup"><span data-stu-id="ecb57-116">Post-uninstallation</span></span>|<span data-ttu-id="ecb57-117">すべてのファイルがローカル ファイル システムから削除されています。</span><span class="sxs-lookup"><span data-stu-id="ecb57-117">All files have been deleted from the local file system.</span></span>|  
|<span data-ttu-id="ecb57-118">前のインポート</span><span class="sxs-lookup"><span data-stu-id="ecb57-118">Pre-import</span></span>|<span data-ttu-id="ecb57-119">ファイルがないローカル ファイル システムで、アプリケーションがローカル コンピューターにインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="ecb57-119">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
|<span data-ttu-id="ecb57-120">インポート後</span><span class="sxs-lookup"><span data-stu-id="ecb57-120">Post-import</span></span>|<span data-ttu-id="ecb57-121">ファイルがないローカル ファイル システムで、アプリケーションがローカル コンピューターにインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="ecb57-121">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
  
 <span data-ttu-id="ecb57-122">\* ファイルは、ファイルがアプリケーションに追加されたときに、有効な変換先の場所が指定されている場合にのみ、ローカル ファイル システムに存在します。</span><span class="sxs-lookup"><span data-stu-id="ecb57-122">\* Files exist on the local file system only if a valid destination location was specified when the file was added to the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb57-123">参照</span><span class="sxs-lookup"><span data-stu-id="ecb57-123">See Also</span></span>  
 [<span data-ttu-id="ecb57-124">処理前および処理後のスクリプトを使用したアプリケーション展開のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ecb57-124">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)