---
title: "パイプライン コンポーネントの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84ee3255c38e26c5f5d6d19797cba03ba549668b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-pipeline-components"></a><span data-ttu-id="ed15e-102">パイプライン コンポーネントの展開</span><span class="sxs-lookup"><span data-stu-id="ed15e-102">Deploying Pipeline Components</span></span>
<span data-ttu-id="ed15e-103">すべての .NET パイプライン コンポーネント アセンブリ (ネイティブおよびカスタム) がである必要があります、 \<*インストール ディレクトリ*> \Pipeline Components フォルダー、サーバーによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ed15e-103">All the .NET pipeline component assemblies (native and custom) must be located in the \<*installation directory*>\Pipeline Components folder to be executed by the server.</span></span> <span data-ttu-id="ed15e-104">カスタム コンポーネントを持つパイプラインを複数のサーバーに展開するには、各サーバー上の指定のフォルダーに、コンポーネントのバイナリが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed15e-104">If the pipeline with a custom component will be deployed across several servers, the component's binaries must be present in the specified folder on every server.</span></span>  
  
 <span data-ttu-id="ed15e-105">BizTalk ランタイムで使用するカスタム パイプライン コンポーネントを、グローバル アセンブリ キャッシュ (GAC) に追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed15e-105">You do not need to add a custom pipeline component to be used by the BizTalk Runtime to the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="ed15e-106">パイプラインのカスタム COM コンポーネントも、そのコンピューターに COM コンポーネントとして登録されている限り、ツールボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed15e-106">Custom COM components in the pipeline will also appear in the Toolbox, provided they are registered on the computer as a COM component.</span></span> <span data-ttu-id="ed15e-107">カスタム .NET パイプライン コンポーネントを配置する必要があります、 \<*インストール ディレクトリ*> \Pipeline Components フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ed15e-107">Custom .NET pipeline components must be placed into the \<*installation directory*>\Pipeline Components folder.</span></span>  
  
 <span data-ttu-id="ed15e-108">バイナリ ファイルを正しい場所に配置した後、コンポーネントをツールボックスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed15e-108">After the binary files are in the correct location, you need to add the component to the Toolbox.</span></span> <span data-ttu-id="ed15e-109">パイプライン コンポーネントをツールボックスに追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)です。</span><span class="sxs-lookup"><span data-stu-id="ed15e-109">For instructions on adding the pipeline component to the Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed15e-110">参照</span><span class="sxs-lookup"><span data-stu-id="ed15e-110">See Also</span></span>  
 [<span data-ttu-id="ed15e-111">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="ed15e-111">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)