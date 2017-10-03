---
title: "Visual Studio での Siebel 操作のメタデータを取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: metadata, retrieving for Siebel operations in Visual Studio
ms.assetid: 63643942-6497-4891-ad7d-34b1df9acbc1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30935631052adf4c455e730c476104b54a6a352b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-for-siebel-operations-in-visual-studio"></a><span data-ttu-id="4db43-102">Visual Studio での Siebel 操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="4db43-102">Get Metadata for Siebel Operations in Visual Studio</span></span>
<span data-ttu-id="4db43-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] 2 つ提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4db43-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] provides two [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter.</span></span>  
  
-   <span data-ttu-id="4db43-104">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]は BizTalk Server プロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4db43-104">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is available in BizTalk Server projects.</span></span> <span data-ttu-id="4db43-105">使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を対象となる、BizTalk ソリューションでの操作のメッセージ スキーマ (Xsd) を生成します。</span><span class="sxs-lookup"><span data-stu-id="4db43-105">You use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate message schemas (XSDs) for operations that you want to target in your BizTalk solution.</span></span> <span data-ttu-id="4db43-106">BizTalk Server とソリューションの開発に関する詳細については、次を参照してください。 [Siebel アダプターを使用する開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="4db43-106">For more information about developing solutions with BizTalk Server, see [Develop BizTalk applications using the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).</span></span>
  
-   <span data-ttu-id="4db43-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]は BizTalk 以外のプログラミング プロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4db43-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] is available in non-BizTalk programming projects.</span></span> <span data-ttu-id="4db43-108">使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="4db43-108">You use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client class or a WCF service callback interface when you develop solutions using the WCF service model.</span></span> <span data-ttu-id="4db43-109">WCF サービス モデルでのソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発 Siebel アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="4db43-109">For more information about developing solutions with the WCF service model, see [Develop Siebel applications using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="4db43-110">これらの両方の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントでの開発を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="4db43-110">Both of these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
-   <span data-ttu-id="4db43-111">ソリューションで使用する操作を使用するには、参照および検索することができます、Microsoft Windows インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4db43-111">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
-   <span data-ttu-id="4db43-112">これらのターゲット操作用にアダプターによって公開されるメタデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="4db43-112">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
-   <span data-ttu-id="4db43-113">そのメタデータを変換するとして表される Web サービス記述言語 (WSDL) ドキュメント、アダプターによって (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクト表現は、ソリューションで使用できるフォームサービス モデル) し、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4db43-113">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
 <span data-ttu-id="4db43-114">このセクションで説明を使用する手順については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4db43-114">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="4db43-115">参照</span><span class="sxs-lookup"><span data-stu-id="4db43-115">See Also</span></span>  
[<span data-ttu-id="4db43-116">Siebel アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="4db43-116">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)