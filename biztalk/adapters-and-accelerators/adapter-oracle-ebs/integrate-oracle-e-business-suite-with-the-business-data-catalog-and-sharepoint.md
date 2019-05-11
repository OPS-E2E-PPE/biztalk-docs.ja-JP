---
title: ビジネス データ カタログと SharePoint との Oracle E-business Suite の統合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 311f605d-78b4-41a0-b231-1a00a879f637
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2b5d3db229e7a0d2d4df5a93123576bee478b73
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530671"
---
# <a name="integrate-oracle-e-business-suite-with-the-business-data-catalog-and-sharepoint"></a><span data-ttu-id="c750a-102">ビジネス データ カタログと SharePoint との Oracle E-business Suite の統合します。</span><span class="sxs-lookup"><span data-stu-id="c750a-102">Integrate Oracle E-Business Suite with the business data catalog and SharePoint</span></span>
<span data-ttu-id="c750a-103">[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]が含まれています、 [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]、WCF サービスを特定の LOB アーティファクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="c750a-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] includes the [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], which generates a WCF service for specific LOB artifacts.</span></span> <span data-ttu-id="c750a-104">この WCF サービスは、Microsoft インターネット インフォメーション サービス (IIS) などのホスト環境でホストされます。</span><span class="sxs-lookup"><span data-stu-id="c750a-104">This WCF service is hosted in a hosting environment such as Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="c750a-105">ビジネス データ カタログ定義エディターでは、WCF サービスの Web サービス記述言語 (WSDL) を取得する WCF サービスがホストされている URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="c750a-105">The Business Data Catalog Definition Editor uses the URL where the WCF service is hosted to get the Web Services Description Language (WSDL) for the WCF service.</span></span> <span data-ttu-id="c750a-106">WSDL を使用して、ビジネス データ カタログ定義エディターは、WCF サービスで使用できるメソッドを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c750a-106">Using the WSDL, the Business Data Catalog Definition Editor extracts the methods available to the WCF service.</span></span> <span data-ttu-id="c750a-107">これらのメソッドは、エンティティとエンティティ間の関連付けを確立するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c750a-107">These methods can be used to establish entities and the association between the entities.</span></span>  
  
 <span data-ttu-id="c750a-108">ビジネス データ カタログ定義エディターでは、Microsoft Office SharePoint Server を使用するアプリケーション定義ファイル (XML ファイル) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c750a-108">The Business Data Catalog Definition Editor helps you create an application definition file (an XML file) that Microsoft Office SharePoint Server can consume.</span></span> <span data-ttu-id="c750a-109">アプリケーション定義ファイルを Microsoft Office SharePoint Server にインポートすると、エンタープライズ アプリケーションから情報を提供する Web パーツを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c750a-109">Once the application definition file is imported to Microsoft Office SharePoint Server, you can create Web Parts to present the information from enterprise applications.</span></span> <span data-ttu-id="c750a-110">詳細については、手順 3 の「Web パーツの作成」を参照してください。Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成[チュートリアル。SharePoint サイト上の Oracle E-business Suite からデータを提示](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)します。</span><span class="sxs-lookup"><span data-stu-id="c750a-110">For more information, see “Creating Web Parts” in Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite in [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
## <a name="tutorial"></a><span data-ttu-id="c750a-111">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="c750a-111">Tutorial</span></span>  
 <span data-ttu-id="c750a-112">使用する方法を示すために、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Microsoft Office SharePoint Server、による、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] SharePoint サイト上の Oracle E-business Suite からデータを表示するための手順を説明しているチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c750a-112">To demonstrate how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server, the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] includes a tutorial that provides step-by-step instructions to present data from Oracle E-Business Suite on a SharePoint site.</span></span> <span data-ttu-id="c750a-113">「[チュートリアル:SharePoint サイト上の Oracle E-business Suite からデータを提示](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)します。</span><span class="sxs-lookup"><span data-stu-id="c750a-113">See [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c750a-114">参照</span><span class="sxs-lookup"><span data-stu-id="c750a-114">See Also</span></span>  
[<span data-ttu-id="c750a-115">SharePoint で Oracle E-business Suite アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c750a-115">Use the Oracle E-Business Suite adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)