---
title: Visual Studio での Oracle E-business Suite 操作のメタデータを取得 |Microsoft Docs
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
ms.openlocfilehash: 77977351036e86e558491a2c2927a29878ae550b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375527"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a><span data-ttu-id="7903c-102">Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="7903c-102">Get metadata for Oracle E-Business Suite operations in Visual Studio</span></span>
<span data-ttu-id="7903c-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 3 つ提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7903c-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter:</span></span>  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
- [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
  <span data-ttu-id="7903c-104">アダプター クライアントは、これらのコンポーネントを使用して Oracle E-business Suite に接続しを実行する操作のメタデータを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7903c-104">Adapter clients must use these components to connect to Oracle E-Business Suite, and then generate metadata for the operations they want to perform.</span></span> <span data-ttu-id="7903c-105">これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントで開発を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="7903c-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="7903c-106">ソリューションで使用する操作を参照および検索は、Microsoft Windows インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7903c-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="7903c-107">これらの操作のターゲットのアダプターによって公開されているメタデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="7903c-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="7903c-108">そのメタデータを変換するには、これによって表されます Web サービス記述言語 (WSDL) ドキュメントとしてアダプターは、ソリューション (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクトの表現で使用できる形式にサービス モデル)、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="7903c-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="7903c-109">このセクションでは使用する方法について説明、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7903c-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7903c-110">Oracle E-business Suite では、特定のバージョンのアダプターを使用してソリューションを作成した別のバージョンの Oracle E-business Suite でソリューションを展開しようとする場合は、展開する前に、ソリューションをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7903c-110">If you have created a solution using the adapter on a particular version of Oracle E-Business Suite, and now want to deploy the solution on a different version of Oracle E-Business Suite then you should test the solution before deploying it.</span></span> <span data-ttu-id="7903c-111">基になる成果物のメタデータが異なる可能性があるために、別のバージョンの Oracle E-business Suite のソリューションをデプロイするときに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7903c-111">You might face issues while deploying the solution on a different version of Oracle E-Business Suite because the metadata of the underlying artifact might be different.</span></span> <span data-ttu-id="7903c-112">この問題を解決するには、Oracle E-business Suite のソリューションを配置するのと同じバージョンのアダプターを使用してメタデータを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7903c-112">To resolve this issue, you should regenerate the metadata using the adapter on the same version of Oracle E-Business Suite on which you intend to deploy the solution.</span></span>  
  
