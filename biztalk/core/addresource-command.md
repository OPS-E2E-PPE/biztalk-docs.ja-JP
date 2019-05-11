---
title: AddResource コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d8831cbac23343186eb4df9959378cb49fe279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360202"
---
# <a name="addresource-command"></a><span data-ttu-id="69ced-102">AddResource コマンド</span><span class="sxs-lookup"><span data-stu-id="69ced-102">AddResource Command</span></span>
<span data-ttu-id="69ced-103">このセクションのトピックでは、AddResource コマンドのパラメーターに関する参照情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="69ced-103">The topics in this section provide reference information about the parameters of the AddResource command.</span></span> <span data-ttu-id="69ced-104">このコマンドで使用するパラメーターを追加するアイテムの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="69ced-104">The parameters that you use with this command vary according to the type of artifact that you want to add.</span></span> <span data-ttu-id="69ced-105">成果物の種類の完全な一覧を取得する、 **ListTypes** 」の説明に従って、コマンド[ListTypes コマンド](../core/listtypes-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="69ced-105">To obtain complete lists of artifact types, use the **ListTypes** command, as described in [ListTypes Command](../core/listtypes-command.md).</span></span>  
  
 <span data-ttu-id="69ced-106">に特定の成果物の種類の追加のヘルプを取得するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="69ced-106">To get help for adding a particular artifact type, type the following command:</span></span>  
  
 <span data-ttu-id="69ced-107">**BTSTask AddResource/Type:**\<*型名*\> **/でしょうか。**</span><span class="sxs-lookup"><span data-stu-id="69ced-107">**BTSTask AddResource /Type:**\<*type name*\> **/?**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69ced-108">追加するアイテムがあるファイル名を含む非常に長いパス名をアプリケーションにアイテムを追加する操作が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="69ced-108">If the artifact you are adding has a very long path name, including the file name, the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="69ced-109">パスは 260 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="69ced-109">A path cannot exceed 260 characters.</span></span>  
>   
>  <span data-ttu-id="69ced-110">追加操作が失敗した場合、操作中に実行されたすべてのアクションはロールバックする点を除いて、このコマンドでは、追加された場合にすべてのエントリが加えられた場合、エントリは Windows レジストリから削除されませんアセンブリはグローバル アセンブリ キャッシュから削除されません。</span><span class="sxs-lookup"><span data-stu-id="69ced-110">If an add operation fails, all actions taken during the operation are rolled back, except that assemblies are not removed from the global assembly cache if they were added by this command, and entries are not removed from the Windows registry if any entries were made.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69ced-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="69ced-111">In This Section</span></span>  
  
-   [<span data-ttu-id="69ced-112">AddResource コマンド:BizTalk アセンブリ</span><span class="sxs-lookup"><span data-stu-id="69ced-112">AddResource Command: BizTalk Assembly</span></span>](../core/addresource-command-biztalk-assembly.md)  
  
-   [<span data-ttu-id="69ced-113">AddResource コマンド:BizTalk バインド</span><span class="sxs-lookup"><span data-stu-id="69ced-113">AddResource Command: BizTalk Binding</span></span>](../core/addresource-command-biztalk-binding.md)  
  
-   [<span data-ttu-id="69ced-114">AddResource コマンド: .NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="69ced-114">AddResource Command: .NET Assembly</span></span>](../core/addresource-command-net-assembly.md)  
  
-   [<span data-ttu-id="69ced-115">AddResource コマンド:BAM アイテム</span><span class="sxs-lookup"><span data-stu-id="69ced-115">AddResource Command: BAM Artifact</span></span>](../core/addresource-command-bam-artifact.md)  
  
-   [<span data-ttu-id="69ced-116">AddResource コマンド:証明書</span><span class="sxs-lookup"><span data-stu-id="69ced-116">AddResource Command: Certificate</span></span>](../core/addresource-command-certificate.md)  
  
-   [<span data-ttu-id="69ced-117">AddResource コマンド:COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="69ced-117">AddResource Command: COM Component</span></span>](../core/addresource-command-com-component.md)  
  
-   [<span data-ttu-id="69ced-118">AddResource コマンド:ファイル</span><span class="sxs-lookup"><span data-stu-id="69ced-118">AddResource Command: File</span></span>](../core/addresource-command-file.md)  
  
-   [<span data-ttu-id="69ced-119">AddResource コマンド:処理前のスクリプト</span><span class="sxs-lookup"><span data-stu-id="69ced-119">AddResource Command: Preprocessing Script</span></span>](../core/addresource-command-preprocessing-script.md)  
  
-   [<span data-ttu-id="69ced-120">AddResource コマンド:処理後のスクリプト</span><span class="sxs-lookup"><span data-stu-id="69ced-120">AddResource Command: Postprocessing Script</span></span>](../core/addresource-command-postprocessing-script.md)  
  
-   [<span data-ttu-id="69ced-121">AddResource コマンド:ポリシー</span><span class="sxs-lookup"><span data-stu-id="69ced-121">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)  
  
-   [<span data-ttu-id="69ced-122">AddResource コマンド:仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="69ced-122">AddResource Command: Virtual Directory</span></span>](../core/addresource-command-virtual-directory.md)