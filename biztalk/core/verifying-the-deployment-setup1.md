---
title: "展開 Setup1 の検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLASSPATH, verifying
- deployment, verifying setup
ms.assetid: 6c719e4c-9a61-480f-a4e4-0a1c518d1364
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5799d164dc2470236c3ab0286e38d19986a4d5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="verifying-the-deployment-setup"></a><span data-ttu-id="f8038-102">展開セットアップの確認</span><span class="sxs-lookup"><span data-stu-id="f8038-102">Verifying the Deployment Setup</span></span>
<span data-ttu-id="f8038-103">BizTalk Server を使用してバインド ファイルをインポートする前に、以下の項目について確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8038-103">Before you use the BizTalk Server to import a binding file, you must verify the following:</span></span>  
  
-   <span data-ttu-id="f8038-104">CLASSPATH が JD Edwards EnterpriseOne 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="f8038-104">The CLASSPATH is pointing to a specific location for the JD Edwards EnterpriseOne-specific files.</span></span> <span data-ttu-id="f8038-105">新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="f8038-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f8038-106">新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="f8038-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f8038-107">JD Edwards EnterpriseOne システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="f8038-107">JD Edwards EnterpriseOne system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="f8038-108">詳細については、次を参照してください。[展開の制限事項](../core/deployment-limitations4.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8038-108">For more information see [Deployment Limitations](../core/deployment-limitations4.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8038-109">参照</span><span class="sxs-lookup"><span data-stu-id="f8038-109">See Also</span></span>  
 [<span data-ttu-id="f8038-110">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="f8038-110">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)