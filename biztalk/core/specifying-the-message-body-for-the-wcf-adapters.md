---
title: WCF アダプタのメッセージ本文の指定 |Microsoft Docs
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
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32e62da213c4fceaf54773c2fe44584f43de9155
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972147"
---
# <a name="specifying-the-message-body-for-the-wcf-adapters"></a>WCF アダプタのメッセージ本文の指定
使用することができます、**メッセージ**] タブの [WCF アダプターでは、受信 SOAP メッセージから BizTalk メッセージ本文を抽出する方法を指定して、BizTalk メッセージの本文は、送信 SOAP メッセージに配置されます。  

## <a name="specifying-how-the-biztalk-message-body-is-extracted-from-an-incoming-soap-message"></a>受信 SOAP メッセージからの BizTalk メッセージ本文の抽出方法の指定  
 WCF アダプタを通じて受信する SOAP メッセージから受信 BizTalk メッセージ本文を作成する方法を制御できます。 次の図、**メッセージ**Wcf-netnamedpipe のタブでは例としてアダプタと送信アダプタが受信します。  

 ![[メッセージ] タブの wcf 受信アダプター](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")  

 ![[メッセージ] タブの wcf 送信アダプタ](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")  

 BizTalk メッセージ本文を作成する方法を指定するには、次のオプションのいずれかを選択、**受信 BizTalk メッセージ本文**上記の図でセクション。  

- **エンベロープ--全体\<Soap:envelope\>** します。 SOAP を使用して**エンベロープ**BizTalk メッセージのボディ部を作成する受信メッセージの要素。 受信メッセージ全体が BizTalk メッセージ本文になります。 このオプションは、すべてのヘッダーを組み込んで BizTalk メッセージ本文を作成する場合に使用します。  

  > [!NOTE]
  >  SOAP ヘッダーはメッセージ コンテキストに配置されますが、自動的に昇格されません。 昇格は、カスタム パイプライン コンポーネントで行うことができます。  

- **ボディ--内容\<Soap:body\>要素**します。 SOAP の内容を使用して**本文**BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。  

- **パス--本文のパスである内容を**します。 ボディ パス式を使用して、**本文のパス式**テキスト ボックスに、BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 受信メッセージにバイナリ データが含まれている場合は、BizTalk メッセージ本文にこのオプションを使用して、タグなしのバイナリ データだけを含めることができます。  

  ときに、**パス--本文のパスで見つかったコンテンツ**オプションが選択されている、**ノード エンコード**ボディ パス式で指定されたノードの予想されるエンコードの種類を指定するプロパティを構成することができます**本文のパス式**テキスト ボックス。 本文のパス式が複数の要素に一致する場合は、最初に一致した要素のみが使用されます。  

> [!NOTE]
>  **本文のパス式**プロパティ、XML の前方参照専用の処理に適した式がサポートされている XPath のみです。 このプロパティの使用可能な XPath 式の詳細についてを参照してください"、最適なの両方の世界:: を組み合わせること XPath と XmlReader" [ http://go.microsoft.com/fwlink/?LinkID=75701](http://go.microsoft.com/fwlink/?LinkID=75701)します。  

 場合、**パス--本文のパスで見つかったコンテンツ**オプションを選択して、**ノード エンコード**プロパティに設定されて**文字列**、WCF アダプタは、一致するノードは、utf-8 であるを期待文字データをエンコードします。 受信メッセージが含まれる場合などの XML 特殊文字の文字データをエスケープ\<と\>、WCF アダプターが BizTalk メッセージのボディ部を作成するときに、エスケープ文字データを復元します。 たとえば、一致するノードでは、文字データをようエスケープした**&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** WCF アダプターを作成**\<FirstName\>CONTOSO\</FirstName\>** 受信 biztalk メッセージ本文。  

 場合、**パス--本文のパスで見つかったコンテンツ**オプションを選択して、**ノード エンコード**プロパティに設定されて**16 進**または**Base64**、一致するノードが、有効なことができますが**BinHex**または**Base64**シーケンス。 一致するノードに無効なシーケンスがある場合は、WCF クライアントが受け取る**FaultException**、エラー メッセージが BizTalk Server コンピューターのイベント ログに記録し、メッセージは中断されません。  

 場合、**パス--本文のパスで見つかったコンテンツ**オプションを選択して、**ノード エンコード**プロパティに設定されて**XML**、WCF アダプタを BizTalk メッセージ本文を作成する、ボディ パス式で選択されたノードの外部の XML、**本文のパス式**テキスト ボックス。  

 指定された一致するノードとしてエンコードされたデータがない場合、**ノード エンコード**プロパティ、空の受信 BizTalk メッセージ本文が作成されます。  

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

 構成する場合、**受信 BizTalk メッセージ本文**受信 BizTalk メッセージのボディ部をセクションに次の表では、上記の受信 SOAP メッセージに示すようになります。  

|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**Envelope -- entire \<soap:Envelope\>**|なし|なし|  

 構成する場合、 **BizTalk メッセージ本文**セクションで、WCF アダプタがのみが含まれる受信 BizTalk メッセージのボディ パーツを作成して、次の表に示すように、**順序**前の要素受信 SOAP メッセージ。  

|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**ボディ--内容\<Soap:body\>要素**|なし|なし|  

 構成する場合、 **BizTalk メッセージ本文**セクション ボディ パス式に一致する受信ノードが utf-8 でエンコードされた文字データにある次の表に示すように WCF アダプタが期待されます。  

|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**パス--本文のパスでのコンテンツ**|/* [ローカル名 () = 'Order']/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']|**String**|  

 上記の受信 SOAP メッセージの WCF アダプタは、文字データを使用して**CONTOSO**の**CustomerID**受信 BizTalk メッセージのボディ部を作成する要素。  

> [!NOTE]
>  XPath の省略構文を使用することはできません **/Order/OrderDetail/CustomerID**、上記の受信 SOAP メッセージにします。 これは、XPath の省略構文は、名前空間で宣言されていないノードを返すため、 **CustomerID**で上記の SOAP メッセージ内の要素が宣言されている、 **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess**によって名前空間既定の名前空間。  

 構成する場合、 **BizTalk メッセージ本文**セクションの次の表に示すように、 **CustomID**上記の受信 SOAP メッセージ内の要素が有効な必要**BinHex**または**Base64**シーケンス。  

|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**パス--本文のパスでのコンテンツ**|/* [ローカル名 () = 'Order']/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']|**16 進**または**Base64**|  

 構成する場合、 **BizTalk メッセージ本文**セクションで、WCF アダプタが、表の後のコードに示すように、上記の受信 SOAP メッセージの受信 BizTalk メッセージ本文を作成、次の表に示すようにします。  

|受信 BizTalk メッセージ本文|本文のパス式|[ノード エンコード]|  
|----------------------------------|--------------------------|-------------------|  
|**パス--本文のパスでのコンテンツ**|/* [ローカル名 () = 'Order']/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']|**XML**|  

```  
<CustomerID xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">CONTOSO</CustomerID>   
```  

## <a name="specifying-the-source-of-the-outbound-wcf-message-body"></a>送信 WCF メッセージ本文の送信元の指定  
 WCF アダプタを通じて送信される BizTalk メッセージ本文から送信 WCF メッセージ本文を作成する方法を制御できます。 BizTalk メッセージ本文を送信 WCF メッセージ本文に配置する方法を指定する、次のオプションのいずれかを使用できます、**送信 WCF メッセージ本文**セクションで、**メッセージ**タブのように、前のセクションでの数値。  

- **ボディ--BizTalk 応答メッセージの本文**します。 BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。 送信 BizTalk メッセージ本文が、送信 SOAP メッセージの本文になります。  

- **テンプレート--テンプレートで指定されたコンテンツ**します。 指定されているテンプレートを使用して、 **XML** 、SOAP のコンテンツを作成するテキスト ボックス**本文**送信メッセージの要素。 WCF アダプターで**ボディ--BizTalk 応答メッセージ本文**(既定値) オプションは文字データやビットマップ イメージなどの XML 以外のメッセージの送信を許可していません。 使用することができます、**テンプレート--テンプレートで指定されたコンテンツ**でエンコードされた XML 以外のメッセージを送信する WCF アダプターのオプション**base64**、 **16 進**、または**文字列**.  

  ときに、**テンプレート--テンプレートで指定されたコンテンツ**オプションを選択すると、内の任意のテンプレート XML 要素を提供する必要があります、**送信 WCF メッセージ本文 - XML**テキスト ボックス。 テンプレート XML 要素は、次を含める必要があります**bts メッセージの本文**要素が 1 回だけテンプレート XML 要素が空のままにしない限り、します。  

```  
<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2010" encoding="[base64|hex|string|xml]"/>  
```  

 WCF アダプタに従い、BizTalk メッセージ本文のエンコード、**エンコード**属性を XML テンプレートとし、置換、 **bts メッセージの本文**を作成するときに、エンコードされた BizTalk メッセージ本文の要素送信 WCF メッセージ。 場合、**送信 WCF メッセージ本文 - XML**テキスト ボックスが空のまま、WCF アダプタで BizTalk メッセージ本文をエンコードする**Base64**、し、配置、 **Base64**内のシーケンス、送信 SOAP メッセージの本文。  

 場合、**エンコード**XML テンプレートの属性に設定されて**文字列**、WCF アダプターは、XML の特殊文字のなどをutf-8でエンコードされた文字データとしてのBizTalkメッセージのボディ部のエンコード\<と\>エスケープされます。  

 場合、**エンコード**XML テンプレートの属性に設定されて**base64**または**16 進**、WCF アダプターとして BizTalk メッセージのボディ部のエンコード、 **BinHex**または**Base64**シーケンス。  

 場合、**エンコード**XML テンプレートの属性に設定されて**xml**、WCF アダプターの交換、 **bts メッセージの本文**を作成する送信 BizTalk メッセージ本文の要素、送信 WCF メッセージ。  

 たとえば、WCF アダプタで、次の BizTalk メッセージのボディ部を WCF クライアントに送信する必要が生じたとします。  

```  
<ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
```  

 構成する場合、**送信 WCF メッセージ本文**セクションで、WCF アダプタが、表の後のコードに示すように、送信 WCF メッセージを作成、次の表に示すようにします。  

|送信 WCF メッセージ本文|XML|  
|-------------------------------|---------|  
|**ボディ--BizTalk 応答メッセージの本文**|なし|  

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

 構成する場合、**送信 WCF メッセージ本文**セクションで、WCF アダプタが、表の後のコードに示すように、送信 WCF メッセージを作成、次の表に示すようにします。  


|         送信 WCF メッセージ本文         |                                                                    XML                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| **ボディ--BizTalk 応答メッセージの本文** | \<書籍\><br /><br /> \<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**string**"/\><br /><br /> \</Book\> |

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

 構成する場合、**送信 WCF メッセージ本文**セクションで、WCF アダプタが、表の後のコードに示すように、送信 WCF メッセージを作成、次の表に示すようにします。  


|         送信 WCF メッセージ本文         |                                                                    XML                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| **ボディ--BizTalk 応答メッセージの本文** | \<書籍\><br /><br /> \<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**base64**"/\><br /><br /> \</Book\> |

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

 構成する場合、**送信 WCF メッセージ本文**セクションで、WCF アダプタが、表の後のコードに示すように、送信 WCF メッセージを作成、次の表に示すようにします。  


|         送信 WCF メッセージ本文         |                                                                  XML                                                                   |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **ボディ--BizTalk 応答メッセージの本文** | \<書籍\><br /><br /> \<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**xml**"/\><br /><br /> \</Book\> |

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