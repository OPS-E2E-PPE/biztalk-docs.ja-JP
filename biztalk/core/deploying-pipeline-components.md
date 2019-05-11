---
title: パイプライン コンポーネントの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14ac8f8c91b0ed8b83a6bcbcf4664726c0079515
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389581"
---
# <a name="deploying-pipeline-components"></a><span data-ttu-id="ed5c0-102">パイプライン コンポーネントの展開</span><span class="sxs-lookup"><span data-stu-id="ed5c0-102">Deploying Pipeline Components</span></span>
<span data-ttu-id="ed5c0-103">すべての .NET パイプライン コンポーネント アセンブリ (ネイティブおよびカスタム) がである必要があります、 \<*インストール ディレクトリ*\>\Pipeline Components フォルダーに、サーバーによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ed5c0-103">All the .NET pipeline component assemblies (native and custom) must be located in the \<*installation directory*\>\Pipeline Components folder to be executed by the server.</span></span> <span data-ttu-id="ed5c0-104">カスタム コンポーネントを使用して、パイプラインがいくつかのサーバー間でデプロイされる場合、コンポーネントのバイナリがすべてのサーバーで指定したフォルダーに存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed5c0-104">If the pipeline with a custom component will be deployed across several servers, the component's binaries must be present in the specified folder on every server.</span></span>  
  
 <span data-ttu-id="ed5c0-105">グローバル アセンブリ キャッシュ (GAC) に BizTalk ランタイムで使用するカスタム パイプライン コンポーネントを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed5c0-105">You do not need to add a custom pipeline component to be used by the BizTalk Runtime to the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="ed5c0-106">パイプラインのカスタム COM コンポーネントを COM コンポーネントとしてコンピューターに登録されている限りも、ツールボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed5c0-106">Custom COM components in the pipeline will also appear in the Toolbox, provided they are registered on the computer as a COM component.</span></span> <span data-ttu-id="ed5c0-107">カスタム .NET パイプライン コンポーネントを配置する必要があります、 \<*インストール ディレクトリ*\>\Pipeline Components フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ed5c0-107">Custom .NET pipeline components must be placed into the \<*installation directory*\>\Pipeline Components folder.</span></span>  
  
 <span data-ttu-id="ed5c0-108">バイナリ ファイルは、正しい位置には後、は、ツールボックスにコンポーネントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5c0-108">After the binary files are in the correct location, you need to add the component to the Toolbox.</span></span> <span data-ttu-id="ed5c0-109">パイプライン コンポーネントをツールボックスに追加する手順については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)します。</span><span class="sxs-lookup"><span data-stu-id="ed5c0-109">For instructions on adding the pipeline component to the Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5c0-110">参照</span><span class="sxs-lookup"><span data-stu-id="ed5c0-110">See Also</span></span>  
 [<span data-ttu-id="ed5c0-111">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="ed5c0-111">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)