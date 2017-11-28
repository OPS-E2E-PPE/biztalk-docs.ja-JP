---
title: "Internet Explorer を使用して、公開された Web サービスをテストする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, receive locations
- Web services, Internet Explorer
- testing, Web services
- receive locations, modifying
- Web services, modifying
- modifying, Web.config file
- Web.config file
- Web services, Web.config file
- HTTP-GET
- Web services, testing
- Web services, HTTP-GET
- modifying, Web services
ms.assetid: 4dc2171d-4abe-43db-b4bc-e484048c6430
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 687078a14d8cb2163c9795c68f65171e7b82467c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-internet-explorer-to-test-a-published-web-service"></a><span data-ttu-id="93b85-102">Internet Explorer を使用して、公開された Web サービスをテストする方法</span><span class="sxs-lookup"><span data-stu-id="93b85-102">How to Use Internet Explorer to Test a Published Web Service</span></span>
<span data-ttu-id="93b85-103">Web クライアント アプリケーションを記述せずに、公開済み Web サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="93b85-103">You can test your published Web service without writing a Web client application.</span></span> <span data-ttu-id="93b85-104">Internet Explorer などの Web ブラウザを使用して、公開済み Web サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="93b85-104">You can use a Web browser, such as Internet Explorer, to test your published Web service.</span></span> <span data-ttu-id="93b85-105">Web ブラウザを使用して公開済み Web サービスにアクセスできますが、テストできるのは、単純な型パラメータを使用する Web メソッドを持つ Web サービスのみです。</span><span class="sxs-lookup"><span data-stu-id="93b85-105">Although you can access any published Web service using a Web browser, you can only test Web services with Web methods that contain simple type parameters.</span></span> <span data-ttu-id="93b85-106">Web ブラウザーで、Web メソッドをテストするには、受信ポートで使用される要求と応答メッセージのメッセージ部分できるだけ単純型など**System.String**または**System.Int32**です。</span><span class="sxs-lookup"><span data-stu-id="93b85-106">To test your Web method in a Web browser, your message parts for the request and response messages that are used in the receive port can only be a simple type, such as **System.String** or **System.Int32**.</span></span> <span data-ttu-id="93b85-107">メッセージ部分がメッセージ型としてスキーマを使用している場合、ブラウザで Web メソッドをテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="93b85-107">If any message part uses a schema as a message type, you cannot test the Web method with a browser.</span></span>  
  
 <span data-ttu-id="93b85-108">HTTP-GET または HTTP-POST を使用して公開済み Web サービスをテストするには、SOAP アダプタの BizTalk 受信場所を構成し、公開済み Web サービスの Web.config ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93b85-108">If you want to test your published Web services using HTTP-GET or HTTP-POST, you must configure your BizTalk receive location for the SOAP adapter and modify the Web.config file for your published Web service.</span></span>  
  
 <span data-ttu-id="93b85-109">**変更、受信場所**</span><span class="sxs-lookup"><span data-stu-id="93b85-109">**Modifying the Receive Locations**</span></span>  
  
 <span data-ttu-id="93b85-110">SOAP アダプタは、受信場所を構成するとき、通常、次の仮想ディレクトリと Web サービスの .asmx ファイルの名前を指定することで、受信場所の URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="93b85-110">When the SOAP adapter configures receive locations, the SOAP adapter normally sets the URI of the receive location by giving the virtual directory and the Web service .asmx file name:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 <span data-ttu-id="93b85-111">これにより、SOAP アダプタは HTTP-SOAP プロトコルを使用して Web サービス要求を受信できます。</span><span class="sxs-lookup"><span data-stu-id="93b85-111">This allows the SOAP adapter to receive Web service requests using the HTTP-SOAP protocol.</span></span> <span data-ttu-id="93b85-112">HTTP-GET プロトコルまたは HTTP-POST プロトコルを使用するように受信場所を構成するには、次のようにメソッド名を URI に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93b85-112">To configure the receive location to use the HTTP-GET or HTTP-POST protocol, you must append the method name to the URI:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 <span data-ttu-id="93b85-113">メソッド名は、オーケストレーションのポート操作名と同じです。</span><span class="sxs-lookup"><span data-stu-id="93b85-113">The method name is the same as the port operation name in the orchestration.</span></span>  
  
 <span data-ttu-id="93b85-114">**Web.config ファイルを変更します。**</span><span class="sxs-lookup"><span data-stu-id="93b85-114">**Modifying the Web.config file**</span></span>  
  
 <span data-ttu-id="93b85-115">既定では、Web サービスは HTTP-SOAP プロトコルを使用するようウィザードにより構成されます。</span><span class="sxs-lookup"><span data-stu-id="93b85-115">By default, the wizard configures the Web services to use the HTTP-SOAP protocol.</span></span> <span data-ttu-id="93b85-116">HTTP-GET および HTTP-POST は明示的に無効になっています。</span><span class="sxs-lookup"><span data-stu-id="93b85-116">HTTP-GET and HTTP-POST are explicitly disabled.</span></span> <span data-ttu-id="93b85-117">Web ブラウザを使用して Web サービスをテストするには、HTTP-GET を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93b85-117">To test a Web service with a Web browser, you must enable HTTP-GET.</span></span>  
  
### <a name="to-modify-the-webconfig-file-for-the-published-web-service"></a><span data-ttu-id="93b85-118">公開済み Web サービスの Web.config ファイルを変更するには</span><span class="sxs-lookup"><span data-stu-id="93b85-118">To modify the Web.config file for the published Web service</span></span>  
  
1.  <span data-ttu-id="93b85-119">公開済み Web サービスの Web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="93b85-119">Open the Web.config file for the published Web service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="93b85-120">Web.config ファイルは、Web サービスを格納する IIS 仮想ルートとして構成したディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="93b85-120">You can find the Web.config file in the directory that you configured for the IIS virtual root that contains the Web service.</span></span>  
  
2.  <span data-ttu-id="93b85-121">検索、\<プロトコル > セクション。</span><span class="sxs-lookup"><span data-stu-id="93b85-121">Find the \<protocols> section:</span></span>  
  
    ```  
    <webServices>  
       <protocols>  
         <remove name="HttpPost" />  
         <remove name="HttpGet" />  
         <remove name="HttpPostLocalhost" />  
       </protocols>  
  
    </webServices>  
    ```  
  
3.  <span data-ttu-id="93b85-122">HTTP GET をテストするには、HTTP POST、または、ローカル コンピューターからの HTTP POST でから対応する行が削除、\<プロトコル > セクションでします。</span><span class="sxs-lookup"><span data-stu-id="93b85-122">For testing HTTP-GET, HTTP-POST, or HTTP-POST from the local computer, remove the corresponding line from the \<protocols> section.</span></span>  
  
 <span data-ttu-id="93b85-123">構成オプションの詳細についてを参照してください"構成オプションの XML Web サービス作成された ASP.NET を使用して"、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62264](http://go.microsoft.com/fwlink/?LinkId=62264)です。</span><span class="sxs-lookup"><span data-stu-id="93b85-123">For more information about the configuration options, see "Configuration Options for XML Web Services Created Using ASP.NET" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62264](http://go.microsoft.com/fwlink/?LinkId=62264).</span></span>  
  
#### <a name="to-access-a-web-service-with-internet-explorer"></a><span data-ttu-id="93b85-124">Internet Explorer を使用して Web サービスにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="93b85-124">To access a Web service with Internet Explorer</span></span>  
  
-   <span data-ttu-id="93b85-125">Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力 **http://*servername*/*apppath*/ *webservicename*.asmx * *。</span><span class="sxs-lookup"><span data-stu-id="93b85-125">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format **http://*servername*/*apppath*/*webservicename*.asmx**.</span></span>  
  
    |<span data-ttu-id="93b85-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93b85-126">Parameter</span></span>|<span data-ttu-id="93b85-127">値</span><span class="sxs-lookup"><span data-stu-id="93b85-127">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="93b85-128">***サーバー名***</span><span class="sxs-lookup"><span data-stu-id="93b85-128">***servername***</span></span>|<span data-ttu-id="93b85-129">XML Web サービスを配置したサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="93b85-129">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="93b85-130">***アプリケーションのパス***</span><span class="sxs-lookup"><span data-stu-id="93b85-130">***Apppath***</span></span>|<span data-ttu-id="93b85-131">仮想ディレクトリ名と Web アプリケーションのパスです。</span><span class="sxs-lookup"><span data-stu-id="93b85-131">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="93b85-132">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="93b85-132">***webservicename.asmx***</span></span>|<span data-ttu-id="93b85-133">XML Web サービスの .asmx ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="93b85-133">The name of the XML Web service .asmx file.</span></span>|  
  
 <span data-ttu-id="93b85-134">Web サービスの説明には、特定の Web サービスがサポートするすべての Web サービス メソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93b85-134">The description for the Web service shows you all the Web service methods that the particular Web service supports.</span></span> <span data-ttu-id="93b85-135">[Web サービスの説明] ページには、使用できる Web メソッドへのリンクと、Web サービスの説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="93b85-135">The Web service description page contains links for each available Web method and the service description of the Web service.</span></span>  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get"></a><span data-ttu-id="93b85-136">Internet Explorer で HTTP-GET を使用して Web サービスをテストするには</span><span class="sxs-lookup"><span data-stu-id="93b85-136">To test a Web service with Internet Explorer using HTTP-GET</span></span>  
  
1.  <span data-ttu-id="93b85-137">[Web サービスの説明] ページにアクセスし、一覧表示されている Web メソッドの 1 つをクリックします。</span><span class="sxs-lookup"><span data-stu-id="93b85-137">After accessing the Web service description page, click one of the Web methods listed in the Web service description page.</span></span>  
  
2.  <span data-ttu-id="93b85-138">Web メソッドに必要なパラメーターを入力し、クリックして**Invoke**です。</span><span class="sxs-lookup"><span data-stu-id="93b85-138">Type the necessary parameters for the Web method, and then click **Invoke**.</span></span>  
  
3.  <span data-ttu-id="93b85-139">サーバーがブラウザに XML 応答を返します。</span><span class="sxs-lookup"><span data-stu-id="93b85-139">The server returns an XML response in the browser.</span></span> <span data-ttu-id="93b85-140">Web サービスの戻り値のデータ型が倍精度浮動小数点数の場合、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="93b85-140">If the return data type for the Web service is a double-precision floating-point number, the result might look like the following:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a><span data-ttu-id="93b85-141">Internet Explorer で HTTP-GET を使用して Web サービスをテストするには (別の方法)</span><span class="sxs-lookup"><span data-stu-id="93b85-141">To test a Web service with Internet Explorer using HTTP-GET (alternate method)</span></span>  
  
1.  <span data-ttu-id="93b85-142">Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***です。</span><span class="sxs-lookup"><span data-stu-id="93b85-142">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***.</span></span>  
  
    |<span data-ttu-id="93b85-143">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93b85-143">Parameter</span></span>|<span data-ttu-id="93b85-144">値</span><span class="sxs-lookup"><span data-stu-id="93b85-144">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="93b85-145">***サーバー名***</span><span class="sxs-lookup"><span data-stu-id="93b85-145">***servername***</span></span>|<span data-ttu-id="93b85-146">XML Web サービスを配置したサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="93b85-146">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="93b85-147">***アプリケーションのパス***</span><span class="sxs-lookup"><span data-stu-id="93b85-147">***Apppath***</span></span>|<span data-ttu-id="93b85-148">仮想ディレクトリ名と Web アプリケーションのパスです。</span><span class="sxs-lookup"><span data-stu-id="93b85-148">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="93b85-149">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="93b85-149">***webservicename.asmx***</span></span>|<span data-ttu-id="93b85-150">XML Web サービスの .asmx ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="93b85-150">The name of the XML Web service .asmx file.</span></span>|  
    |<span data-ttu-id="93b85-151">***Methodname***</span><span class="sxs-lookup"><span data-stu-id="93b85-151">***Methodname***</span></span>|<span data-ttu-id="93b85-152">XML Web サービスが公開するパブリック メソッドの名前です。</span><span class="sxs-lookup"><span data-stu-id="93b85-152">The name of a public method that the XML Web service exposes.</span></span> <span data-ttu-id="93b85-153">空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます</span><span class="sxs-lookup"><span data-stu-id="93b85-153">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="93b85-154">(オプション)</span><span class="sxs-lookup"><span data-stu-id="93b85-154">(Optional)</span></span>|  
    |<span data-ttu-id="93b85-155">***パラメーター***</span><span class="sxs-lookup"><span data-stu-id="93b85-155">***parameter***</span></span>|<span data-ttu-id="93b85-156">メソッドで必須となっているパラメータの名前とその値です。</span><span class="sxs-lookup"><span data-stu-id="93b85-156">The appropriate parameter name and value for any parameters required by your method.</span></span> <span data-ttu-id="93b85-157">空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます</span><span class="sxs-lookup"><span data-stu-id="93b85-157">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="93b85-158">(オプション)</span><span class="sxs-lookup"><span data-stu-id="93b85-158">(Optional)</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="93b85-159">この構文の XML Web サービス メソッド名では、大文字と小文字が区別されますが、サーバー名、プロジェクト名、および XML Web サービス名では、区別されません。</span><span class="sxs-lookup"><span data-stu-id="93b85-159">The XML Web service method name in this syntax is case sensitive, but the server, project, and XML Web service names are not.</span></span>  
  
2.  <span data-ttu-id="93b85-160">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="93b85-160">Press Enter.</span></span> <span data-ttu-id="93b85-161">Web ブラウザに、サーバーからの XML 応答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="93b85-161">The Web browser displays an XML response from the server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="93b85-162">HTTP-POST を使用して Web サービスを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="93b85-162">You can also use HTTP-POST to call the Web service.</span></span> <span data-ttu-id="93b85-163">詳細およびサンプルについて、Web ブラウザーから XML Web サービスの呼び出しで「方法に:: アクセス XML Web サービス ブラウザーから」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62265](http://go.microsoft.com/fwlink/?LinkId=62265)です。</span><span class="sxs-lookup"><span data-stu-id="93b85-163">For information and samples about calling XML Web services from a Web browser, see "How to: Access XML Web Services from a Browser" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62265](http://go.microsoft.com/fwlink/?LinkId=62265).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b85-164">参照</span><span class="sxs-lookup"><span data-stu-id="93b85-164">See Also</span></span>  
 [<span data-ttu-id="93b85-165">公開済み Web サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="93b85-165">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)