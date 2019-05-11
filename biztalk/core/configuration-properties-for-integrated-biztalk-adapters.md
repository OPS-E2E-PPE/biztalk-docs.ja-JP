---
title: 統合 BizTalk アダプターの構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- adapters, passwords
- IReceiveLocation.CustomData property
- security, passwords
- ISendPort.CustomData property
- binding files, passwords
- adapters, properties
- binding files, security
ms.assetid: 4780a558-4322-428a-aa4a-0c32913faded
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eac9263364bc4342fd2bdbcd484e9aa150deb82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391486"
---
# <a name="configuration-properties-for-integrated-biztalk-adapters"></a>統合 BizTalk アダプターの構成プロパティ
BizTalk エクスプローラ オブジェクト モデルを公開、 **IReceiveLocation.CustomData**と**ISendPort.CustomData**名前/値の形式でアダプター構成プロパティ バッグを含むプロパティ組の XML 文字列。 この名前/値ペアの XML 文字列が格納されている、 \<CustomProps\>内の要素を\<TransportTypeData\>バインド ファイル内の要素。 ほとんどの情報の\<CustomProps\>要素は、アダプターの BizTalk Server のユーザー インターフェイス (など、BizTalk 管理コンソールまたは BizTalk エクスプ ローラー) に設定できる情報に対応します。 適用されるこれらの値がバインド ファイルに存在する場合は、指定したアダプターの構成を受信場所と、送信ポートのバインド ファイルのインポート時に。 すべてのアダプターの構成情報は、シングル サインオン データベースに格納されます。  
  
 このセクションでは、各統合 BizTalk アダプターを設定できる構成プロパティについて説明します。  
  
> [!NOTE]
>  パスワードの情報に格納されている、 \<TransportTypeData\>バインド ファイルの要素をマスクする機微なデータがクリア テキストで保存しないようにします。 トランスポートに応じて、パスワードの情報は NULL に置き換えられますかまたはアスタリスクに置き換えられます。 この情報は、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前にアダプター構成を更新するバインド ファイルに手動で入力する必要があります。  
  
 アダプター フレームワークを使用して構築されたアダプターの構成データが格納されている、 \<AdapterConfig\>要素。 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データ型、 **\< \>** この要素に含まれる文字をエスケープする必要がありますまたはエラーが発生時にします。バインド ファイルをインポートしようとしてください。 これにより、テキストは小さい値を指定する構成データを人間がこれらの文字をエスケープしない場合よりも読みやすくします。 次の例を POP3 アダプターにバインドされた送信ポートのサンプル構成データからこれらの文字をエスケープする効果を示しています。  
  
 **TransportTypeData 構成データで使用される <> 文字をエスケープしませんが、 \<AdapterConfig\>要素**  
  
 この構成データが無効ですので、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データ型と\<\>に含まれる文字、 \<AdapterConfig\>要素はエスケープされません。  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<mailServer>test.microsoft.com</mailServer>  
<serverPort>0</serverPort>  
<userName>testuser</userName>  
<password>******</password>  
<authenticationScheme>Basic</authenticationScheme>  
<sslRequired>false</sslRequired>  
<applyMIME>true</applyMIME>  
<bodyPartContentType>text/xml</bodyPartContentType>  
<bodyPartIndex>1</bodyPartIndex>  
<errorThreshold>10</errorThreshold>  
<pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure>   
<uri>POP3://test.microsoft.com#testuser</uri>  
</Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 **使用される <> 文字がエスケープされる TransportTypeData 構成データ、 \<AdapterConfig\>要素**  
  
 以降、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データ型、 \< \>から文字をエスケープする必要があります、 \<AdapterConfig\>要素を次に示すように。  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test  
microsoft.com</mailServer><serverPort>0</serverPort>&  
lt;userName>testuser</userName><password>******</pass  
word><authenticationScheme>Basic</authenticationScheme>&  
lt;sslRequired>false</sslRequired><applyMIME>true</ap  
plyMIME><bodyPartContentType>text/xml</bodyPartContentType&  
gt;<bodyPartIndex>1</bodyPartIndex><errorThreshold>10  
</errorThreshold><pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri  
>POP3://test.microsoft.com#testuser</uri></Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 アダプター フレームワークで作成された統合アダプターを以下に示します。  
  
- FTP アダプター  
  
- MQSeries アダプター  
  
- MSMQ アダプター  
  
- POP3 アダプター  
  
- Windows Sharepoint Services アダプター  
  
  各統合アダプターの TransportTypeData 構成データとして使用するサンプル文字列を表示するには、このセクションでは、アダプターに関連付けられている構成プロパティのトピックを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [構成プロパティの変数の型](../core/configuration-property-variable-types.md)  
  
 [ファイル アダプター構成プロパティ](../core/file-adapter-configuration-properties.md)  
  
 [FTP アダプター構成プロパティ](../core/ftp-adapter-configuration-properties.md)  
  
 [HTTP アダプター構成プロパティ](../core/http-adapter-configuration-properties.md)  
  
 [MQSeries アダプター構成プロパティ](../core/mqseries-adapter-configuration-properties.md)  
  
 [MSMQ アダプター構成プロパティ](../core/msmq-adapter-configuration-properties.md)  
  
 [POP3 アダプター構成プロパティ](../core/pop3-adapter-configuration-properties.md)  
  
 [SMTP アダプター構成プロパティ](../core/smtp-adapter-configuration-properties.md)  
  
 [SOAP アダプター構成プロパティ](../core/soap-adapter-configuration-properties.md)  
  
 [Windows SharePoint Services アダプターの構成プロパティ](../core/windows-sharepoint-services-adapter-configuration-properties.md)