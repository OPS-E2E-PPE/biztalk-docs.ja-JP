---
title: Visual Studio での Oracle E-business Suite 操作のメタデータを取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d7f731-cd0f-4970-a3cd-072f09312989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97ef4cc308979718f306958d0da1bb1eceaebaf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215042"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a><span data-ttu-id="ef642-102">Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="ef642-102">Get metadata for Oracle E-Business Suite operations in Visual Studio</span></span>
<span data-ttu-id="ef642-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 3 つの提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="ef642-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter:</span></span>  
  
-   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
-   [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
 <span data-ttu-id="ef642-104">アダプター クライアントは、これらのコンポーネントを使用して Oracle E-business Suite に接続しを実行する操作のメタデータを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef642-104">Adapter clients must use these components to connect to Oracle E-Business Suite, and then generate metadata for the operations they want to perform.</span></span> <span data-ttu-id="ef642-105">これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントでの開発を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="ef642-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
-   <span data-ttu-id="ef642-106">ソリューションで使用する操作を使用するには、参照および検索することができます、Microsoft Windows インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef642-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
-   <span data-ttu-id="ef642-107">これらのターゲット操作用にアダプターによって公開されるメタデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="ef642-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
-   <span data-ttu-id="ef642-108">そのメタデータを変換するとして表される Web サービス記述言語 (WSDL) ドキュメント、アダプターによって (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクト表現は、ソリューションで使用できるフォームサービス モデル) し、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="ef642-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
 <span data-ttu-id="ef642-109">このセクションで説明を使用する手順については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ef642-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef642-110">Oracle E-business Suite の特定のバージョンのアダプターを使用してソリューションを作成した別のバージョンの Oracle E-business Suite でソリューションを展開していて、展開する前に、ソリューションをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef642-110">If you have created a solution using the adapter on a particular version of Oracle E-Business Suite, and now want to deploy the solution on a different version of Oracle E-Business Suite then you should test the solution before deploying it.</span></span> <span data-ttu-id="ef642-111">基になる成果物のメタデータが異なる可能性があるため、異なるバージョンの Oracle E-business Suite でソリューションの展開中に問題に直面可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef642-111">You might face issues while deploying the solution on a different version of Oracle E-Business Suite because the metadata of the underlying artifact might be different.</span></span> <span data-ttu-id="ef642-112">この問題を解決するには、同じバージョンのソリューションを配置する Oracle E-business Suite でアダプターを使用してメタデータを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef642-112">To resolve this issue, you should regenerate the metadata using the adapter on the same version of Oracle E-Business Suite on which you intend to deploy the solution.</span></span>  
  
