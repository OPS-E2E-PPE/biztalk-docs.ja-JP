---
title: "BizTalk web サービスをテスト |Microsoft ドキュメント"
description: "構成する受信場所と、web ブラウザーで BizTalk web サービスをテストする web.config"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dc2171d-4abe-43db-b4bc-e484048c6430
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a35373735102bd75d1c388da29b06d4392ba18
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="test-a-biztalk-web-service"></a><span data-ttu-id="ca3e2-103">BizTalk Web サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-103">Test a BizTalk Web Service</span></span>

## <a name="overview"></a><span data-ttu-id="ca3e2-104">概要</span><span class="sxs-lookup"><span data-stu-id="ca3e2-104">Overview</span></span>
<span data-ttu-id="ca3e2-105">Web クライアント アプリケーションを記述せずに、公開済み Web サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-105">You can test your published Web service without writing a Web client application.</span></span> <span data-ttu-id="ca3e2-106">Internet Explorer などの Web ブラウザを使用して、公開済み Web サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-106">You can use a Web browser, such as Internet Explorer, to test your published Web service.</span></span> <span data-ttu-id="ca3e2-107">Web ブラウザを使用して公開済み Web サービスにアクセスできますが、テストできるのは、単純な型パラメータを使用する Web メソッドを持つ Web サービスのみです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-107">Although you can access any published Web service using a Web browser, you can only test Web services with Web methods that contain simple type parameters.</span></span> <span data-ttu-id="ca3e2-108">Web ブラウザーで、Web メソッドをテストするには、受信ポートで使用される要求と応答メッセージのメッセージ部分できるだけ単純型など**System.String**または**System.Int32**です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-108">To test your Web method in a Web browser, your message parts for the request and response messages that are used in the receive port can only be a simple type, such as **System.String** or **System.Int32**.</span></span> <span data-ttu-id="ca3e2-109">メッセージ部分がメッセージ型としてスキーマを使用している場合、ブラウザで Web メソッドをテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-109">If any message part uses a schema as a message type, you cannot test the Web method with a browser.</span></span>  
  
 <span data-ttu-id="ca3e2-110">HTTP-GET または HTTP-POST を使用して公開済み Web サービスをテストするには、SOAP アダプタの BizTalk 受信場所を構成し、公開済み Web サービスの Web.config ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-110">If you want to test your published Web services using HTTP-GET or HTTP-POST, you must configure your BizTalk receive location for the SOAP adapter and modify the Web.config file for your published Web service.</span></span>  
  
 <span data-ttu-id="ca3e2-111">**変更、受信場所**</span><span class="sxs-lookup"><span data-stu-id="ca3e2-111">**Modifying the Receive Locations**</span></span>  
  
 <span data-ttu-id="ca3e2-112">SOAP アダプタは、受信場所を構成するとき、通常、次の仮想ディレクトリと Web サービスの .asmx ファイルの名前を指定することで、受信場所の URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-112">When the SOAP adapter configures receive locations, the SOAP adapter normally sets the URI of the receive location by giving the virtual directory and the Web service .asmx file name:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 <span data-ttu-id="ca3e2-113">これにより、SOAP アダプタは HTTP-SOAP プロトコルを使用して Web サービス要求を受信できます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-113">This allows the SOAP adapter to receive Web service requests using the HTTP-SOAP protocol.</span></span> <span data-ttu-id="ca3e2-114">HTTP-GET プロトコルまたは HTTP-POST プロトコルを使用するように受信場所を構成するには、次のようにメソッド名を URI に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-114">To configure the receive location to use the HTTP-GET or HTTP-POST protocol, you must append the method name to the URI:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 <span data-ttu-id="ca3e2-115">メソッド名は、オーケストレーションのポート操作名と同じです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-115">The method name is the same as the port operation name in the orchestration.</span></span>  
  
 <span data-ttu-id="ca3e2-116">**Web.config ファイルを変更します。**</span><span class="sxs-lookup"><span data-stu-id="ca3e2-116">**Modifying the Web.config file**</span></span>  
  
 <span data-ttu-id="ca3e2-117">既定では、Web サービスは HTTP-SOAP プロトコルを使用するようウィザードにより構成されます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-117">By default, the wizard configures the Web services to use the HTTP-SOAP protocol.</span></span> <span data-ttu-id="ca3e2-118">HTTP-GET および HTTP-POST は明示的に無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-118">HTTP-GET and HTTP-POST are explicitly disabled.</span></span> <span data-ttu-id="ca3e2-119">Web ブラウザを使用して Web サービスをテストするには、HTTP-GET を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-119">To test a Web service with a Web browser, you must enable HTTP-GET.</span></span>  
  
## <a name="update-the-webconfig"></a><span data-ttu-id="ca3e2-120">Web.config を更新します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-120">Update the Web.config</span></span>
  
1.  <span data-ttu-id="ca3e2-121">公開済み Web サービスの Web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-121">Open the Web.config file for the published Web service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca3e2-122">Web.config ファイルは、Web サービスを格納する IIS 仮想ルートとして構成したディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-122">You can find the Web.config file in the directory that you configured for the IIS virtual root that contains the Web service.</span></span>  
  
2.  <span data-ttu-id="ca3e2-123">検索、\<プロトコル\>セクション。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-123">Find the \<protocols\> section:</span></span>  
  
    ```  
    <webServices>  
       <protocols>  
         <remove name="HttpPost" />  
         <remove name="HttpGet" />  
         <remove name="HttpPostLocalhost" />  
       </protocols>  
  
    </webServices>  
    ```  
  
3.  <span data-ttu-id="ca3e2-124">HTTP GET をテストするには、HTTP POST、または、ローカル コンピューターからの HTTP POST でから対応する行が削除、\<プロトコル\>セクションです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-124">For testing HTTP-GET, HTTP-POST, or HTTP-POST from the local computer, remove the corresponding line from the \<protocols\> section.</span></span>  
  
 <span data-ttu-id="ca3e2-125">構成オプションの詳細については、次を参照してください。 [ASP.NET を使用して作成した XML Web サービスの構成オプション](https://msdn.microsoft.com/library/b2c0ew36.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-125">For more information about the configuration options, see [Configuration Options for XML Web Services Created Using ASP.NET](https://msdn.microsoft.com/library/b2c0ew36.aspx).</span></span> 
  
#### <a name="access-a-web-service-with-internet-explorer"></a><span data-ttu-id="ca3e2-126">Internet Explorer で Web サービスへのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-126">Access a Web service with Internet Explorer</span></span>  
  
-   <span data-ttu-id="ca3e2-127">Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力 **http://*servername*/*apppath*/ *webservicename*.asmx * *。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-127">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format **http://*servername*/*apppath*/*webservicename*.asmx**.</span></span>  
  
    |<span data-ttu-id="ca3e2-128">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ca3e2-128">Parameter</span></span>|<span data-ttu-id="ca3e2-129">値</span><span class="sxs-lookup"><span data-stu-id="ca3e2-129">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="ca3e2-130">***サーバー名***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-130">***servername***</span></span>|<span data-ttu-id="ca3e2-131">XML Web サービスを配置したサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-131">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="ca3e2-132">***アプリケーションのパス***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-132">***Apppath***</span></span>|<span data-ttu-id="ca3e2-133">仮想ディレクトリ名と Web アプリケーションのパスです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-133">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="ca3e2-134">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-134">***webservicename.asmx***</span></span>|<span data-ttu-id="ca3e2-135">XML Web サービスの .asmx ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-135">The name of the XML Web service .asmx file.</span></span>|  
  
 <span data-ttu-id="ca3e2-136">Web サービスの説明には、特定の Web サービスがサポートするすべての Web サービス メソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-136">The description for the Web service shows you all the Web service methods that the particular Web service supports.</span></span> <span data-ttu-id="ca3e2-137">[Web サービスの説明] ページには、使用できる Web メソッドへのリンクと、Web サービスの説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-137">The Web service description page contains links for each available Web method and the service description of the Web service.</span></span>  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get"></a><span data-ttu-id="ca3e2-138">HTTP GET を使用する Internet Explorer で Web サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-138">Test a Web service with Internet Explorer using HTTP-GET</span></span>  
  
1.  <span data-ttu-id="ca3e2-139">[Web サービスの説明] ページにアクセスし、一覧表示されている Web メソッドの 1 つをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-139">After accessing the Web service description page, click one of the Web methods listed in the Web service description page.</span></span>  
  
2.  <span data-ttu-id="ca3e2-140">Web メソッドに必要なパラメーターを入力し、クリックして**Invoke**です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-140">Type the necessary parameters for the Web method, and then click **Invoke**.</span></span>  
  
3.  <span data-ttu-id="ca3e2-141">サーバーがブラウザに XML 応答を返します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-141">The server returns an XML response in the browser.</span></span> <span data-ttu-id="ca3e2-142">Web サービスの戻り値のデータ型が倍精度浮動小数点数の場合、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-142">If the return data type for the Web service is a double-precision floating-point number, the result might look like the following:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a><span data-ttu-id="ca3e2-143">HTTP GET (代替手段) を使用する Internet Explorer で Web サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-143">Test a Web service with Internet Explorer using HTTP-GET (alternate method)</span></span>  
  
1.  <span data-ttu-id="ca3e2-144">Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-144">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***.</span></span>  
  
    |<span data-ttu-id="ca3e2-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ca3e2-145">Parameter</span></span>|<span data-ttu-id="ca3e2-146">値</span><span class="sxs-lookup"><span data-stu-id="ca3e2-146">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="ca3e2-147">***サーバー名***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-147">***servername***</span></span>|<span data-ttu-id="ca3e2-148">XML Web サービスを配置したサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-148">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="ca3e2-149">***アプリケーションのパス***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-149">***Apppath***</span></span>|<span data-ttu-id="ca3e2-150">仮想ディレクトリ名と Web アプリケーションのパスです。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-150">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="ca3e2-151">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-151">***webservicename.asmx***</span></span>|<span data-ttu-id="ca3e2-152">XML Web サービスの .asmx ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-152">The name of the XML Web service .asmx file.</span></span>|  
    |<span data-ttu-id="ca3e2-153">***Methodname***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-153">***Methodname***</span></span>|<span data-ttu-id="ca3e2-154">XML Web サービスが公開するパブリック メソッドの名前です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-154">The name of a public method that the XML Web service exposes.</span></span> <span data-ttu-id="ca3e2-155">空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます</span><span class="sxs-lookup"><span data-stu-id="ca3e2-155">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="ca3e2-156">(オプション)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-156">(Optional)</span></span>|  
    |<span data-ttu-id="ca3e2-157">***パラメーター***</span><span class="sxs-lookup"><span data-stu-id="ca3e2-157">***parameter***</span></span>|<span data-ttu-id="ca3e2-158">メソッドで必須となっているパラメータの名前とその値です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-158">The appropriate parameter name and value for any parameters required by your method.</span></span> <span data-ttu-id="ca3e2-159">空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます</span><span class="sxs-lookup"><span data-stu-id="ca3e2-159">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="ca3e2-160">(オプション)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-160">(Optional)</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="ca3e2-161">この構文の XML Web サービス メソッド名では、大文字と小文字が区別されますが、サーバー名、プロジェクト名、および XML Web サービス名では、区別されません。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-161">The XML Web service method name in this syntax is case sensitive, but the server, project, and XML Web service names are not.</span></span>  
  
2.  <span data-ttu-id="ca3e2-162">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-162">Press Enter.</span></span> <span data-ttu-id="ca3e2-163">Web ブラウザに、サーバーからの XML 応答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-163">The Web browser displays an XML response from the server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca3e2-164">HTTP-POST を使用して Web サービスを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-164">You can also use HTTP-POST to call the Web service.</span></span> <span data-ttu-id="ca3e2-165">詳細およびサンプル Web ブラウザーから XML Web サービスの呼び出しについてを参照してください[ブラウザーから XML Web サービスにアクセス](https://msdn.microsoft.com/library/45fez2a8.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="ca3e2-165">For information and samples about calling XML Web services from a Web browser, see [Access XML Web Services from a Browser](https://msdn.microsoft.com/library/45fez2a8.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3e2-166">参照</span><span class="sxs-lookup"><span data-stu-id="ca3e2-166">See Also</span></span>  
 [<span data-ttu-id="ca3e2-167">公開済み Web サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="ca3e2-167">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)