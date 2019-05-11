---
title: オーケストレーションで SOAP ヘッダーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, properties
- Web services, SOAP headers
- orchestrations, SOAP headers
- creating, SOAP headers
ms.assetid: 4754dd23-386b-4093-8ea4-4da6b4d9279c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce21530c975356b811378f437cddaf8eb64612d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321768"
---
# <a name="using-soap-headers-in-orchestrations"></a>オーケストレーションで SOAP ヘッダーの使用
オーケストレーションでは、プロパティ スキーマを使用して、SOAP ヘッダー コンテキスト プロパティを定義します。 SOAP ヘッダー コンテキスト プロパティを設定するのにには、BizTalk エディターを使用します。  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a>プロパティ スキーマを使用した SOAP ヘッダー コンテキスト プロパティを定義します。  
 プロパティ スキーマをオーケストレーションで定義済みの SOAP ヘッダー コンテキスト プロパティを使用する必要があります。 プロパティ スキーマのターゲットの名前空間をいる必要があります**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**、および**Property Schema Base**プロパティに設定**MessageContextPropertyBase**します。 プロパティ スキーマ内の各ルート要素名は、定義済みの SOAP ヘッダー内のルート要素名と一致する必要があります。 プロパティ スキーマおよびプロパティ名の名前空間を使用して、コンテキスト プロパティの値を設定できます。  
  
> [!NOTE]
>  プロパティ スキーマの名前空間は、ターゲット スキーマの名前空間と異なる (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**)。 名前空間は、任意の文字列。ただし、通常、プロジェクトの名前を既定になります。  
  
 次のコードは、プロパティ スキーマ名前空間は、SOAP ヘッダー コンテキスト プロパティを割り当てる**SOAPHeader**プロパティ名を持つ**OrigDest**:  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 プロパティ スキーマおよびコンテキスト プロパティの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)します。  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a>BizTalk エディターを使用して、SOAP ヘッダー コンテキスト プロパティを設定するには  
 オーケストレーションで SOAP ヘッダー コンテキスト プロパティは、XML データを含む文字列に設定されます。 BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形。  
  
 次の例は、コンテキスト プロパティを設定する文字列を示しています。  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a>BizTalk エディターを使用して、SOAP ヘッダー ルート要素のインスタンスを作成するには  
 SOAP ヘッダーを正しい文字列に設定すると、困難なことができます。 BizTalk プロジェクトに Web 参照を追加するには、すべての複合 Web メッセージ部分は、ルート要素として Reference.xsd に追加されます。 Reference.xsd には、各定義済みの SOAP ヘッダーのルート要素も含まれています。 SOAP ヘッダーを正しい文字列を設定するためには、BizTalk エディターを使用して Reference.xsd の SOAP ヘッダー ルート要素のインスタンスを作成する必要があります。 実際のデータを格納するのに、生成されたインスタンス データを直接またはインスタンス データを使用できます。  
  
 BizTalk エディターを使用してインスタンス データを生成する方法の詳細については、次を参照してください。[インスタンス メッセージの生成方法](../core/how-to-generate-instance-messages.md)します。  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>コンテキスト プロパティを設定する XmlDocument の作成  
 コンテキスト プロパティを設定するには、作成を**XmlDocument**との文字列値を書き込み、 **XmlDocument**をコンテキスト プロパティ。 型の変数を宣言する**XMLDocument**し、XML データを割り当てます。  
  
 次の例では、宣言型の変数を設定**XMLDocument**し、XML データを割り当てます。  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 次の例では、コンテキスト プロパティの設定を示しています。  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)します。 .NET クラスを呼び出すことの詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
## <a name="creating-soap-headers-for-a-soap-request"></a>SOAP 要求の SOAP ヘッダーを作成します。  
 SOAP 要求の SOAP ヘッダーを作成するときに、SOAP ヘッダーを正しく作成されていることを確認する必要があります。 SOAP アダプターでは、SOAP ヘッダー コンテキスト プロパティの内容を検証しません。  
  
> [!NOTE]
>  SOAP ヘッダーが正しくない場合、BizTalk は、Web サービスに SOAP 要求を送信することはできません。  
  
 BizTalk を返す Web サービスに SOAP 応答は、SOAP ヘッダーを含めることもできます。 定義済みの SOAP ヘッダーがある場合は、これらの SOAP ヘッダーのみアクセスできます。  
  
> [!NOTE]
>  消費済み Web サービスのサポートは、SOAP ヘッダーを定義するだけです。  
  
 定義済みの SOAP ヘッダーの詳細については、次を参照してください。[を使用して SOAP ヘッダー](../core/using-soap-headers.md)します。 応答 SOAP ヘッダーは、要求 SOAP ヘッダーと同じ構文を使用するコンテキスト プロパティに設定されます。  
  
 次のコードでは、応答 SOAP ヘッダーにアクセスする方法を示します。  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 コンテキスト プロパティに含まれる値は、XML データを含む文字列です。 BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形。 内の文字列を読み込み、 **XmlDocument** XPath クエリを使用して、特定のフィールドにアクセスするとします。  
  
 BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [xlang-s 言語](../core/xlang-s-language.md)します。  
  
## <a name="see-also"></a>参照  
 [Xlang-s 言語](../core/xlang-s-language.md)   
 [使用する Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md)