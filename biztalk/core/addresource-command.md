---
title: "AddResource コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 875a087fa3afe7515aee2c406cbc47551bea1f4d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="addresource-command"></a><span data-ttu-id="8df8b-102">AddResource コマンド</span><span class="sxs-lookup"><span data-stu-id="8df8b-102">AddResource Command</span></span>
<span data-ttu-id="8df8b-103">このセクションの各トピックでは、AddResource コマンドの各種パラメーターについてのリファレンス情報を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="8df8b-103">The topics in this section provide reference information about the parameters of the AddResource command.</span></span> <span data-ttu-id="8df8b-104">このコマンドで使用されるパラメーターは、追加するアイテムの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8df8b-104">The parameters that you use with this command vary according to the type of artifact that you want to add.</span></span> <span data-ttu-id="8df8b-105">成果物の種類の完全な一覧を取得するを使用して、 **ListTypes**コマンドを」の説明に従って[ListTypes コマンド](../core/listtypes-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="8df8b-105">To obtain complete lists of artifact types, use the **ListTypes** command, as described in [ListTypes Command](../core/listtypes-command.md).</span></span>  
  
 <span data-ttu-id="8df8b-106">次のコマンドを入力することによって、追加するアイテムの種類に応じたヘルプを参照できます。</span><span class="sxs-lookup"><span data-stu-id="8df8b-106">To get help for adding a particular artifact type, type the following command:</span></span>  
  
 <span data-ttu-id="8df8b-107">**BTSTask AddResource/Type:**\<*型名*\> **/しますか?**</span><span class="sxs-lookup"><span data-stu-id="8df8b-107">**BTSTask AddResource /Type:**\<*type name*\> **/?**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8df8b-108">追加するアイテムのパス名 (あるいはファイル名) が極端に長いと、アイテムをアプリケーションに追加するときにエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8df8b-108">If the artifact you are adding has a very long path name, including the file name, the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="8df8b-109">パスは 260 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="8df8b-109">A path cannot exceed 260 characters.</span></span>  
>   
>  <span data-ttu-id="8df8b-110">追加操作に失敗した場合、その操作中に行われたすべてのアクションがロールバックされます。ただし、このコマンドでグローバル アセンブリ キャッシュに追加されたアセンブリは削除されず、そのまま残ってしまいます。また、Windows レジストリにエントリが書き込まれた場合も、エントリは削除されません。</span><span class="sxs-lookup"><span data-stu-id="8df8b-110">If an add operation fails, all actions taken during the operation are rolled back, except that assemblies are not removed from the global assembly cache if they were added by this command, and entries are not removed from the Windows registry if any entries were made.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8df8b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8df8b-111">In This Section</span></span>  
  
-   [<span data-ttu-id="8df8b-112">AddResource コマンド: BizTalk アセンブリ</span><span class="sxs-lookup"><span data-stu-id="8df8b-112">AddResource Command: BizTalk Assembly</span></span>](../core/addresource-command-biztalk-assembly.md)  
  
-   [<span data-ttu-id="8df8b-113">AddResource コマンド: BizTalk バインディング</span><span class="sxs-lookup"><span data-stu-id="8df8b-113">AddResource Command: BizTalk Binding</span></span>](../core/addresource-command-biztalk-binding.md)  
  
-   [<span data-ttu-id="8df8b-114">AddResource コマンド: .NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="8df8b-114">AddResource Command: .NET Assembly</span></span>](../core/addresource-command-net-assembly.md)  
  
-   [<span data-ttu-id="8df8b-115">AddResource コマンド: BAM アイテム</span><span class="sxs-lookup"><span data-stu-id="8df8b-115">AddResource Command: BAM Artifact</span></span>](../core/addresource-command-bam-artifact.md)  
  
-   [<span data-ttu-id="8df8b-116">AddResource コマンド: 証明書</span><span class="sxs-lookup"><span data-stu-id="8df8b-116">AddResource Command: Certificate</span></span>](../core/addresource-command-certificate.md)  
  
-   [<span data-ttu-id="8df8b-117">AddResource コマンド: COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8df8b-117">AddResource Command: COM Component</span></span>](../core/addresource-command-com-component.md)  
  
-   [<span data-ttu-id="8df8b-118">AddResource コマンド: ファイル</span><span class="sxs-lookup"><span data-stu-id="8df8b-118">AddResource Command: File</span></span>](../core/addresource-command-file.md)  
  
-   [<span data-ttu-id="8df8b-119">AddResource コマンド: 前処理スクリプト</span><span class="sxs-lookup"><span data-stu-id="8df8b-119">AddResource Command: Preprocessing Script</span></span>](../core/addresource-command-preprocessing-script.md)  
  
-   [<span data-ttu-id="8df8b-120">AddResource コマンド: 処理後のスクリプト</span><span class="sxs-lookup"><span data-stu-id="8df8b-120">AddResource Command: Postprocessing Script</span></span>](../core/addresource-command-postprocessing-script.md)  
  
-   [<span data-ttu-id="8df8b-121">AddResource コマンド: ポリシー</span><span class="sxs-lookup"><span data-stu-id="8df8b-121">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)  
  
-   [<span data-ttu-id="8df8b-122">AddResource コマンド: 仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="8df8b-122">AddResource Command: Virtual Directory</span></span>](../core/addresource-command-virtual-directory.md)