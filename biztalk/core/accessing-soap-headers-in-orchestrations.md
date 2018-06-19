---
title: オーケストレーションで SOAP ヘッダーへのアクセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, properties
- orchestrations, SOAP headers
ms.assetid: 91fe053a-3f16-497c-b4bb-5fb54bec62e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 516b2bcc57bef507a028f30c61fd329a5fd7a598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225922"
---
# <a name="accessing-soap-headers-in-orchestrations"></a>オーケストレーションで SOAP ヘッダーへのアクセス
定義されている SOAP ヘッダーと不明な SOAP ヘッダーに関して、オーケストレーション内の SOAP ヘッダー コンテキスト プロパティにアクセスできます。 プロパティ スキーマおよびコンテキスト プロパティの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)です。  
  
## <a name="defined-soap-header-context-properties"></a>定義されている SOAP ヘッダー コンテキスト プロパティ  
 オーケストレーションで定義済み SOAP ヘッダー コンテキスト プロパティでは、プロパティ スキーマが必要です。 プロパティ スキーマは、ターゲットの名前空間を持つ必要があります**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**、および**Property Schema Base**プロパティに設定**MessageContextPropertyBase**です。 各ルート要素名、プロパティ スキーマでは、定義済み SOAP ヘッダーのルート要素名と一致する必要があります。 プロパティ スキーマおよびプロパティ名の名前空間を使用して、コンテキスト プロパティの値を表示できます。 プロパティ スキーマの名前空間は、上に示したターゲットの名前空間と異なります。 プロパティ スキーマの名前空間には、任意の文字列できますが、通常、プロジェクトの名前を既定になります。  
  
 次の例は、プロパティ スキーマ名前空間では、SOAP ヘッダー コンテキスト プロパティにアクセスする**SOAPHeader**、およびプロパティ名**OrigDest**:  
  
```  
stringVar = requestMessageInstance(SOAPHeader.OrigDest);  
```  
  
> [!NOTE]
>  定義されている SOAP ヘッダーは、"in" または "out" ヘッダーとして取り扱われます。 ウィザードで要求メッセージと応答メッセージに同じ SOAP ヘッダーが定義された場合、応答には受信値は自動的に返されません。 要求メッセージの SOAP ヘッダー コンテキスト プロパティを応答メッセージの SOAP ヘッダー コンテキスト プロパティに明示的にコピーする必要があります。  
  
## <a name="copying-soap-header-context-property-of-incoming-message"></a>受信メッセージの SOAP ヘッダー コンテキスト プロパティのコピー  
 受信メッセージの SOAP ヘッダー コンテキスト プロパティは、応答メッセージの同じ SOAP ヘッダー コンテキスト プロパティにコピーできます。  
  
 次の例は、SOAP ヘッダー コンテキスト プロパティのコピーを示します。  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = RequestMessageInstance(SOAPHeader.OrigDest);  
```  
  
 SOAP 応答の SOAP ヘッダーを作成するときは、SOAP ヘッダーを正しく作成する必要があります。 SOAP アダプタでは SOAP ヘッダー コンテキスト プロパティの内容を検証しません。 応答 SOAP ヘッダーの値が誤っていた場合、SOAP アダプタでは Web サービスのコンシューマに応答メッセージを送信できません。  
  
## <a name="unknown-soap-header-context-property"></a>不明な SOAP ヘッダー コンテキスト プロパティ  
 不明な SOAP ヘッダー コンテキスト プロパティにはプロパティ スキーマは必要ありません。 このグローバル コンテキスト プロパティにアクセスすることができます**SOAP です。UnknownHeaders**です。  
  
 次の例は、不明な SOAP ヘッダー コンテキスト プロパティにアクセスする**SOAP です。UnknownHeaders**:  
  
```  
stringVar = RequestMessageInstance(SOAP.UnknownHeaders);  
```  
  
 コンテキスト プロパティに含まれている値は、XML データを含む文字列です。 このデータにアクセスする最も簡単な方法で BizTalk 式エディタを使用する、**メッセージの割り当て**または**式**図形および内の文字列を読み込み、 **XmlDocument**および使用特定のフィールドにアクセスする XPATH クエリです。 BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [XLANG-s 言語](../core/xlang-s-language.md)します。  
  
 コンテキスト プロパティは、特定のメッセージに関連付けられています。 メッセージング エンジンでは、応答メッセージに要求メッセージからの既知の SOAP ヘッダーの値は自動的にマップしません。 Web サービスの応答メッセージを作成する場合は、SOAP ヘッダーの値を明示的に設定する必要があります。 次のコマンドは、SOAP ヘッダー コンテキスト プロパティの設定の最も単純なメソッドを示します。  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = "<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination xmlns=\"\">Home</Origination><Destination xmlns=\"\">Work</Destination> </OrigDest>"  
```  
  
 これを実現する作成することで、 **XmlDocument**と書き込みの文字列値、 **XmlDocument**をコンテキスト プロパティです。  
  
> [!NOTE]
>  場合、 **SOAP です。UnknownHeaders**プロパティが null で、BizTalk が自動的に SOAP 要求を SOAP 応答で受信した不明なヘッダーを返します。 場合、 **SOAP です。UnknownHeaders**応答メッセージのコンテキスト プロパティが null でないし、BizTalk は、SOAP 応答にその値を返します。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスでの SOAP ヘッダー](../core/soap-headers-with-published-web-services.md)