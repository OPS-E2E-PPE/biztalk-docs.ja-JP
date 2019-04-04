---
title: アプリケーションを 64 ビット アイテムを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, 64-bit support
- scripts, 64-bit support
- virtual directories, 64-bit support
- artifacts, applications
- 64-bit support, COM components
- 64-bit support, virtual directories
- applications, artifacts
- 64-bit support, scripts
- 64-bit support, artifacts
- COM components, 64-bit support
- BizTalk Server, 64-bit support
- applications, 64-bit support
ms.assetid: 46aca7d4-c5be-421e-b16d-7f3095c8cc67
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979b7be419be6b39c5a80fcd1548af7404588e01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012867"
---
# <a name="how-to-add-a-64-bit-artifact-to-an-application"></a><span data-ttu-id="e3939-102">64 ビット アイテムをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="e3939-102">How to Add a 64-Bit Artifact to an Application</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e3939-103">では、64 ビット アプリケーションもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e3939-103">includes support for 64-bit applications.</span></span> <span data-ttu-id="e3939-104">つまり、32 ビット アイテムと同じ方法で 64 ビット アイテムを BizTalk アプリケーションに追加できます。ただし、次の 64 ビット アイテムを 32 ビットのコンピューターにインストールすると次のような問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3939-104">This means that you can add 64-bit artifacts to a BizTalk application in the same manner as 32-bit artifacts; however, you may encounter the following issues when installing the following 64-bit artifacts on a 32-bit computer:</span></span>  
  
- <span data-ttu-id="e3939-105">**64 ビット ワーカー プロセスを実行している Web サーバーから仮想ディレクトリ。**</span><span class="sxs-lookup"><span data-stu-id="e3939-105">**Virtual directory from a Web server that is running a 64-bit worker process.**</span></span> <span data-ttu-id="e3939-106">仮想ディレクトリは 32 ビット コンピューターにインストールされますが、正常に機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3939-106">The virtual directory will install on a 32-bit computer, but it may not function correctly.</span></span> <span data-ttu-id="e3939-107">不一致がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e3939-107">A mismatch will be logged.</span></span>  
  
- <span data-ttu-id="e3939-108">**アンマネージ COM またはマネージ COM + コンポーネントは、64 ビットとしてマークします。**</span><span class="sxs-lookup"><span data-stu-id="e3939-108">**Unmanaged COM or Managed COM+ components marked as 64 bit.**</span></span> <span data-ttu-id="e3939-109">これらのコンポーネントは、32 ビット コンピューターにはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="e3939-109">These components will not install on a 32-bit computer.</span></span>  
  
- <span data-ttu-id="e3939-110">**64 ビットの .exe ファイルとして保存されたスクリプトです。**</span><span class="sxs-lookup"><span data-stu-id="e3939-110">**64-bit scripts saved as .exe files.**</span></span> <span data-ttu-id="e3939-111">この種類のスクリプトは正常に機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3939-111">This type of script may not function correctly.</span></span>  
  
  <span data-ttu-id="e3939-112">成果物を追加する方法の一般的な手順は、[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3939-112">For general instructions on adding artifacts, see [How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md).</span></span> <span data-ttu-id="e3939-113">特定の成果物の種類を追加する手順については、[管理成果物](../core/managing-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3939-113">For instructions on adding specific artifact types, see [Managing Artifacts](../core/managing-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3939-114">参照</span><span class="sxs-lookup"><span data-stu-id="e3939-114">See Also</span></span>  
 <span data-ttu-id="e3939-115">[作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e3939-115">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="e3939-116">BizTalk アプリケーションをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e3939-116">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)