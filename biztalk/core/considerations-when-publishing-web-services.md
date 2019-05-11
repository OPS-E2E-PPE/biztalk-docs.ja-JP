---
title: Web サービスの発行時の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, planning
- Web services, schemas
- schemas, Web services
ms.assetid: 3ace0260-a1cb-4e59-a820-36ee7d5cceda
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72d45e269d091c2c39b44e260c10a96a3895706e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390336"
---
# <a name="considerations-when-publishing-web-services"></a><span data-ttu-id="92690-102">Web サービスを公開する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="92690-102">Considerations When Publishing Web Services</span></span>
<span data-ttu-id="92690-103">このトピックでは、情報を提供します。 Web サービスを発行する前に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92690-103">This topic provides information that you should consider before you publish your Web services.</span></span>  
  
## <a name="publishing-schemas-and-the-include-element"></a><span data-ttu-id="92690-104">発行のスキーマおよび include 要素</span><span class="sxs-lookup"><span data-stu-id="92690-104">Publishing schemas and the include element</span></span>  
 <span data-ttu-id="92690-105">いくつかのシナリオがある場所が含まれたスキーマ、**含める**要素は、Web サービスとして発行できません。</span><span class="sxs-lookup"><span data-stu-id="92690-105">There are a few scenarios where schemas that contain the **include** element cannot be published as a Web service.</span></span> <span data-ttu-id="92690-106">BizTalk Web サービス公開ウィザードを完了すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="92690-106">An error will occur when you complete the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="92690-107">これらの制限事項を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="92690-107">These restrictions include the following:</span></span>  
  
- <span data-ttu-id="92690-108">循環が含まれています (インクルードされるスキーマが、**含める**をインクルードするスキーマの要素)</span><span class="sxs-lookup"><span data-stu-id="92690-108">Circular includes (the included schema has an **include** element to the including schema)</span></span>  
  
- <span data-ttu-id="92690-109">未解決**schemaLocation**属性には、エラーが発生</span><span class="sxs-lookup"><span data-stu-id="92690-109">An unresolved **schemaLocation** attribute will cause an error</span></span>  
  
  <span data-ttu-id="92690-110">制限の詳細については要素が含まれてに「含める要素のバインディング サポート」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=62312](http://go.microsoft.com/fwlink/?LinkId=62312)します。</span><span class="sxs-lookup"><span data-stu-id="92690-110">For more information about the limitation of include element, see "Include Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62312](http://go.microsoft.com/fwlink/?LinkId=62312).</span></span>  
  
## <a name="publishing-schemas-and-the-import-element"></a><span data-ttu-id="92690-111">発行のスキーマおよび import 要素</span><span class="sxs-lookup"><span data-stu-id="92690-111">Publishing schemas and the import element</span></span>  
 <span data-ttu-id="92690-112">BizTalk Web サービス公開ウィザードは、.NET Framework に付属する XSD.exe と同じ制限です。</span><span class="sxs-lookup"><span data-stu-id="92690-112">BizTalk Web Services Publishing Wizard has the same limitation as XSD.exe included in .NET Framework.</span></span> <span data-ttu-id="92690-113">詳細についてで「Import 要素のバインディング サポート」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62311](http://go.microsoft.com/fwlink/?LinkId=62311)します。</span><span class="sxs-lookup"><span data-stu-id="92690-113">For more information, see "Import Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62311](http://go.microsoft.com/fwlink/?LinkId=62311).</span></span>  
  
## <a name="publishing-schemas-and-the-redefine-element"></a><span data-ttu-id="92690-114">発行のスキーマおよび redefine 要素</span><span class="sxs-lookup"><span data-stu-id="92690-114">Publishing schemas and the redefine element</span></span>  
 <span data-ttu-id="92690-115">BizTalk Web サービス公開ウィザードは、.NET Framework に付属する XSD.exe と同じ制限です。</span><span class="sxs-lookup"><span data-stu-id="92690-115">BizTalk Web Services Publishing Wizard has the same limitation as XSD.exe included in .NET Framework.</span></span> <span data-ttu-id="92690-116">詳細についてで「Redefine 要素バインディング サポート」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62313](http://go.microsoft.com/fwlink/?LinkId=62313)します。</span><span class="sxs-lookup"><span data-stu-id="92690-116">For more information, see "Redefine Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62313](http://go.microsoft.com/fwlink/?LinkId=62313).</span></span>  
  
## <a name="publishing-schemas-that-specify-values-for-minoccurs-or-maxoccurs-attributes"></a><span data-ttu-id="92690-117">MinOccurs または maxOccurs 属性の値を指定するスキーマの公開</span><span class="sxs-lookup"><span data-stu-id="92690-117">Publishing schemas that specify values for minOccurs or maxOccurs attributes</span></span>  
 <span data-ttu-id="92690-118">含むスキーマを発行する場合**minOccurs**または**maxOccurs**属性値を指定して、これらの値が公開された Web サービスによって公開されるスキーマで異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="92690-118">If you publish a schema that contains **minOccurs** or **maxOccurs** attributes with specific values, these values may be different in schema exposed by the published Web service.</span></span> <span data-ttu-id="92690-119">一般則として、minOccurs のすべての属性が 0 に変換されます (minOccurs = 0) および maxOccurs 属性が 1 に変換または unbounded (maxOccurs = 1 または maxOccurs = unbounded)。</span><span class="sxs-lookup"><span data-stu-id="92690-119">As a general rule of thumb, all minOccurs attributes are converted to 0 (minOccurs=0) and maxOccurs attributes are converted to either 1 or unbounded (maxOccurs=1 or maxOccurs=unbounded).</span></span>  
  
## <a name="publishing-envelope-schemas"></a><span data-ttu-id="92690-120">エンベロープ スキーマの公開</span><span class="sxs-lookup"><span data-stu-id="92690-120">Publishing envelope schemas</span></span>  
 <span data-ttu-id="92690-121">Web サービスとして公開するエンベロープ スキーマがあれば、手動で生成された Web プロジェクトを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92690-121">If you have an envelop schema that you are publishing as a Web service, you need to manually modify the generated Web project.</span></span>  
  
#### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a><span data-ttu-id="92690-122">エンベロープ スキーマの生成された Web プロジェクトを変更するには</span><span class="sxs-lookup"><span data-stu-id="92690-122">To modify the generated Web project for envelope schemas</span></span>  
  
1.  <span data-ttu-id="92690-123">開いている、<`myWebService`>. ある asmx.cs ファイル。</span><span class="sxs-lookup"><span data-stu-id="92690-123">Open the <`myWebService`>.asmx.cs file.</span></span>  
  
2.  <span data-ttu-id="92690-124">ファイルを編集し、変更`bodyTypeAssemblyQualifiedName = <dll.name.version.>`に`bodyTypeAssemblyQualifiedName = null`します。</span><span class="sxs-lookup"><span data-stu-id="92690-124">Edit the file and change `bodyTypeAssemblyQualifiedName = <dll.name.version.>` to `bodyTypeAssemblyQualifiedName = null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92690-125">以前の .dll ファイルが引き続き ASPNET ワーカー プロセスの場合は、インターネット インフォメーション サービス (IIS) をリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92690-125">You may need to reset Internet Information Services (IIS) if the previous .dll file is still in the ASPNET worker process.</span></span>  
  
## <a name="web-service-and-web-method-attributes"></a><span data-ttu-id="92690-126">Web サービスおよび Web メソッド属性</span><span class="sxs-lookup"><span data-stu-id="92690-126">Web service and Web method attributes</span></span>  
 <span data-ttu-id="92690-127">BizTalk Web サービス公開ウィザードでは、Web サービスまたは ASP.NET で使用する Web メソッド属性をカスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="92690-127">The BizTalk Web Services Publishing Wizard does not allow you to customize the Web service or Web method attributes you use in ASP.NET.</span></span> <span data-ttu-id="92690-128">いくつかの属性は、ウィザードによって提供される情報に基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="92690-128">Some attributes are automatically set based upon information that the wizard provides.</span></span> <span data-ttu-id="92690-129">ウィザードでは、その他の属性は使用しません。</span><span class="sxs-lookup"><span data-stu-id="92690-129">The wizard does not use the other attributes.</span></span>  
  
 <span data-ttu-id="92690-130">既存の属性を変更または BizTalk Web サービス公開ウィザードが生成する Web サービスに新しい属性を追加するには、正しく機能する Web サービスがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="92690-130">Modifying the existing attributes or adding new attributes to Web services that the BizTalk Web Services Publishing Wizard generates may cause the Web service to function incorrectly.</span></span>  
  
 <span data-ttu-id="92690-131">Web サービスと Web メソッド属性の詳細については、次を参照してください。、 **WebServiceAttribute**と**WebMethodAttribute** 、.NET Framework SDK ドキュメント内のクラス。</span><span class="sxs-lookup"><span data-stu-id="92690-131">For more information about Web services and Web method attributes, see the **WebServiceAttribute** and **WebMethodAttribute** classes in the .NET Framework SDK documentation.</span></span>  
  
## <a name="web-method-required"></a><span data-ttu-id="92690-132">必要な web メソッド</span><span class="sxs-lookup"><span data-stu-id="92690-132">Web method required</span></span>  
 <span data-ttu-id="92690-133">Web サービスを少なくとも 1 つの Web メソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="92690-133">A Web service must have at least one Web method.</span></span> <span data-ttu-id="92690-134">少なくとも 1 つの Web メソッドを使用しないでポートの種類を作成、操作する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92690-134">Without at least one Web method, port types will not have their operations created.</span></span> <span data-ttu-id="92690-135">XLANG/秒は、操作がないポートの種類をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="92690-135">XLANG/s does not support port types that do not have operations.</span></span>  
  
## <a name="dbcs-character-support"></a><span data-ttu-id="92690-136">DBCS 文字のサポート</span><span class="sxs-lookup"><span data-stu-id="92690-136">DBCS character support</span></span>  
 <span data-ttu-id="92690-137">Web サービスは、中国語/日本語/韓国語 (CJK) 統合漢字拡張 A 文字をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="92690-137">Web services do not support Chinese/Japanese/Korean (CJK) Unified Ideograph Extension A characters.</span></span>  
  
## <a name="republishing-web-services-using-the-biztalk-web-services-publishing-wizard"></a><span data-ttu-id="92690-138">BizTalk Web サービス公開ウィザードを使用して Web サービスを再パブリッシュ</span><span class="sxs-lookup"><span data-stu-id="92690-138">Republishing Web services using the BizTalk Web Services Publishing Wizard</span></span>  
 <span data-ttu-id="92690-139">BizTalk Web サービス公開ウィザードを使用して、公開済み Web サービスを再発行することができます。</span><span class="sxs-lookup"><span data-stu-id="92690-139">You can use the BizTalk Web Services Publishing Wizard to republish a published Web service.</span></span> <span data-ttu-id="92690-140">**Web**<strong>サービス</strong>**プロジェクト**ページで、選択できる、**上書き**<strong>Web</strong> **サービス**オプション。</span><span class="sxs-lookup"><span data-stu-id="92690-140">On the **Web**<strong>Service</strong>**Project** page, you can select the **Overwrite**<strong>Web</strong>**Service** option.</span></span>  
  
 <span data-ttu-id="92690-141">ウィザードでは以前に使用されるストアの設定ではなく、します。</span><span class="sxs-lookup"><span data-stu-id="92690-141">The wizard does not store previously used settings.</span></span> <span data-ttu-id="92690-142">ウィザードを再実行するときに、設定の変更を行った場合、使用する (呼び出す) Web クライアント公開された Web サービスがあります。</span><span class="sxs-lookup"><span data-stu-id="92690-142">If you make changes in the settings when you rerun the wizard, any Web clients that consume (call) the published Web service may fail.</span></span> <span data-ttu-id="92690-143">再公開 Web サービス (呼び出し) を使用するすべてのクライアントの Web 参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92690-143">You should update the Web references of any clients that consume (call) a republished Web service.</span></span>  
  
## <a name="clients-of-published-web-services-may-not-receive-server-script-timeout-errors"></a><span data-ttu-id="92690-144">公開済み Web サービスのクライアントは、サーバー スクリプト タイムアウト エラーを受信しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92690-144">Clients of published Web services may not receive Server script timeout errors</span></span>  
 <span data-ttu-id="92690-145">Web サービスで Web サービス公開ウィザードで生成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定のスクリプトのタイムアウト値で構成が**110**秒。</span><span class="sxs-lookup"><span data-stu-id="92690-145">Web services generated with the Web Services Publishing Wizard in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are configured by default with a script timeout value of **110** seconds.</span></span> <span data-ttu-id="92690-146">これは、.NET Framework の既定値です。</span><span class="sxs-lookup"><span data-stu-id="92690-146">This is the default value for the .NET Framework.</span></span> <span data-ttu-id="92690-147">**HttpServerUtility.ScriptTimeout**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92690-147">**HttpServerUtility.ScriptTimeout** property.</span></span> <span data-ttu-id="92690-148">.NET Framework を使用する web クライアントが要求のタイムアウト値では既定で構成されている**100**秒。</span><span class="sxs-lookup"><span data-stu-id="92690-148">Web clients that use .NET Framework are configured by default with a request timeout value of **100** seconds.</span></span> <span data-ttu-id="92690-149">これは、.NET Framework の既定値**HttpWebRequest.Timeout**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92690-149">This is the default value for the .NET Framework **HttpWebRequest.Timeout** property.</span></span>  
  
 <span data-ttu-id="92690-150">.NET framework を使用する Web クライアントが使用して生成された Web サービスを呼び出しているかどうか、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービスの公開ウィザードでは、既定ではまずクライアントの要求タイムアウトが発生するために、クライアントがサーバー スクリプト タイムアウト エラーを受信できないことができます。</span><span class="sxs-lookup"><span data-stu-id="92690-150">If Web clients that use .NET framework are calling a Web Service generated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services Publishing Wizard, it is possible that the client cannot receive server script timeout errors because the client request timeout occurs first by default.</span></span> <span data-ttu-id="92690-151">この問題を解決するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="92690-151">To resolve this problem you can do one of the following:</span></span>  
  
-   <span data-ttu-id="92690-152">値を増やすことで、サーバー スクリプト タイムアウトよりも大きい値にクライアント要求タイムアウトの値を増やし、 **HttpWebRequest.Timeout**クライアントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="92690-152">Increase the client request timeout to a value greater than the server script timeout by increasing the value for the **HttpWebRequest.Timeout** property on the client.</span></span>  
  
-   <span data-ttu-id="92690-153">値を減らすことで、クライアント要求のタイムアウトよりも小さい値に、サーバー スクリプト タイムアウトを減らす、 **HttpServerUtility.ScriptTimeout**サーバーのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="92690-153">Reduce the server script timeout to a value less than the client request timeout by reducing the value for the **HttpServerUtility.ScriptTimeout** property on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92690-154">参照</span><span class="sxs-lookup"><span data-stu-id="92690-154">See Also</span></span>  
 [<span data-ttu-id="92690-155">Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="92690-155">Publishing Web Services</span></span>](../core/publishing-web-services.md)