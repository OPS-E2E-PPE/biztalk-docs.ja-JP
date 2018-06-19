---
title: 使用する Web サービスの URI を動的に設定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95829a28-7898-4757-87cc-40fc99bf707e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3766eb98ffe5d2b73d79f09c58cf98f081c644db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254938"
---
# <a name="how-to-dynamically-set-the-uri-of-a-consumed-web-service"></a>使用する Web サービスの URI の動的な設定方法
使用する Web サービスの Web ポートを作成するときは、ポートの動的バインドを選択できます。 ポートの動的バインドを選択するときは、使用する Web サービスの URI を実行時に設定する必要があります。 選択した URI は、Web ポートの種類の作成時に使用した Web サービスと同じ Web プロキシを持つ Web サービスを呼び出す必要があります。  
  
> [!NOTE]
>  このトピックでは、オーケストレーション内の動的な SOAP 送信ポートのプロパティを、プログラムによって動的に設定する方法について説明します。 ただし、これらのプロパティは、送信ポートが静的であるか動的であるかにかかわらず、オーケストレーションまたはカスタム パイプライン コンポーネントに設定することもできます。 カスタム パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。  
  
 Web ポート用の動的バインドの動作は、Web ポート以外のポートの動的バインドの動作とは異なります。 Web ポート以外のポートの動的バインドを選択する場合、SOAP アダプタを使用することはできません。  
  
 動的な Web ポートで Web サービスを使用する場合、送信ポートのプロパティは既定値に設定されます。 これらの値の一部が内部で設定されており、既定値に設定されている値に、 **SOAP アダプタ ハンドラ**プロパティ ページ。 オーケストレーション内のこれらの値は、動的送信ポートを使用するときに上書きできます。 詳細については、次を参照してください。[に関する考慮事項と Web サービスの利用](../core/considerations-when-consuming-web-services.md)です。  
  
## <a name="dynamically-change-the-uri-of-a-consumed-web-service"></a>使用する Web サービスの URI を動的に変更します。  
  
1.  説明したように、Web ポートを追加[Web ポートを追加する方法](../core/how-to-add-a-web-port.md)です。 選択する代わりに、ただし、**今指定する**ポート バインドで、**動的**ポートのバインド、次の図に示すようにします。  
  
     ![](../core/media/ebiz-prog-wsc-dynamic.gif "ebiz_prog_wsc_dynamic")  
  
2.  使用する Web サービスを呼び出すオーケストレーションの追加、**式**いくつかの時点より前のバージョンの図形、**送信**Web ポートに接続されている図形です。  
  
3.  **式**図形は、ような式を追加します。  
  
    ```  
    myWebPort(Microsoft.XLANGs.BaseTypes.Address) = "http://orders/myCompany.asmx";  
    ```  
  
> [!NOTE]
>  BizTalk 式エディタで使用する URI は、受信メッセージ、SQL データベース、基幹業務アプリケーションなどのさまざまな場所から取得できます。  
  
## <a name="dynamically-modify-send-port-properties"></a>送信ポートのプロパティを動的に変更します。  
  
1.  **メッセージの構築**図形を使用して Web メッセージの作成、追加、**メッセージの割り当て**図形のいずれかが存在しない場合。  
  
2.  **メッセージの割り当て**図形は、ような式を追加します。  
  
    ```  
    myWebMessage(SOAP.UseSSO) = true;  
    ```  
  
 SOAP 送信ポートのプロパティでは、いずれも SOAP 名前空間を使用します。  
  
 次の表に、動的な Web ポートの使用時に設定できる SOAP 送信ポートのプロパティの一覧を示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**AuthenticationScheme**|文字列|Web サービスの呼び出しに使用する認証方法です。<br /><br /> 既定値: 匿名<br /><br /> その他の有効な値: Basic、Digest、NTLM|  
|**ユーザー名**|文字列|対象の Web サービスにアクセスするために指定するユーザー名です。<br /><br /> 既定値: 空白|  
|**Password**|文字列|サーバーでの認証に使用するユーザーのパスワード。<br /><br /> 既定値: 空白|  
|**ClientCertificate**|文字列|Secure Sockets Layer (SSL) 証明書の拇印です。<br /><br /> 既定値: 空白|  
|**UseSSO**|ブール値|この Web ポートがシングル サインオン (SSO) を使用するかどうかを示します。<br /><br /> 既定値: False|  
|**AffiliateApplicationName**|文字列|この Web ポートが、クライアントの資格情報と引き換えるために使用する SSO アプリケーションの名前です。<br /><br /> 既定値: 空白|  
|**UseHandlerSetting**|ブール値|この Web ポートが、SOAP 送信ハンドラの HTTP プロキシ設定を使用するかどうかを示します。 **注:** 場合、 **UseProxy**コンテキスト プロパティを設定し、 **UseHandlerSetting**コンテキスト プロパティは無視されます。 <br /><br /> 既定値: False|  
|**UseProxy**|ブール値|この Web ポートで、対象の Web サービスへのアクセスにプロキシ サーバーを使用するかどうかを示します。 **注:** 場合、 **UseProxy**コンテキスト プロパティを設定し、 **UseHandlerSetting**コンテキスト プロパティは無視されます。 <br /><br /> 既定値: False|  
|**ProxyAddress**|文字列|Web サービスの呼び出しに使用する HTTP プロキシのアドレスです。<br /><br /> 既定値: SOAP 送信ハンドラのプロパティから取得します。|  
|**ProxyPort**|Integer|Web サービスの呼び出しに使用する HTTP プロキシのポートです。<br /><br /> 既定値: SOAP 送信ハンドラのプロパティから取得します。|  
|**ProxyUsername**|文字列|HTTP プロキシに使用するユーザー名です。<br /><br /> 既定値: SOAP 送信ハンドラのプロパティから取得します。|  
|**ProxyPassword**|文字列|HTTP プロキシに使用するパスワードです。<br /><br /> 既定値: SOAP 送信ハンドラのプロパティから取得します。|  
|**ClientConnectionTimeout**|Int32|HTTP クライアント接続のタイムアウト値です。<br /><br /> 既定値: ASP.NET の HTTP 接続タイムアウトの既定値と同じです。|  
|**型名**|文字列|呼び出す Web メソッドを含むクラスの名前を指定します。<br /><br /> 既定値: 空白|  
|**MethodName**|文字列|呼び出すクラスのメソッドを指定します。 **注:** を構成する**MethodName**プロパティの静的 SOAP 送信ポートがプログラムで、設定する必要があります**メソッド名**としてに **[後で指定]** で**Web サービス**のタブ、 **SOAP トランスポートのプロパティ**BizTalk Server 管理コンソールのダイアログ ボックス。 詳細については**SOAP トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **SOAP トランスポートのプロパティ ダイアログ ボックス、Web サービス**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 <br /><br /> 既定値: 空白|  
|**AssemblyName**|文字列|読み込んで実行する .NET 型およびアセンブリを識別します。<br /><br /> 既定値: 空白|  
|**UnknownHeaders**|文字列|不明な SOAP ヘッダーのシリアル化された一覧を指定します。<br /><br /> 既定値: 空白|  
|**UserDefined**|文字列|ユーザー定義クラスを定義します。<br /><br /> 既定値: 空白|  
|**UseSoap12**|ブール値|SOAP 1.2 プロトコルをサポートするプロキシ コードを生成する場合に指定します。 このプロパティが False の場合は、SOAP 1.1 準拠のプロキシ コードが生成されます。<br /><br /> 既定値: False|  
  
> [!NOTE]
>  を除き、 **ClientConnectionTimeout**設定すると、これらの値のみ動的に設定できますを使用する場合**動的**ポートのバインド。 読み取り専用で使用する場合、**今指定**ポートのバインド。 設定することができます、 **ClientConnectionTimeout**の両設定**今指定**と**動的**ポートのバインド。  
  
## <a name="see-also"></a>参照  
 [使用する Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md)   
 [Web ポートの作成](../core/creating-web-ports.md)