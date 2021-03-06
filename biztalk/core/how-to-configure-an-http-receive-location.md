---
title: HTTP 受信場所を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, HTTP adapters
- configuring [HTTP adapters], receive locations
- HTTP adapters, receive locations
ms.assetid: 901adfc8-0361-49d9-b992-c27089dfbd3b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d5c6bde11a4e0ca382815842e0eb71794dc422
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341747"
---
# <a name="how-to-configure-an-http-receive-location"></a>HTTP の受信場所を構成する方法
HTTP の受信場所のアダプタ変数は、プログラムから、または BizTalk Server 管理コンソールを使用して設定できます。 プロパティが受信場所に設定されていない場合は、BizTalk Server 管理コンソールで設定された既定の受信ハンドラーの値が使用されます。  

> [!NOTE]
>  次の手順を実行する前に、受信ポートを追加する必要があります。 詳細については、「[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)します。  

 **HTTP 受信場所構成するプログラムを使用する方法**  

 HTTP アダプタの構成情報は BizTalk 管理データベース (構成データベース) に書き込まれます。 この構成はカスタム XML プロパティ バッグに保存されます。  

 BizTalk エクスプローラ オブジェクト モデルを公開、**という**構成インターフェイスを**TransportTypeData**読み取り/書き込みプロパティ。 このプロパティでは、名前と値の組の XML 文字列の形式で HTTP の受信場所の構成プロパティ バッグを指定できます。  

 設定、 **TransportTypeData**のプロパティ、**という**は必要ありません。 このプロパティを設定しない場合、HTTP の受信場所の構成の既定値が使用されます。 次の表に、既定値に加え、BizTalk エクスプローラ オブジェクト モデルで HTTP の受信場所用に設定できる構成プロパティを示します。  

|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|**ResponseContentType**|string|HTTP アダプタによってこの受信場所からクライアントに返送される HTTP 応答メッセージのコンテンツの種類です。 このプロパティは、要求 - 応答の受信ポートに対してのみ有効です。一方向の受信ポートでは無視されます。|String<br /><br /> **最小長:** 0<br /><br /> **最大長:** 256|既定値:テキストまたは XML|  
|**ループバック**|ブール値|この場所で受信した要求メッセージが、送信ポートにルーティングされるか、またはこの受信場所にルーティングされて応答として送信されるかを指定します。 このプロパティは、要求 - 応答の受信ポートに対してのみ有効です。 これは無視されます一方向受信ポート。|なし|**既定値:** False|  
|**ReturnCorrelationHandle**|ブール値|メッセージの送信に成功した場合に、クライアントに対する HTTP 応答で送信されたメッセージの関連付けトークンを HTTP アダプタから送信するかどうかを指定します。 このプロパティは、一方向の受信ポートに対してのみ有効です。要求 - 応答の受信ポートでは無視されます。|なし|**既定値:** True|  
|**SuspendFailedRequests**|ブール値|失敗した HTTP 要求を中断するかどうかを指定します。 値を True に設定すると、失敗した要求は中断されます。また、一方向の受信ポートの場合はクライアントに "受理" 状態コード (202) が送信され、双方向の受信ポートの場合はクライアントに "エラー" 状態コード (500) が送信されます。|なし|**既定値:** False|  
|**UseSSO**|ブール値|HTTP アダプタが、この受信場所で受信するメッセージに SSO チケットを発行するかどうかを指定します。|なし|**既定値:** False|  

 これらのプロパティを設定する XML 文字列の形式は次のとおりです。  

```  
<CustomProps>  
   <UseSSO vt="11">-1</UseSSO>  
   <SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
   <ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
   <ResponseContentType vt="8">text/xml</ResponseContentType>  
   <LoopBack vt="11">-1</LoopBack>  
</CustomProps>  

```  

 **HTTP 受信場所を BizTalk Server 管理コンソールを構成する方法**  

 BizTalk Server 管理コンソールを使用して受信場所を構成するには、次の手順を実行します。  

### <a name="to-configure-variables-for-an-http-receive-location"></a>HTTP の受信場所の変数を構成するには  

1. HTTP の受信場所を使用するようにインターネット インフォメーション サービス (IIS) を構成します。 IIS を構成する方法については、次を参照してください。 [IIS の HTTP 受信場所を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)します。  

2. BizTalk Server 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、受信場所を作成するアプリケーションです。  

3. 左側のウィンドウでをクリックして、**受信ポート**ノード。 次に右ウィンドウで、既存の受信場所に関連付けられているか、新しい受信場所に関連付ける受信ポートを右クリックし、**[プロパティ]** をクリックします。  

4. **受信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウで、**受信場所**、右側のウィンドウは、既存の受信場所 をクリックしてまたはダブルクリックで**新規**新しい受信場所を作成します。  

5. **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**、 **HTTP**ドロップダウン リストからクリックして**構成**します。  

6. **HTTP トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  


   |                           プロパティ                           |                                                                                                                                                                                                                                                                                                                                目的                                                                                                                                                                                                                                                                                                                                |
   |--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |          **仮想ディレクトリと ISAPI 拡張**          | HTTP/HTTPS 受信場所によって受信されたメッセージの送信先仮想ディレクトリの名前を指定します。 仮想ディレクトリには、受信場所 DLL の名前と省略可能なクエリ文字列が含まれます。 仮想ディレクトリ名の例を以下に示します。<br /><br /> /\<仮想ディレクトリ\>>/btshttpreceive.dll<br /><br /> /\<仮想ディレクトリ\>>/btshttpreceive.dll でしょうか。購入 %20order<br /><br /> この場所 (すべてのサブフォルダを含む) には、複数の ISAPI 拡張 (BTSHTTPReceive.dll) を格納しないでください。<br /><br /> **種類:** String<br /><br /> **最大長:** 256**に注意してください。** URI を送信ポートまたは受信場所が 256 文字を超えることはできません。  |
   |                      **パブリック アドレス**                      | この受信場所の完全修飾 URI を指定します。 このプロパティの値は、サーバー名と仮想ディレクトリの組み合わせです。 BizTalk メッセージング エンジンは、このアドレスを外部のパートナーに公開します。 指定した URI は、取引先から BizTalk Server へのメッセージの送信時に接続するためのパブリック Web サイト URL を示す必要があります。<br /><br /> この情報は省略可能で、BizTalk Server では使用されません。 このパラメーターを使用すると、管理者は、受信場所が関連付けられているパブリック URL を記述できます。<br /><br /> **種類:** String<br /><br /> **最小長:** 0<br /><br /> **最大長:** 256 |
   |                   **返すコンテンツの種類**                    |                                                                                                                                                                            受信場所からクライアントに返送される HTTP 応答メッセージのコンテンツの種類を指定します。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> **既定値:** テキスト/xml<br /><br /> **種類:** String<br /><br /> **最小長:** 0<br /><br /> **最大長:** 256                                                                                                                                                                            |
   |                         **Loopback**                         |                                                                                                                                                                                       この場所で受信した要求メッセージが、送信ポートにルーティングされるか、またはこの受信場所にルーティングされて応答として送信されるかを定義します。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> **既定値:** False<br /><br /> **種類:** ブール値                                                                                                                                                                                        |
   | **戻り値の関連付けハンドルを成功した場合 (一方向ポートのみ)** |                                                                                                                                                                                                  成功時に、クライアントに対する HTTP 応答で送信されたメッセージの関連付けトークンを受信場所から送信することを定義します。 このプロパティは、一方向の受信場所に対してのみ有効です。<br /><br /> **既定値:** True<br /><br /> **種類:** ブール値                                                                                                                                                                                                   |
   |                    **シングル サインオンを使う**                    |                                   エンタープライズ シングル サインオンが使用されることを示します。<br /><br /> **既定値:** False<br /><br /> **種類:** ブール**に注意してください。** このオプションが有効になっているかどうかは、するためのオプションを有効にする必要がありますも**チケットを許可**で、 **SSO システム**レベル。 **チケットを許可**オプションを構成するには、**オプション**のタブ、 **SSO システム プロパティ**ダイアログ ボックスで、 **SSOの管理**MMC インターフェイスです。 このオプションが有効になっている場合、**チケットを許可**オプション、 **SSO システム**レベルが有効になっていないし、これによって受信されるメッセージの受信場所は中断されます。                                    |
   |                 **失敗した要求を中断します。**                  |                                                                              受信処理に失敗した HTTP 要求を中断するかどうかを示します。<br /><br /> 値を False に設定すると、失敗した要求は破棄され、エラー状態コード (401 または 500) がクライアントに送信されます。<br /><br /> 失敗した要求を中断し、一方向のクライアントに「受理」状態コード (200) を送信することを示します値が True の受信ポート用にクライアント「エラー」状態コード (500) 双方向受信ポート。<br /><br /> **既定値:** False<br /><br /> **種類:** ブール値                                                                              |


7. クリックして**OK**設定を保存します。  

8. **[受信場所のプロパティ]** ダイアログ ボックスで、受信場所を構成するための適切な値を入力し、**[OK]** をクリックして設定を保存します。 **[受信場所のプロパティ]** ダイアログ ボックスの詳細については、「 [受信場所を作成する方法](../core/how-to-create-a-receive-location.md)」を参照してください。  

   HTTP クライアントが HTTP の場所を呼び出すと、HTTP アダプタでは、匿名認証、基本認証、ダイジェスト認証、または Windows 統合認証を使用して HTTP クライアントを認証します。 ユーザーが確認されると、受信ハンドラーにユーザー コンテキストが渡されます。  

> [!NOTE]
>  同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。 プロセスごとに 1 つの分離受信場所のみを指定できます。