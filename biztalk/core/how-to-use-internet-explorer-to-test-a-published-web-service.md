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
# <a name="how-to-use-internet-explorer-to-test-a-published-web-service"></a>Internet Explorer を使用して、公開された Web サービスをテストする方法
Web クライアント アプリケーションを記述せずに、公開済み Web サービスをテストできます。 Internet Explorer などの Web ブラウザを使用して、公開済み Web サービスをテストできます。 Web ブラウザを使用して公開済み Web サービスにアクセスできますが、テストできるのは、単純な型パラメータを使用する Web メソッドを持つ Web サービスのみです。 Web ブラウザーで、Web メソッドをテストするには、受信ポートで使用される要求と応答メッセージのメッセージ部分できるだけ単純型など**System.String**または**System.Int32**です。 メッセージ部分がメッセージ型としてスキーマを使用している場合、ブラウザで Web メソッドをテストすることはできません。  
  
 HTTP-GET または HTTP-POST を使用して公開済み Web サービスをテストするには、SOAP アダプタの BizTalk 受信場所を構成し、公開済み Web サービスの Web.config ファイルを変更する必要があります。  
  
 **変更、受信場所**  
  
 SOAP アダプタは、受信場所を構成するとき、通常、次の仮想ディレクトリと Web サービスの .asmx ファイルの名前を指定することで、受信場所の URI を設定します。  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 これにより、SOAP アダプタは HTTP-SOAP プロトコルを使用して Web サービス要求を受信できます。 HTTP-GET プロトコルまたは HTTP-POST プロトコルを使用するように受信場所を構成するには、次のようにメソッド名を URI に追加する必要があります。  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 メソッド名は、オーケストレーションのポート操作名と同じです。  
  
 **Web.config ファイルを変更します。**  
  
 既定では、Web サービスは HTTP-SOAP プロトコルを使用するようウィザードにより構成されます。 HTTP-GET および HTTP-POST は明示的に無効になっています。 Web ブラウザを使用して Web サービスをテストするには、HTTP-GET を有効にする必要があります。  
  
### <a name="to-modify-the-webconfig-file-for-the-published-web-service"></a>公開済み Web サービスの Web.config ファイルを変更するには  
  
1.  公開済み Web サービスの Web.config ファイルを開きます。  
  
    > [!NOTE]
    >  Web.config ファイルは、Web サービスを格納する IIS 仮想ルートとして構成したディレクトリ内にあります。  
  
2.  検索、\<プロトコル > セクション。  
  
    ```  
    <webServices>  
       <protocols>  
         <remove name="HttpPost" />  
         <remove name="HttpGet" />  
         <remove name="HttpPostLocalhost" />  
       </protocols>  
  
    </webServices>  
    ```  
  
3.  HTTP GET をテストするには、HTTP POST、または、ローカル コンピューターからの HTTP POST でから対応する行が削除、\<プロトコル > セクションでします。  
  
 構成オプションの詳細についてを参照してください"構成オプションの XML Web サービス作成された ASP.NET を使用して"、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62264](http://go.microsoft.com/fwlink/?LinkId=62264)です。  
  
#### <a name="to-access-a-web-service-with-internet-explorer"></a>Internet Explorer を使用して Web サービスにアクセスするには  
  
-   Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力 **http://*servername*/*apppath*/ *webservicename*.asmx * *。  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |***サーバー名***|XML Web サービスを配置したサーバーの名前です。|  
    |***アプリケーションのパス***|仮想ディレクトリ名と Web アプリケーションのパスです。|  
    |***webservicename.asmx***|XML Web サービスの .asmx ファイルの名前です。|  
  
 Web サービスの説明には、特定の Web サービスがサポートするすべての Web サービス メソッドが表示されます。 [Web サービスの説明] ページには、使用できる Web メソッドへのリンクと、Web サービスの説明が含まれます。  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get"></a>Internet Explorer で HTTP-GET を使用して Web サービスをテストするには  
  
1.  [Web サービスの説明] ページにアクセスし、一覧表示されている Web メソッドの 1 つをクリックします。  
  
2.  Web メソッドに必要なパラメーターを入力し、クリックして**Invoke**です。  
  
3.  サーバーがブラウザに XML 応答を返します。 Web サービスの戻り値のデータ型が倍精度浮動小数点数の場合、結果は次のようになります。  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="to-test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a>Internet Explorer で HTTP-GET を使用して Web サービスをテストするには (別の方法)  
  
1.  Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***です。  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |***サーバー名***|XML Web サービスを配置したサーバーの名前です。|  
    |***アプリケーションのパス***|仮想ディレクトリ名と Web アプリケーションのパスです。|  
    |***webservicename.asmx***|XML Web サービスの .asmx ファイルの名前です。|  
    |***Methodname***|XML Web サービスが公開するパブリック メソッドの名前です。 空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます (オプション)|  
    |***パラメーター***|メソッドで必須となっているパラメータの名前とその値です。 空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます (オプション)|  
  
    > [!NOTE]
    >  この構文の XML Web サービス メソッド名では、大文字と小文字が区別されますが、サーバー名、プロジェクト名、および XML Web サービス名では、区別されません。  
  
2.  Enter キーを押します。 Web ブラウザに、サーバーからの XML 応答が表示されます。  
  
    > [!NOTE]
    >  HTTP-POST を使用して Web サービスを呼び出すこともできます。 詳細およびサンプルについて、Web ブラウザーから XML Web サービスの呼び出しで「方法に:: アクセス XML Web サービス ブラウザーから」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62265](http://go.microsoft.com/fwlink/?LinkId=62265)です。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスのテスト](../core/testing-published-web-services.md)