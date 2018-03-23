---
title: WCF アダプタのメッセージ本文の指定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, SOAP messages
- messages, WCF adapters
- WCF adapters, message bodies
- SOAP messages, WCF adapters
ms.assetid: b20364b7-0365-4636-b4d6-bde9c69b8dcb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109ad486baa542aff3cd1c4a44804ff2fd79aac5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="specifying-the-message-body-for-the-wcf-adapters"></a>WCF アダプタのメッセージ本文の指定
使用することができます、 **メッセージ** ] タブの [WCF アダプターでは、受信 SOAP メッセージから BizTalk メッセージ本文を抽出する方法を指定して、BizTalk メッセージの本文は、送信 SOAP メッセージに配置されます。  
  
## <a name="specifying-how-the-biztalk-message-body-is-extracted-from-an-incoming-soap-message"></a>受信 SOAP メッセージからの BizTalk メッセージ本文の抽出方法の指定  
 WCF アダプタを通じて受信する SOAP メッセージから受信 BizTalk メッセージ本文を作成する方法を制御できます。 次の図、 **メッセージ** Wcf-netnamedpipe のタブでは例としてアダプターと送信アダプターが受信します。  
  
 ![[メッセージ] タブ、WCF 受信アダプター](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")  
  
 ![[メッセージ] タブ、WCF 送信アダプタ](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")  
  
 BizTalk メッセージ本文を作成する方法を指定するには、次のオプションのいずれかを選択、 **受信 BizTalk メッセージ本文** 」セクションを上記の図。  
  
-   **-エンベロープ\<Soap:envelope\>**です。 SOAP を使用して **エンベロープ** を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 受信メッセージ全体が BizTalk メッセージ本文になります。 このオプションは、すべてのヘッダーを組み込んで BizTalk メッセージ本文を作成する場合に使用します。  
  
    > [!NOTE]
    >  SOAP ヘッダーはメッセージ コンテキストに配置されますが、自動的に昇格されません。 昇格は、カスタム パイプライン コンポーネントで行うことができます。  
  
-   **本文--内容\<Soap:body\>要素**です。 SOAP の内容を使用して **本文** を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。  
  
-   **パス--本文のパスである内容**します。 ボディ パス式を使用して、 **本文のパス式** BizTalk メッセージのボディ部を作成するテキスト ボックスです。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 受信メッセージにバイナリ データが含まれている場合は、BizTalk メッセージ本文にこのオプションを使用して、タグなしのバイナリ データだけを含めることができます。  
  
 ときに、 **パス--本文のパスで見つかったコンテンツ** オプションが選択されて、 **ノード エンコード** ボディ パス式で指定したノードの予想されるエンコードの種類を指定するプロパティを構成することができます、 **本文のパス式** テキスト ボックスです。 本文のパス式が複数の要素に一致する場合は、最初に一致した要素のみが使用されます。  
  
> [!NOTE]
>  **本文のパス式** プロパティには、XML の前方参照専用の処理に適した式がサポートされている XPath のみです。 このプロパティの使用可能な XPath 式の詳細についてを参照してください"ベストの両方長所:: 結合 XPath で、XmlReader" [ http://go.microsoft.com/fwlink/?LinkID=75701](http://go.microsoft.com/fwlink/?LinkID=75701)です。  
  
 場合、 **パス--本文のパスで見つかったコンテンツ** オプションを選択して **ノード エンコード** プロパティに設定されて **文字列**, 、WCF アダプタは、utf-8 でエンコードされた文字データが一致したノードにあるを期待します。 受信メッセージが含まれる場合など、XML の特殊文字の文字データをエスケープ\<と\>、WCF アダプターが BizTalk メッセージのボディ部を作成するときに、エスケープ文字データを復元します。 たとえば、一致するノードが文字データをようにエスケープ**&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** 、WCF アダプタ作成**\<FirstName\>CONTOSO\</FirstName\>**受信 biztalk メッセージ本文。  
  
 場合、 **パス--本文のパスで見つかったコンテンツ** オプションを選択して、 **ノード エンコード** プロパティに設定されて **16 進数** または **Base64**, 、一致するノードが、有効なことができますが **BinHex** または **Base64** シーケンスです。 一致するノードに無効なシーケンスがある場合は、WCF クライアントが受け取る **FaultException**, 、エラー メッセージは、BizTalk Server コンピューターのイベント ログに記録、およびメッセージは中断されません。  
  
 場合、 **パス--本文のパスで見つかったコンテンツ** オプションを選択して、 **ノード エンコード** にプロパティが設定されている **XML**, 、ボディ パス式で選択されたノードの外部の XML で、WCF アダプタが BizTalk メッセージ本文を作成、 **本文のパス式** テキスト ボックスです。  
  
 指定された一致するノードとしてエンコードされたデータがない場合、 **ノード エンコード** プロパティには、空の受信 BizTalk メッセージ本文を作成します。  
  
 たとえば、WCF 送信アダプタが WCF クライアントから次の SOAP メッセージを受信したとします。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/OrderRefresh</a:Action>   
    <a:MessageID>urn:uuid:59e74507-66d0-4d50-be70-c3ec248b6f78</a:MessageID>   
    <a:ReplyTo>  
       <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>   
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>   
  </s:Header>  
  <s:Body>  
    <Order xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
     <OrderDetail>  
       <CustomerID>CONTOSO</CustomerID>   
       <OrderID>00000000</OrderID>   
     </OrderDetail>  
    </Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 構成する場合、 **受信 BizTalk メッセージ本文** セクションの次の表では、上記の受信 SOAP メッセージに示すように受信 BizTalk メッセージのボディ部になります。  
  
|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**Envelope -- entire \<soap:Envelope\>**|なし|なし|  
  
 構成する場合、 **BizTalk メッセージ本文** セクションで、WCF アダプタがのみが含まれる受信 BizTalk メッセージのボディ部を作成して、次の表に示すように、 **順序** 上記の受信 SOAP メッセージ内の要素。  
  
|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**本文--内容\<Soap:body\>要素**|なし|なし|  
  
 構成する場合、 **BizTalk メッセージ本文** セクションで、WCF アダプタにボディ パス式に一致する受信ノードが utf-8 でエンコードされた文字データを持つことが予想される次の表に示すようにします。  
  
|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**本文のパスで見つかったパス--コンテンツ**|/* [ローカル名 () ="Order"]/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']|**文字列**|  
  
 WCF アダプターは、上記の受信 SOAP メッセージの文字データを使用して **CONTOSO**, の **CustomerID** 受信 BizTalk メッセージのボディ部を作成する要素。  
  
> [!NOTE]
>  XPath の省略構文を使用することはできません **/Order/OrderDetail/CustomerID**, 、上記の受信 SOAP メッセージにします。 これは、XPath の省略構文には、名前空間で宣言されていないノードが返されるため、 **CustomerID** で上記の SOAP メッセージ内の要素が宣言されている、 **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess** 既定の名前空間では名前空間。  
  
 構成する場合、 **BizTalk メッセージ本文** セクションの次の表に示すように、 **CustomID** 上記の受信 SOAP メッセージ内の要素が有効な必要 **BinHex** または **Base64** シーケンスです。  
  
|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**本文のパスで見つかったパス--コンテンツ**|/* [ローカル名 () ="Order"]/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']|**16 進** または **Base64**|  
  
 構成する場合、 **BizTalk メッセージ本文** セクションで、表の後に、コードに示すように、WCF アダプタが上記の受信 SOAP メッセージの受信 BizTalk メッセージ本文を作成、次の表に示すようにします。  
  
|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**本文のパスで見つかったパス--コンテンツ**|/* [ローカル名 () ="Order"]/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']|**XML**|  
  
```  
<CustomerID xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">CONTOSO</CustomerID>   
```  
  
## <a name="specifying-the-source-of-the-outbound-wcf-message-body"></a>送信 WCF メッセージ本文の送信元の指定  
 WCF アダプタを通じて送信される BizTalk メッセージ本文から送信 WCF メッセージ本文を作成する方法を制御できます。 BizTalk メッセージ本文を送信 WCF メッセージ本文に配置する方法を指定する、次のオプションのいずれかを使用ことができます、 **送信 WCF メッセージ本文** セクションで、 **メッセージ**  タブの前のセクションでの図に示すようにします。  
  
-   **ボディ--BizTalk 応答メッセージの本文**します。 BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する **本文** 、送信メッセージの要素。 送信 BizTalk メッセージ本文が、送信 SOAP メッセージの本文になります。  
  
-   **テンプレート--テンプレートで指定されたコンテンツ**します。 提供されているテンプレートを使用して、 **XML** 、SOAP のコンテンツを作成するテキスト ボックス **本文** 、送信メッセージの要素。 WCF アダプターで **ボディ--BizTalk 応答メッセージの本文** (既定値) オプション文字データやビットマップ イメージなどの XML 以外のメッセージを送信することはできます。 使用することができます、 **テンプレート--テンプレートで指定されたコンテンツ** WCF アダプターでエンコードされた XML 以外のメッセージを送信するためのオプション **base64**, 、**16 進**, 、または **文字列**します。  
  
 ときに、 **テンプレート--テンプレートで指定されたコンテンツ** オプションが選択されている場合、内の任意のテンプレート XML 要素を指定する必要があります、 **送信 WCF メッセージ本文 - XML** テキスト ボックスです。 テンプレートの XML 要素は、次を含める必要があります **bts メッセージ本文** 要素が 1 回だけテンプレート XML 要素は空のままにしない限り。  
  
```  
<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2010" encoding="[base64|hex|string|xml]"/>  
```  
  
 WCF アダプタは」の手順に従って BizTalk メッセージ本文をエンコード、 **エンコーディング** 属性の XML テンプレートとし、置換、 **bts メッセージ本文** 送信 WCF メッセージを作成するときに、エンコードされた BizTalk メッセージ本文を持つ要素。 場合、 **送信 WCF メッセージ本文 - XML** テキスト ボックスが空のまま、WCF アダプターが BizTalk メッセージ本文をエンコード **Base64**, 、し、配置、 **Base64** 送信 SOAP メッセージの本文内のシーケンス。  
  
 場合、**エンコード**XML テンプレート内の属性に設定されている**文字列**、WCF アダプターは、XML の特殊文字のなどをutf-8でエンコードされた文字データとしてのBizTalkメッセージのボディ部のエンコード\<と\>エスケープされます。  
  
 場合、 **エンコーディング** に XML テンプレート内の属性が設定されている **base64** または **16 進**, 、WCF アダプターとして BizTalk メッセージのボディ部のエンコード、 **BinHex** または **Base64** シーケンスです。  
  
 場合、 **エンコーディング** に XML テンプレート内の属性が設定されている **xml**, 、WCF アダプタの交換、 **bts メッセージ本文** 送信 WCF メッセージを作成する送信 BizTalk メッセージ本文を持つ要素。  
  
 たとえば、WCF アダプタで、次の BizTalk メッセージのボディ部を WCF クライアントに送信する必要が生じたとします。  
  
```  
<ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
```  
  
 構成する場合、 **送信 WCF メッセージ本文** セクションで、表の後に、コードに示すように、WCF アダプタが送信 WCF メッセージを作成、次の表に示すようにします。  
  
|送信 WCF メッセージ本文|XML|  
|-------------------------------|---------|  
|**ボディ--BizTalk 応答メッセージ本文**|なし|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:6a706a54-c4f5-4767-909d-a992c7c26dba</a:MessageID>  
    <a:ReplyTo>  
<a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 構成する場合、 **送信 WCF メッセージ本文** セクションで、表の後に、コードに示すように、WCF アダプタが送信 WCF メッセージを作成、次の表に示すようにします。  
  
|送信 WCF メッセージ本文|XML|  
|-------------------------------|---------|  
|**ボディ--BizTalk 応答メッセージ本文**|\<書籍\><br /><br /> \<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**string**"/\><br /><br /> \</Book\>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:05dde292-eedd-467e-b0d2-f1b8f0757410</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <Book><ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  <ns0:OrderDetail>    <ns0:CustomerID>CONTOSO</ns0:CustomerID>    <ns0:OrderID> 01A2c</ns0:OrderID>  </ns0:OrderDetail></ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```  
  
 構成する場合、 **送信 WCF メッセージ本文** セクションで、表の後に、コードに示すように、WCF アダプタが送信 WCF メッセージを作成、次の表に示すようにします。  
  
|送信 WCF メッセージ本文|XML|  
|-------------------------------|---------|  
|**ボディ--BizTalk 応答メッセージ本文**|\<書籍\><br /><br /> \<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**base64**"/\><br /><br /> \</Book\>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://ww  
w.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe  
/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:cb3cac6d-a542-4a90-bad8-cdbfa8251112</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessSer  
vice</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>77u/PG5zMDpPcmRlciB4bWxuczpuczA9Imh0dHA6Ly9NaWNyb3NvZnQuU2FtcGxlcy5CaX  
pUYWxrLk5ldE5hbWVkUGlwZS9PcmRlclByb2Nlc3MiPg0KICA8bnMwOk9yZGVyRGV0YWlsPg0KICAgID  
xuczA6Q3VzdG9tZXJJRD5DT05UT1NPPC9uczA6Q3VzdG9tZXJJRD4NCiAgICA8bnMwOk9yZGVySUQ+MD  
FBMmM8L25zMDpPcmRlcklEPg0KICA8L25zMDpPcmRlckRldGFpbD4NCjwvbnMwOk9yZGVyPg==</Book  
>  
  </s:Body>  
</s:Envelope>  
```  
  
 構成する場合、 **送信 WCF メッセージ本文** セクションで、表の後に、コードに示すように、WCF アダプタが送信 WCF メッセージを作成、次の表に示すようにします。  
  
|送信 WCF メッセージ本文|XML|  
|-------------------------------|---------|  
|**ボディ--BizTalk 応答メッセージ本文**|\<書籍\><br /><br /> \<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**xml**"/\><br /><br /> \</Book\>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:A  
ction>  
    <a:MessageID>{513C123C-0600-4A1C-BEE2-EF83E0EFEB15}</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>  
      <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CustomerID_0</ns0:CustomerID>  
    <ns0:OrderID>OrderID_0</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```