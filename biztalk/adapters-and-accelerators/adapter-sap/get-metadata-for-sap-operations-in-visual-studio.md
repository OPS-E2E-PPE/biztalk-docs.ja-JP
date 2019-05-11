---
title: Visual Studio で SAP 操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving for SAP operations in Visual Studio
ms.assetid: 1be5934a-a5d4-4734-8bea-fb8274f59c71
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 338130847a220d16cd4b5e42c1f93ff2bc3b2334
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373408"
---
# <a name="get-metadata-for-sap-operations-in-visual-studio"></a><span data-ttu-id="64958-102">Visual Studio で SAP 操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="64958-102">Get Metadata for SAP Operations in Visual Studio</span></span>
<span data-ttu-id="64958-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、2[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント:、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="64958-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] provides two [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter—the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="64958-104">アダプター クライアントは、これらのコンポーネントを使用して、SAP システムに接続し、呼び出し先 SAP アイテムのメタデータを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64958-104">Adapter clients must use these components to connect to an SAP system and then generate metadata for the SAP artifacts they want to invoke.</span></span>  
  
 <span data-ttu-id="64958-105">これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントで開発を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="64958-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="64958-106">ソリューションで使用する操作を参照および検索は、Microsoft Windows インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="64958-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="64958-107">これらの操作のターゲットのアダプターによって公開されているメタデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="64958-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="64958-108">そのメタデータを変換するには、これによって表されます Web サービス記述言語 (WSDL) ドキュメントとしてアダプターは、ソリューション (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクトの表現で使用できる形式にサービス モデル)、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="64958-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="64958-109">このセクションでは使用する方法について説明、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="64958-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="64958-110">参照</span><span class="sxs-lookup"><span data-stu-id="64958-110">See Also</span></span>  
[<span data-ttu-id="64958-111">SAP アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="64958-111">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)