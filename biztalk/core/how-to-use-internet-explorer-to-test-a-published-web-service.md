---
title: BizTalk web サービスのテスト |Microsoft Docs
description: 構成の受信場所と、web ブラウザーで BizTalk web サービスをテストする web.config
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dc2171d-4abe-43db-b4bc-e484048c6430
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf7e57d163b5729685c4103a8a3e5da78e37355
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979691"
---
# <a name="test-a-biztalk-web-service"></a>BizTalk Web サービスをテストします。

## <a name="overview"></a>概要
Web クライアント アプリケーションを記述せずに、公開済み Web サービスをテストできます。 Internet Explorer などの Web ブラウザを使用して、公開済み Web サービスをテストできます。 Web ブラウザを使用して公開済み Web サービスにアクセスできますが、テストできるのは、単純な型パラメータを使用する Web メソッドを持つ Web サービスのみです。 Web ブラウザーで Web メソッドをテストするには、受信ポートで使用される要求と応答メッセージのメッセージ部分ことができますのみ単純型であるなど**System.String**または**System.Int32**します。 メッセージ部分がメッセージ型としてスキーマを使用している場合、ブラウザで Web メソッドをテストすることはできません。  
  
 HTTP-GET または HTTP-POST を使用して公開済み Web サービスをテストするには、SOAP アダプタの BizTalk 受信場所を構成し、公開済み Web サービスの Web.config ファイルを変更する必要があります。  
  
 **変更の受信場所**  
  
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
  
## <a name="update-the-webconfig"></a>Web.config を更新します。
  
1. 公開済み Web サービスの Web.config ファイルを開きます。  
  
   > [!NOTE]
   >  Web.config ファイルは、Web サービスを格納する IIS 仮想ルートとして構成したディレクトリ内にあります。  
  
2. 検索、\<プロトコル\>セクション。  
  
   ```  
   <webServices>  
      <protocols>  
        <remove name="HttpPost" />  
        <remove name="HttpGet" />  
        <remove name="HttpPostLocalhost" />  
      </protocols>  
  
   </webServices>  
   ```  
  
3. HTTP GET をテストするには、HTTP POST、またはローカルのコンピューターから HTTP-POST で対応する行が削除、\<プロトコル\>セクション。  
  
   構成オプションの詳細については、次を参照してください。 [ASP.NET を使用して作成した XML Web サービスの構成オプション](https://msdn.microsoft.com/library/b2c0ew36.aspx)します。 
  
#### <a name="access-a-web-service-with-internet-explorer"></a>Internet Explorer で Web サービスへのアクセスします。  
  
- Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力**http://<em>servername</em>/*apppath* /*webservicename*.asmx**します。  
  
  |パラメーター|値|  
  |---------------|-----------|  
  |***servername***|XML Web サービスを配置したサーバーの名前です。|  
  |***apppath***|仮想ディレクトリ名と Web アプリケーションのパスです。|  
  |***webservicename.asmx***|XML Web サービスの .asmx ファイルの名前です。|  
  
  Web サービスの説明には、特定の Web サービスがサポートするすべての Web サービス メソッドが表示されます。 [Web サービスの説明] ページには、使用できる Web メソッドへのリンクと、Web サービスの説明が含まれます。  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get"></a>HTTP GET を使用して Internet Explorer で Web サービスをテストします。  
  
1.  [Web サービスの説明] ページにアクセスし、一覧表示されている Web メソッドの 1 つをクリックします。  
  
2.  Web メソッドに必要なパラメーターを入力し、クリックして**Invoke**します。  
  
3.  サーバーがブラウザに XML 応答を返します。 Web サービスの戻り値のデータ型が倍精度浮動小数点数の場合、結果は次のようになります。  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a>HTTP GET (代替手段) を使用して Internet Explorer で Web サービスをテストします。  
  
1.  Internet explorer で、**アドレス**ボックスに、形式を使用して Web サービスの URL を入力 ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***します。  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |***servername***|XML Web サービスを配置したサーバーの名前です。|  
    |***apppath***|仮想ディレクトリ名と Web アプリケーションのパスです。|  
    |***webservicename.asmx***|XML Web サービスの .asmx ファイルの名前です。|  
    |***Methodname***|XML Web サービスが公開するパブリック メソッドの名前です。 空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます (オプション)|  
    |***parameter***|メソッドで必須となっているパラメータの名前とその値です。 空白にすると、XML Web サービスの説明ページが表示され、.asmx ファイルで使用できるパブリック メソッドが一覧表示されます (オプション)|  
  
    > [!NOTE]
    >  この構文の XML Web サービス メソッド名では、大文字と小文字が区別されますが、サーバー名、プロジェクト名、および XML Web サービス名では、区別されません。  
  
2.  Enter キーを押します。 Web ブラウザに、サーバーからの XML 応答が表示されます。  
  
    > [!NOTE]
    >  HTTP-POST を使用して Web サービスを呼び出すこともできます。 Web ブラウザーから XML Web サービスの呼び出しのサンプルとは、次を参照してください。[ブラウザーから XML Web サービスにアクセス](https://msdn.microsoft.com/library/45fez2a8.aspx)します。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスのテスト](../core/testing-published-web-services.md)