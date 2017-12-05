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
ms.openlocfilehash: 041bd8c6e6fa9c3969be18f0804460c00de5f11a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-pipeline-components"></a><span data-ttu-id="2ad7d-102">パイプライン コンポーネントの展開</span><span class="sxs-lookup"><span data-stu-id="2ad7d-102">Deploying Pipeline Components</span></span>
<span data-ttu-id="2ad7d-103">すべての .NET パイプライン コンポーネント アセンブリ (ネイティブおよびカスタム) がである必要があります、 \<*インストール ディレクトリ*\>サーバーによって実行される \Pipeline Components フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="2ad7d-103">All the .NET pipeline component assemblies (native and custom) must be located in the \<*installation directory*\>\Pipeline Components folder to be executed by the server.</span></span> <span data-ttu-id="2ad7d-104">カスタム コンポーネントを持つパイプラインを複数のサーバーに展開するには、各サーバー上の指定のフォルダーに、コンポーネントのバイナリが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ad7d-104">If the pipeline with a custom component will be deployed across several servers, the component's binaries must be present in the specified folder on every server.</span></span>  
  
 <span data-ttu-id="2ad7d-105">BizTalk ランタイムで使用するカスタム パイプライン コンポーネントを、グローバル アセンブリ キャッシュ (GAC) に追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2ad7d-105">You do not need to add a custom pipeline component to be used by the BizTalk Runtime to the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="2ad7d-106">パイプラインのカスタム COM コンポーネントも、そのコンピューターに COM コンポーネントとして登録されている限り、ツールボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ad7d-106">Custom COM components in the pipeline will also appear in the Toolbox, provided they are registered on the computer as a COM component.</span></span> <span data-ttu-id="2ad7d-107">カスタム .NET パイプライン コンポーネントを配置する必要があります、 \<*インストール ディレクトリ*\>\Pipeline Components フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="2ad7d-107">Custom .NET pipeline components must be placed into the \<*installation directory*\>\Pipeline Components folder.</span></span>  
  
 <span data-ttu-id="2ad7d-108">バイナリ ファイルを正しい場所に配置した後、コンポーネントをツールボックスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ad7d-108">After the binary files are in the correct location, you need to add the component to the Toolbox.</span></span> <span data-ttu-id="2ad7d-109">パイプライン コンポーネントをツールボックスに追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)です。</span><span class="sxs-lookup"><span data-stu-id="2ad7d-109">For instructions on adding the pipeline component to the Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad7d-110">参照</span><span class="sxs-lookup"><span data-stu-id="2ad7d-110">See Also</span></span>  
 [<span data-ttu-id="2ad7d-111">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="2ad7d-111">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)