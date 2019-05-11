---
title: オーケストレーションで SOAP ヘッダーへのアクセス |Microsoft Docs
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
ms.openlocfilehash: 01260e95c6e4bb1676c2bca589660e21812f2d9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361931"
---
# <a name="accessing-soap-headers-in-orchestrations"></a>オーケストレーションで SOAP ヘッダーへのアクセス
定義されていると、不明な SOAP ヘッダーのオーケストレーションで SOAP ヘッダー コンテキスト プロパティにアクセスすることができます。 プロパティ スキーマおよびコンテキスト プロパティの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)します。  
  
## <a name="defined-soap-header-context-properties"></a>定義済みの SOAP ヘッダー コンテキスト プロパティ  
 オーケストレーションで定義されている SOAP ヘッダー コンテキスト プロパティには、プロパティ スキーマが必要です。 プロパティ スキーマは、ターゲットの名前空間をいる必要があります**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**、および**Property Schema Base**プロパティに設定**MessageContextPropertyBase**します。 プロパティ スキーマ内の各ルート要素名は、定義済みの SOAP ヘッダーのルート要素名と一致する必要があります。 プロパティ スキーマおよびプロパティ名の名前空間を使用して、コンテキスト プロパティの値を表示できます。 プロパティ スキーマの名前空間は、上に示したターゲットの名前空間と異なります。 プロパティ スキーマの名前空間には、任意の文字列できますが、通常、プロジェクトの名前を既定になります。  
  
 次の例は、プロパティ スキーマの名前空間、SOAP ヘッダー コンテキスト プロパティにアクセスする**SOAPHeader**、およびプロパティ名**OrigDest**:  
  
```  
stringVar = requestMessageInstance(SOAPHeader.OrigDest);  
```  
  
> [!NOTE]
>  定義済みの SOAP ヘッダーは、"in"または"out"ヘッダーに扱われます。 ウィザードでは、要求と応答メッセージの同じ SOAP ヘッダーが定義されている場合、ウィザードでは、応答の受信値は自動的に返されません。 応答メッセージの SOAP ヘッダー コンテキスト プロパティに要求メッセージの SOAP ヘッダー コンテキスト プロパティに明示的にコピーする必要があります。  
  
## <a name="copying-soap-header-context-property-of-incoming-message"></a>受信メッセージの SOAP ヘッダー コンテキスト プロパティのコピー  
 応答メッセージの同じ SOAP ヘッダー コンテキスト プロパティには、受信メッセージの SOAP ヘッダー コンテキスト プロパティをコピーできます。  
  
 次の例では、SOAP ヘッダー コンテキスト プロパティのコピーを示しています。  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = RequestMessageInstance(SOAPHeader.OrigDest);  
```  
  
 SOAP 応答の SOAP ヘッダーを作成するときに、SOAP ヘッダーを正しく作成することを確認します。 SOAP アダプターでは、SOAP ヘッダー コンテキスト プロパティの内容を検証しません。 応答 SOAP ヘッダーの値が正しくない場合、SOAP アダプターは、Web サービスのコンシューマーに応答メッセージを送信することはできません。  
  
## <a name="unknown-soap-header-context-property"></a>不明な SOAP ヘッダー コンテキスト プロパティ  
 不明な SOAP ヘッダー コンテキスト プロパティでは、プロパティ スキーマは必要ありません。 このグローバル コンテキスト プロパティにアクセスすることができます**SOAP します。UnknownHeaders**します。  
  
 次の例は、不明な SOAP ヘッダー コンテキスト プロパティにアクセスする**SOAP します。UnknownHeaders**:  
  
```  
stringVar = RequestMessageInstance(SOAP.UnknownHeaders);  
```  
  
 コンテキスト プロパティに含まれる値は、XML データを含む文字列です。 このデータにアクセスする最も簡単な方法は、BizTalk 式エディターを使用する、**メッセージの割り当て**または**式**図形および内の文字列を読み込み、 **XmlDocument**および使用特定のフィールドにアクセスする XPATH クエリです。 BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [xlang-s 言語](../core/xlang-s-language.md)します。  
  
 コンテキスト プロパティは、特定のメッセージに関連付けられます。 メッセージング エンジンは、応答メッセージに要求メッセージからの既知の SOAP ヘッダーの値を自動的にマップしません。 Web サービスの応答メッセージを作成するときに具体的には、SOAP ヘッダーの値を設定する必要があります。 次のコマンドは、SOAP ヘッダー コンテキスト プロパティの設定の最も簡単なメソッドを示します。  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = "<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination xmlns=\"\">Home</Origination><Destination xmlns=\"\">Work</Destination> </OrigDest>"  
```  
  
 作成してこれも実現できる、 **XmlDocument**の文字列値の書き込みと、 **XmlDocument**をコンテキスト プロパティ。  
  
> [!NOTE]
>  場合、 **SOAP します。UnknownHeaders**プロパティが null で、BizTalk は自動的に SOAP 要求を SOAP 応答で受信した不明なヘッダーを返します。 場合、 **SOAP します。UnknownHeaders**応答メッセージのコンテキスト プロパティが null でないし、BizTalk は、SOAP 応答にその値を返します。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスでの SOAP ヘッダー](../core/soap-headers-with-published-web-services.md)