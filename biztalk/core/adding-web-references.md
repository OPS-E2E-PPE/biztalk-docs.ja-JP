---
title: Web 参照の追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- orchestrations, BPEL
- Web services, ports
- orchestrations, exporting
- Web services, projects
- Web services, references
- projects, Web services
ms.assetid: 7e40f215-f11a-4151-bcc6-e107bf36b6f6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cbf8cd4c21009190fc459312467656410dc663a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964768"
---
# <a name="adding-web-references"></a><span data-ttu-id="56289-102">Web 参照の追加</span><span class="sxs-lookup"><span data-stu-id="56289-102">Adding Web References</span></span>
<span data-ttu-id="56289-103">Web ポートを追加するには、BizTalk プロジェクトに Web 参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56289-103">Before you can add a Web port, you need to add a Web reference to your BizTalk project.</span></span> <span data-ttu-id="56289-104">Web 参照は、プロジェクトで使用可能な Web サービスの説明です。</span><span class="sxs-lookup"><span data-stu-id="56289-104">A Web reference is a description of a Web service that is available to your project.</span></span> <span data-ttu-id="56289-105">プロジェクトに Web 参照を追加すると、BizTalk プロジェクト作成オーケストレーション Web ポートの種類、Web メッセージの種類、Reference.map (マップ ファイル)、Reference.odx (オーケストレーション ファイル)、 \< *WebService*\>です。disco (探索ファイル)、および\< *WebService*\>.wsdl (Web サービス記述言語ファイル) をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="56289-105">When you add a Web reference to your project, BizTalk project creates an orchestration Web port type, Web message types, Reference.map (map file), Reference.odx (orchestration file), \<*WebService*\>.disco (discovery file), and \<*WebService*\>.wsdl (Web Service Description Language file) to your project.</span></span> <span data-ttu-id="56289-106">Web サービス記述言語 (WSDL) ファイルにスキーマ Web メッセージの種類が含まれる場合、プロジェクトに Reference.xsd が追加されます。</span><span class="sxs-lookup"><span data-stu-id="56289-106">If your Web Service Description Language (WSDL) file contains schema Web message types, BizTalk project adds Reference.xsd to your project.</span></span>  
  
 <span data-ttu-id="56289-107">Web 参照には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="56289-107">A Web reference includes:</span></span>  
  
-   <span data-ttu-id="56289-108">Web サービスの Universal Resource Locator (URL)。</span><span class="sxs-lookup"><span data-stu-id="56289-108">A Universal Resource Locator (URL) for the Web service.</span></span>  
  
-   <span data-ttu-id="56289-109">使用可能なメソッド、ポート、メッセージの種類などのサービスに関する情報を提供する WSDL ファイル。</span><span class="sxs-lookup"><span data-stu-id="56289-109">A WSDL file that offers information about the service such as available methods, ports, and message types.</span></span>  
  
-   <span data-ttu-id="56289-110">参照マップ (Reference.map)。</span><span class="sxs-lookup"><span data-stu-id="56289-110">A reference map (Reference.map).</span></span>  
  
 <span data-ttu-id="56289-111">Web 参照を追加する場合、その Web サービスのすべての Web メソッドには、BizTalk Server との互換性が必要です。</span><span class="sxs-lookup"><span data-stu-id="56289-111">When you add a Web reference, all the Web methods for that Web service must be compatible with BizTalk Server.</span></span> <span data-ttu-id="56289-112">Web サービス内の特定の Web メソッドの条件付き属性を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="56289-112">You cannot specify conditional attributes for specific Web methods in a Web service.</span></span>  
  
 <span data-ttu-id="56289-113">使用して、プロジェクトに Web 参照を追加する、 **Web 参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="56289-113">You add a Web reference to your project by using the **Add Web Reference** dialog box.</span></span> <span data-ttu-id="56289-114">Web 参照の追加の詳細については、次を参照してください。 [Visual Studio を使って](../core/using-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="56289-114">For more information about adding Web references, see [Using Visual Studio](../core/using-visual-studio.md).</span></span>  
  
 <span data-ttu-id="56289-115">Business Process Execution Language (BPEL) エクスポート プロセスを使用してオーケストレーションをエクスポートする場合、既存の BizTalk プロジェクトから Web 参照を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="56289-115">If you are planning to export your orchestration using the Business Process Execution Language (BPEL) export process, you cannot reference a Web reference from an existing BizTalk project.</span></span> <span data-ttu-id="56289-116">既存の BizTalk プロジェクトから Web 参照を参照すると、BPEL エクスポート プロセスでは、2 つ目の WSDL ファイルが自動生成され、バインド情報が失われます。</span><span class="sxs-lookup"><span data-stu-id="56289-116">When you reference a Web reference from an existing BizTalk project, the BPEL export process will auto-generate a second WSDL file and you will lose your binding information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56289-117">参照</span><span class="sxs-lookup"><span data-stu-id="56289-117">See Also</span></span>  
 <span data-ttu-id="56289-118">[Web ポートの作成](../core/creating-web-ports.md) </span><span class="sxs-lookup"><span data-stu-id="56289-118">[Creating Web Ports](../core/creating-web-ports.md) </span></span>  
 [<span data-ttu-id="56289-119">Web サービスの利用</span><span class="sxs-lookup"><span data-stu-id="56289-119">Consuming Web Services</span></span>](../core/consuming-web-services.md)