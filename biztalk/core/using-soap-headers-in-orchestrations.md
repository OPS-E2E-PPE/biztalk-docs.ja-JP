---
title: オーケストレーションで SOAP ヘッダーの使用 |Microsoft ドキュメント
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
ms.openlocfilehash: faae7013c824926adea67feab296e1993f93e326
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288538"
---
# <a name="using-soap-headers-in-orchestrations"></a>オーケストレーションで SOAP ヘッダーの使用
オーケストレーションは、プロパティ スキーマを使用して SOAP ヘッダー コンテキスト プロパティを定義します。 SOAP ヘッダー コンテキスト プロパティを設定するのにには、BizTalk エディターを使用します。  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a>プロパティ スキーマを使用した SOAP ヘッダー コンテキスト プロパティの定義  
 オーケストレーション内に定義されている SOAP ヘッダー コンテキスト プロパティを使用するには、プロパティ スキーマが必要です。 プロパティ スキーマのターゲットの名前空間を持つ必要があります**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**、および**Property Schema Base**プロパティに設定**MessageContextPropertyBase**です。 プロパティ スキーマ内の各ルート要素名は、定義されている SOAP ヘッダーのルート要素名に一致する必要があります。 これにより、プロパティ スキーマの名前空間とプロパティ名を使用してコンテキスト プロパティの値を設定できます。  
  
> [!NOTE]
>  プロパティ スキーマの名前空間は、ターゲット スキーマの名前空間と異なる (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**)。 名前空間には任意の文字列を指定できますが、通常は既定によりプロジェクト名が使用されます。  
  
 次のコードは、プロパティ スキーマの名前空間がここでは、SOAP ヘッダー コンテキスト プロパティを割り当てる**SOAPHeader**というプロパティ名を持つ**OrigDest**:  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 プロパティ スキーマおよびコンテキスト プロパティの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)です。  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a>BizTalk エディタでの SOAP ヘッダー コンテキスト プロパティの設定  
 オーケストレーションでは、SOAP ヘッダーのコンテキスト プロパティは、XML データを含む文字列に設定されます。 BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形です。  
  
 次の例は、コンテキスト プロパティを設定する文字列を示しています。  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a>BizTalk エディタでの SOAP ヘッダー ルート要素のインスタンスの作成  
 SOAP ヘッダーを正しい文字列に設定することが困難な場合もあります。 BizTalk プロジェクトに Web 参照を追加するときに、すべての複雑な Web メッセージ部分がルート要素として Reference.xsd に追加されます。 Reference.xsd には、定義されている各 SOAP ヘッダーのルート要素も含まれます。 SOAP ヘッダーを正しい文字列に設定するためには、BizTalk エディタを使用して Reference.xsd の SOAP ヘッダー ルート要素のインスタンスを作成する必要があります。 生成されたインスタンス データを直接使用することも、インスタンス データに実際のデータを含めることもできます。  
  
 BizTalk エディターを使用してインスタンス データを生成する方法の詳細については、次を参照してください。[インスタンス メッセージの生成方法](../core/how-to-generate-instance-messages.md)です。  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>XmlDocument の作成によるコンテキスト プロパティの設定  
 コンテキスト プロパティを設定するには作成することで、 **XmlDocument**と書き込みの文字列値、 **XmlDocument**をコンテキスト プロパティです。 型の変数を宣言する**XMLDocument**し、XML データを割り当てます。  
  
 次の例では宣言型の変数を設定**XMLDocument**し、XML データを割り当てます。  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 次の例は、コンテキスト プロパティの設定方法を示しています。  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。 .NET クラスを呼び出すことの詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
## <a name="creating-soap-headers-for-a-soap-request"></a>SOAP 要求の SOAP ヘッダーの作成  
 SOAP 要求の SOAP ヘッダーを作成するときは、SOAP ヘッダーが正しく作成されたことを確認する必要があります。 SOAP アダプタでは SOAP ヘッダー コンテキスト プロパティの内容を検証しません。  
  
> [!NOTE]
>  SOAP ヘッダーが正しくなければ、BizTalk は Web サービスに SOAP 要求を送信できません。  
  
 BizTalk から Web サービスに返される SOAP 応答にも SOAP ヘッダーが含まれている場合があります。 これらの SOAP ヘッダーには、定義されている SOAP ヘッダーである場合にのみアクセスできます。  
  
> [!NOTE]
>  使用される Web サービスは、定義されている SOAP ヘッダーのみをサポートします。  
  
 定義済み SOAP ヘッダーの詳細については、次を参照してください。[を使用して SOAP ヘッダー](../core/using-soap-headers.md)です。 応答 SOAP ヘッダーは、要求 SOAP ヘッダーと同じ構文を使用してコンテキスト プロパティに設定されます。  
  
 次のコードは、応答 SOAP ヘッダーへのアクセス方法を示しています。  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 コンテキスト プロパティに含まれている値は、XML データを含む文字列です。 BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形です。 内の文字列を読み込み、 **XmlDocument**を使用して XPath クエリを特定のフィールドにアクセスします。  
  
 BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [XLANG-s 言語](../core/xlang-s-language.md)します。  
  
## <a name="see-also"></a>参照  
 [XLANG の言語](../core/xlang-s-language.md)   
 [使用する Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md)