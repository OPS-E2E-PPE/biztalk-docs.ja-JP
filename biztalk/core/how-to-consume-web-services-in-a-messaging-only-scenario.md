---
title: メッセージングのみのシナリオのサービスの Web を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66873959-5b1b-4d9b-ad19-f083670420b8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d1e38305fd5b798a2fa8dd59fc6341dc806dfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985451"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a><span data-ttu-id="c0e9b-102">メッセージングのみのシナリオで Web サービスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="c0e9b-102">How to Consume Web Services in a Messaging Only Scenario</span></span>
<span data-ttu-id="c0e9b-103">SOAP アダプターの新しい機能強化の 1 つは、コンテンツ ベースのルーティング送信ポートを使用して、メッセージングのみのシナリオで Web サービスを呼び出す機能です。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-103">One of the new enhancements for the SOAP adapter is ability to call Web services in a messaging only scenario by using content-based routing send ports.</span></span> <span data-ttu-id="c0e9b-104">この機能により、オーケストレーションを作成せずに Web サービスを使用することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-104">This feature makes it possible to consume Web services without creating orchestrations.</span></span> <span data-ttu-id="c0e9b-105">また、メッセージがオーケストレーションで処理されないため、Web サービスの使用におけるパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-105">It also provides better performance to consume Web services because messages do not pass through orchestrations.</span></span>  
  
 <span data-ttu-id="c0e9b-106">メッセージングのみのシナリオで Web サービスを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-106">To consume Web services in a messaging only scenario, do the following:</span></span>  
  
-   <span data-ttu-id="c0e9b-107">Web サービスを呼び出すためのプロキシ ライブラリおよび XML スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-107">Create a proxy library and XML schemas for invoking Web services</span></span>  
  
-   <span data-ttu-id="c0e9b-108">Web サービスを使用するための送信ポートおよび受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-108">Configure a send port and receive location for consuming a Web service</span></span>  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a><span data-ttu-id="c0e9b-109">Web サービスを呼び出すためのプロキシ ライブラリおよび XML スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="c0e9b-109">To create a proxy library and XML schemas for invoking Web services</span></span>  
  
1. <span data-ttu-id="c0e9b-110">Web サービスの URL を決定します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-110">Determine the URL for the Web service.</span></span>  
  
2. <span data-ttu-id="c0e9b-111">開く、**空の BizTalk Server プロジェクト**で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-111">Open an **Empty BizTalk Server Project** in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution.</span></span> <span data-ttu-id="c0e9b-112">BizTalk Server プロジェクトを作成する方法の詳細については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-112">For more information about how to create a BizTalk Server project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c0e9b-113">このチュートリアルでは、BizTalk Server プロジェクトを利用して、Web サービスで使用するプロキシ ライブラリおよび XML スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-113">This walkthrough uses a BizTalk Server project to generate proxy libraries and XML schemas that the Web service uses.</span></span> <span data-ttu-id="c0e9b-114">同じ目的で、.NET Framework 4.0 の SDK の Wsdl.exe および Xsd.exe を使用することができますも。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-114">You can also use the Wsdl.exe and Xsd.exe in the .NET Framework 4.0 SDK for the same purpose.</span></span>  
  
3. <span data-ttu-id="c0e9b-115">ソリューション エクスプ ローラーで、BizTalk Server プロジェクトの名前を右クリックし をクリックし、**サービス参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-115">In Solution Explorer, right-click the BizTalk Server project name, and then click **Add Service Reference**.</span></span>  
  
4. <span data-ttu-id="c0e9b-116">**サービス参照の追加**ダイアログ ボックスで、をクリックして**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-116">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
5. <span data-ttu-id="c0e9b-117">**サービス参照設定** ダイアログ ボックスをクリックします**Web 参照の追加**で、**互換性**セクション。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-117">In the **Service Reference Settings** dialog box, Click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
6. <span data-ttu-id="c0e9b-118">**Web 参照の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-118">In the **Add Web Reference** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="c0e9b-119">**URL**フィールドを Web サービスの URL を入力し、をクリックし、**移動**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-119">In the **URL** field, type a Web service URL, and then click **Go**.</span></span>  
  
   2.  <span data-ttu-id="c0e9b-120">**Web 参照名**フィールドを名前空間の名前を入力し、をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-120">In the **Web reference name** field, type a name for the namespace, and then click **Add Reference**.</span></span>  
  
7. <span data-ttu-id="c0e9b-121">Web 参照は、下に表示されます**Web 参照**ソリューション エクスプ ローラーでノード。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-121">The Web reference will appear under **Web References** node in Solution Explorer.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="c0e9b-122">Web 参照を BizTalk プロジェクトに追加した後、 **Web 参照の追加**プロジェクト名を右クリックすると、コマンドは直接利用または**参照**または**のWeb参照**.</span><span class="sxs-lookup"><span data-stu-id="c0e9b-122">Once you have a web reference added to a BizTalk project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
8. <span data-ttu-id="c0e9b-123">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**プロパティ**をプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-123">In Solution Explorer, right-click the project name, and then click **Properties** to launch the Project Designer.</span></span>  
  
9. <span data-ttu-id="c0e9b-124">プロジェクト デザイナーで、クリックして、**署名**タブ。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-124">In the Project Designer, click the **Signing** tab.</span></span>  
  
10. <span data-ttu-id="c0e9b-125">選択**アセンブリに署名**オプションで、ドロップダウン リストをクリックして、**厳密な名前キー ファイルを選択して**、順にクリックします**参照**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-125">Select **Sign the assembly** option, click the drop-down list for the **Choose a strong name key file**, and then click **Browse**.</span></span>  
  
11. <span data-ttu-id="c0e9b-126">参照しアセンブリ キー ファイルを選択してクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-126">Browse and select the assembly key file, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="c0e9b-127">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-127">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="c0e9b-128">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-128">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a><span data-ttu-id="c0e9b-129">Web サービスを使用するための送信ポートおよび受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="c0e9b-129">To configure a send port and receive location for consuming a Web service</span></span>  
  
1.  <span data-ttu-id="c0e9b-130">BizTalk Server 管理コンソールで、送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-130">In the BizTalk Server Administration console, create a send port.</span></span> <span data-ttu-id="c0e9b-131">詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-131">For more information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="c0e9b-132">送信ポートを作成するときは、トランスポートの種類またはトランスポート プロトコルとして SOAP を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-132">When creating the send port, select SOAP as the transport type or transport protocol.</span></span>  
  
2.  <span data-ttu-id="c0e9b-133">次の設定を使用して、SOAP 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-133">Configure the SOAP send port with the following settings.</span></span> <span data-ttu-id="c0e9b-134">詳細については、次を参照してください。 [SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-134">For more information, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
    |<span data-ttu-id="c0e9b-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c0e9b-135">Use this</span></span>|<span data-ttu-id="c0e9b-136">目的</span><span class="sxs-lookup"><span data-stu-id="c0e9b-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c0e9b-137">**次の設定**</span><span class="sxs-lookup"><span data-stu-id="c0e9b-137">**The following settings**</span></span>|<span data-ttu-id="c0e9b-138">次のプロパティを指定するために、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-138">Select this option to specify the following properties.</span></span>|  
    |<span data-ttu-id="c0e9b-139">**アセンブリ名**</span><span class="sxs-lookup"><span data-stu-id="c0e9b-139">**Assembly name**</span></span>|<span data-ttu-id="c0e9b-140">前の手順で作成したアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-140">Select the assembly created in the previous procedure.</span></span> <span data-ttu-id="c0e9b-141">アセンブリの完全修飾名は、SOAP アダプターに書き込まれます**AssemblyName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-141">The fully qualified name of the assembly is written to the SOAP adapter **AssemblyName** property.</span></span>|  
    |<span data-ttu-id="c0e9b-142">**型名**</span><span class="sxs-lookup"><span data-stu-id="c0e9b-142">**Type name**</span></span>|<span data-ttu-id="c0e9b-143">呼び出す Web メソッドを含むクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-143">Specify the name of the class that contains the Web method to be invoked.</span></span> <span data-ttu-id="c0e9b-144">型名は、SOAP アダプターに書き込まれます**TypeName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-144">The type name is written to the SOAP adapter **TypeName** property.</span></span>|  
    |<span data-ttu-id="c0e9b-145">**メソッド名**</span><span class="sxs-lookup"><span data-stu-id="c0e9b-145">**Method name**</span></span>|<span data-ttu-id="c0e9b-146">リスト ボックスでメソッドの 1 つを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-146">Specify one of the methods in the list box.</span></span> <span data-ttu-id="c0e9b-147">Web メソッドが、Soap アダプターに書き込まれる**MethodName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-147">The Web method is written to the Soap Adapter **MethodName** property.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="c0e9b-148">コンテンツ ベースのルーティング (CBR) を使用する場合は、送信ポートのフィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-148">If you want to use Content-Based Routing (CBR), configure the filter of the send port.</span></span> <span data-ttu-id="c0e9b-149">詳細については、次を参照してください。[送信ポートのフィルターを構成する方法](../core/how-to-configure-filters-for-a-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-149">For more information, see [How to Configure Filters for a Send Port](../core/how-to-configure-filters-for-a-send-port.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0e9b-150">呼び出された Web サービスからの応答メッセージに対するサブスクライバーがない場合は、ルーティング障害のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c0e9b-150">If there is no subscriber to the response messages from the invoked Web services, a routing failure error will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e9b-151">参照</span><span class="sxs-lookup"><span data-stu-id="c0e9b-151">See Also</span></span>  
 [<span data-ttu-id="c0e9b-152">Web サービスの利用</span><span class="sxs-lookup"><span data-stu-id="c0e9b-152">Consuming Web Services</span></span>](../core/consuming-web-services.md)