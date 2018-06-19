---
title: 静的アダプターの IStaticAdapterConfig インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f5de01-0cfc-456a-a52b-28f8f076bdfc
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de8d95ba4a5945cb43e3681055750cdad628759
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277386"
---
# <a name="static-adapter-istaticadapterconfig-interface"></a><span data-ttu-id="1fe49-102">静的アダプターの IStaticAdapterConfig インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fe49-102">Static Adapter IStaticAdapterConfig Interface</span></span>
<span data-ttu-id="1fe49-103">静的デザイン時アダプターを実装する必要があります、 **IStaticAdapterConfig**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="1fe49-103">A static design-time adapter must implement the **IStaticAdapterConfig** interface.</span></span> <span data-ttu-id="1fe49-104">このインターフェイスによって、アダプター メタデータの追加ウィザードが利用可能になり、アダプターからサービス組織や個々のサービスの説明を取得できます。</span><span class="sxs-lookup"><span data-stu-id="1fe49-104">This allows it to interact with the Add Adapter Metadata Wizard and obtain service organizations and individual service descriptions from the adapter.</span></span> <span data-ttu-id="1fe49-105">このウィザードでは、 **GetServiceOrganization**と**GetServiceDescription**アダプターと連携するメタデータ情報を取得し、BizTalk に追加する方法でプロジェクトを[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1fe49-105">The wizard calls the **GetServiceOrganization** and **GetServiceDescription** methods to pull in metadata information with which the adapter interacts and add it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1fe49-106">**GetServiceOrganization**メソッドは、アダプターの公開されたサービスの階層構造を表す XML インスタンス ドキュメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="1fe49-106">The **GetServiceOrganization** method obtains an XML instance document that represents the hierarchical organization of the adapter's exposed services.</span></span> <span data-ttu-id="1fe49-107">この構造体に表示されるサービス組織ツリーが生成されます、 **インポートするサービス**アダプター メタデータの追加ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="1fe49-107">This structure generates the service organization tree that you see on the **Select Services to Import** page in the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="1fe49-108">インポートするサービスを選択すると、ウィザードは呼び出し、 **GetServiceDescription**メソッドの追加 で選択されたサービス カテゴリに対応する Web サービス記述言語 (WSDL) ファイルの配列を取得するにはアダプター メタデータのウィザードのツリーです。</span><span class="sxs-lookup"><span data-stu-id="1fe49-108">After you select the services to import, the wizard calls the **GetServiceDescription** method to obtain an array of Web Services Description Language (WSDL) files corresponding to the service categories that were selected in the Add Adapter Metadata Wizard tree.</span></span> <span data-ttu-id="1fe49-109">アダプター メタデータの追加ウィザードの完了後、サービスを表すスキーマが XSD ファイルとして生成され、BizTalk プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1fe49-109">Schemas representing the services are generated as XSD files and added to your BizTalk project after you complete the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="1fe49-110">ファイル アダプター サンプルでは、 **GetServiceOrganization**と**GetServiceDescription**にメソッドが存在する、 **StaticAdapterManagement**クラス内で、AdapterManagement.cs クラス ファイルです。</span><span class="sxs-lookup"><span data-stu-id="1fe49-110">In the file adapter sample, the **GetServiceOrganization** and **GetServiceDescription** methods reside in the **StaticAdapterManagement** class in the AdapterManagement.cs class file.</span></span> <span data-ttu-id="1fe49-111">このウィザードでは、 **GetServiceOrganization**上に表示するツリー構造を取得するメソッド、 **インポートするサービス**ページ。</span><span class="sxs-lookup"><span data-stu-id="1fe49-111">The wizard calls the **GetServiceOrganization** method to obtain the tree structure to display on the **Select Services to Import** page.</span></span> <span data-ttu-id="1fe49-112">**GetServicesOrganization**ハードコードされた戻り値の次のコード フラグメントに示すように、AdapterManagement.CategorySchema.xml ファイルの値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fe49-112">In **GetServicesOrganization** the hard-coded return value of AdapterManagement.CategorySchema.xml file is used as shown in the following code fragment.</span></span> <span data-ttu-id="1fe49-113">アダプター開発者は、適切な XML ファイルを返すためのロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe49-113">As an adapter developer you will need to add the logic to return the appropriate XML file.</span></span>  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="1fe49-114">変更してください、 **GetServiceDescription**のメソッド、 **StaticAdapterManagement**クラスではなく、 **DynamicAdapterManagement**で最初に表示されるクラスファイル。</span><span class="sxs-lookup"><span data-stu-id="1fe49-114">Be sure to modify the **GetServiceDescription** method of the **StaticAdapterManagement** class, and not of the **DynamicAdapterManagement** class, which appears first in the file.</span></span>  
  
 <span data-ttu-id="1fe49-115">次のコードは、 **GetServiceDescription** AdapterManagement.cs ファイルのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="1fe49-115">The following code is from the **GetServiceDescription** method of the AdapterManagement.cs file.</span></span> <span data-ttu-id="1fe49-116">ここでは、返される WSDL ファイルとしてファイル service1.wsdl がハードコードされており、</span><span class="sxs-lookup"><span data-stu-id="1fe49-116">The file service1.wsdl is hard-coded as the WSDL file returned.</span></span> <span data-ttu-id="1fe49-117">WSDL ファイルとして表されているスキーマが返されます。</span><span class="sxs-lookup"><span data-stu-id="1fe49-117">It returns schemas represented as WSDL files.</span></span> <span data-ttu-id="1fe49-118">`wsdls`パラメーターは、ソースによって読み込まれた XML 内の WSDL 参照に対応する一意の WSDL 参照の配列**GetServicesOrganization**です。</span><span class="sxs-lookup"><span data-stu-id="1fe49-118">The `wsdls` parameter is an array of unique WSDL references that correspond to the WSDL references in the source XML loaded by **GetServicesOrganization**.</span></span> <span data-ttu-id="1fe49-119">返される WSDL 記述のセットは、BizTalk プロジェクトのポートの種類とメッセージの種類を生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fe49-119">The returned set of WSDL descriptions are used to generate the port types and message types for the BizTalk project.</span></span> <span data-ttu-id="1fe49-120">ツリー内に選択できるスキーマの種類が複数存在する場合は、複数の WSDL ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="1fe49-120">If you have more than one schema type available for selection in the tree, you will need more than one WSDL file.</span></span> <span data-ttu-id="1fe49-121">スキーマと WSDL の選択肢が多くある場合は、正しい WSDL ファイルを返すためデータベース検索を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fe49-121">If you have many possible schema and WSDL choices, you may want to add a database lookup to return the correct WSDL file.</span></span>  
  
```  
/// <summary>     
        /// Get the WSDL file name for the selected WSDL  
        /// </summary>  
        /// <param name="wsdls">place holder</param>  
        /// <returns>An empty string[]</returns>  
        public string[] GetServiceDescription(string[] wsdls)   
      {  
            string[] result = new string[1];  
            result[0] = GetResource("AdapterManagement.service1.wsdl");  
            return result;  
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fe49-122">参照</span><span class="sxs-lookup"><span data-stu-id="1fe49-122">See Also</span></span>  
 [<span data-ttu-id="1fe49-123">静的デザイン時アダプター構成</span><span class="sxs-lookup"><span data-stu-id="1fe49-123">Static Design-Time Adapter Configuration</span></span>](../core/static-design-time-adapter-configuration.md)