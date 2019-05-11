---
title: SAP をビジネス データと統合する SAP アダプターを構成するカタログと SharePoint |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ec105c9-0ced-4a45-bc0d-eb72c1ef5d9d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f422b44d8d6d5c060ad8e100f987cc6715bfdff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373774"
---
# <a name="configure-the-sap-adapter-to-integrate-sap-with-the-business-data-catalog-and-sharepoint"></a><span data-ttu-id="01055-102">SAP をビジネス データと統合する SAP アダプターを構成するカタログと SharePoint</span><span class="sxs-lookup"><span data-stu-id="01055-102">Configure the SAP Adapter to Integrate SAP with the Business Data Catalog and SharePoint</span></span>
<span data-ttu-id="01055-103">[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]が含まれています、 [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]、WCF サービスを特定の LOB アーティファクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="01055-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] includes the [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], which generates a WCF service for specific LOB artifacts.</span></span> <span data-ttu-id="01055-104">この WCF サービスは、Microsoft インターネット インフォメーション サービス (IIS) などのホスト環境でホストされます。</span><span class="sxs-lookup"><span data-stu-id="01055-104">This WCF service is hosted in a hosting environment such as Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="01055-105">ビジネス データ カタログ定義エディターでは、WCF サービスの Web サービス記述言語 (WSDL) を取得する WCF サービスがホストされている URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="01055-105">The Business Data Catalog Definition Editor uses the URL where the WCF service is hosted to get the Web Services Description Language (WSDL) for the WCF service.</span></span> <span data-ttu-id="01055-106">WSDL を使用して、ビジネス データ カタログ定義エディターは、WCF サービスで使用できるメソッドを抽出します。</span><span class="sxs-lookup"><span data-stu-id="01055-106">Using the WSDL, the Business Data Catalog Definition Editor extracts the methods available to the WCF service.</span></span> <span data-ttu-id="01055-107">これらのメソッドは、エンティティとエンティティ間の関連付けを確立するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="01055-107">These methods can be used to establish entities and the association between the entities.</span></span>  
  
 <span data-ttu-id="01055-108">ビジネス データ カタログ定義エディターでは、Microsoft Office SharePoint Server を使用するアプリケーション定義ファイル (XML ファイル) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="01055-108">The Business Data Catalog Definition Editor helps you create an application definition file (an XML file) that Microsoft Office SharePoint Server can consume.</span></span> <span data-ttu-id="01055-109">アプリケーション定義ファイルを Microsoft Office SharePoint Server にインポートすると、エンタープライズ アプリケーションから情報を提供する Web パーツを作成できます。</span><span class="sxs-lookup"><span data-stu-id="01055-109">Once the application definition file is imported to Microsoft Office SharePoint Server, you can create Web Parts to present the information from enterprise applications.</span></span> <span data-ttu-id="01055-110">詳細については、「Web パーツを作成する」を参照してください[手順 3。SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)で[チュートリアル 1。SharePoint サイト上の SAP システムからのデータ表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)します。</span><span class="sxs-lookup"><span data-stu-id="01055-110">For more information, see “Creating Web Parts” in [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
## <a name="tutorial"></a><span data-ttu-id="01055-111">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="01055-111">Tutorial</span></span>  
 <span data-ttu-id="01055-112">使用する方法を示すために、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Microsoft Office SharePoint Server、による、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] SharePoint サイト上の SAP システムからデータを表示するための手順を説明しているチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01055-112">To demonstrate how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft Office SharePoint Server, the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] includes a tutorial that provides step-by-step instructions to present data from an SAP system on a SharePoint site.</span></span> <span data-ttu-id="01055-113">参照してください[チュートリアル 1。SharePoint サイト上の SAP システムからのデータ表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)します。</span><span class="sxs-lookup"><span data-stu-id="01055-113">See [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01055-114">参照</span><span class="sxs-lookup"><span data-stu-id="01055-114">See Also</span></span>  
[<span data-ttu-id="01055-115">SharePoint で SAP アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="01055-115">Use the SAP Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)