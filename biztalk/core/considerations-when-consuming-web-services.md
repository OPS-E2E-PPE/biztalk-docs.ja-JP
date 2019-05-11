---
title: Web サービスを使用する場合の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea7038dc-4740-4c0a-b6a1-08bc22f42bc2
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7747e04357f041451e8aa6651704f815cba562a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354710"
---
# <a name="considerations-when-consuming-web-services"></a>Web サービスを使用する際の考慮事項
ここでは、Web サービスを使用する際に考慮すべき情報について説明します。  
  
## <a name="using-two-underscore-characters-in-a-parameter-name"></a>パラメータ名での 2 つのアンダースコア文字の使用  
 Web メソッドのパラメータ名を "__" (2 つのアンダースコア文字) で始めることはできません。 2 つのアンダースコア文字で始まる名前を使用すると、XLANG/s でサポートされない (使用できない) Web メッセージ部分が作成される場合があります。  
  
## <a name="the-any-element-and-the-anyattribute-attributes-are-not-supported-in-web-methods"></a>any 要素と anyAttribute 属性は Web メソッドでサポートされない  
 使用することはできません、**任意**要素または**anyAttribute** Web メソッドのスキーマ内の属性。  
  
## <a name="using-xlangs-keywords"></a>XLANG/s キーワードの使用  
 Web サービス名または Web メソッド名に XLANG/s のキーワードを使用することはできません。 Web サービス名または Web メソッド名で XLANG/s のキーワードを使用すると、Web サービスを追加するときにコンパイル エラーが発生します。 Xlang/s 言語の予約語の一覧は、次を参照してください。 [xlang-s の予約語](../core/xlang-s-reserved-words.md)します。  
  
## <a name="required-xlangs-support-for-parameter-types"></a>パラメータの型は XLANG/s でサポートされる必要がある  
 Web メソッドにおいて、XLANG/s でサポートされていないパラメータの型を使用すると、コンパイル エラーが発生します。 たとえば、BizTalk Server では 1 次元配列のスキーマの種類で構成されるパラメータはサポートされていません。 また、BizTalk Server では多次元配列もサポートされていません。 Xlang/s 言語は、BizTalk server によって予約されている単語の一覧は、次を参照してください。 [xlang-s の予約語](../core/xlang-s-reserved-words.md)します。  
  
## <a name="avoiding-compilation-errors-caused-by-adding-web-references-containing-c-keywords-or-identifiers"></a>C# のキーワードまたは識別子を含む Web 参照を追加することによって発生するコンパイル エラーの回避  
 使用すると、**サービス参照の追加**を BizTalk プロジェクトにサービス参照を追加するには、BizTalk Server はスキーマに対して各 Web メソッドを呼び出すために必要なスキーマ型に変換します。 変換後のスキーマは Reference.xsd に追加されます。 スキーマに C# のキーワードと同じ要素名や C# の識別子として有効でない要素名が含まれる場合は、ランタイム エラーが発生することがあります。 ランタイム エラーを回避するには、使用する Web サービスに C# のキーワードと同じ要素名や C# の識別子として無効な要素名を含めないようにしてください。  
  
## <a name="multiple-serviceport-type-definitions-are-unsupported"></a>複数のサービス/ポートの種類の定義はサポートされていません  
 BizTalk Server では、単一のサービスおよびポートの種類の定義を含む Web サービス ファイルを追加することができます。 複数のサービスまたはポートの種類の定義を含む WSDL ファイルを追加すると、次のエラーが発生することがあります。  
  
 "BizTalk ファイルを生成できませんでした。 オブジェクト参照がオブジェクト インスタンスに設定されていません。"  
  
## <a name="support-for-consuming-arrays-exposed-by-web-services"></a>Web サービスで公開される配列の使用に関するサポート  
 BizTalk Server では、BizTalk Web サービス以外の Web サービスによって公開される 1 次元のジャグ配列を使用できます。 Web サービスの配列を使用する方法の詳細については、次を参照してください。 [Web サービスの配列を使用する方法](../core/how-to-consume-web-service-arrays.md)します。  
  
> [!NOTE]
>  多次元配列の構文はサポートされていません。 たとえば、 `MyArray[1,5]`のようにします。  
  
> [!NOTE]
>  BizTalk Server がの配列の使用をサポートしていません**データセット**Web サービスによって公開されているオブジェクト。 XLANG/s サブサービスでは、.NET DataSet クラスがネイティブでサポートされます。ただし、.NET DataSet オブジェクトの配列を公開する Web サービスへの Web 参照を含む BizTalk プロジェクトを作成した場合は、プロジェクトのコンパイル時にエラーが発生します。  
  
## <a name="web-method-parameters-must-be-xml-serializable"></a>Web メソッドのパラメータは XML シリアル化可能である必要がある  
 使用する Web サービスのパラメータはすべて、XML シリアル化可能である必要があります。 XML シリアル化可能でないパラメータを含む Web メソッドを追加すると、次のエラー メッセージが表示されることがあります。  
  
 "System.Xml.Element はメッセージ部分の型になるように、XML にシリアル化可能である必要があります。"  
  
> [!NOTE]
>  データ型、 **XmlDocument**と**データセット**、サポートされていない Xml シリアル化可能な中にします。  
  
## <a name="consuming-messaging-only-web-services"></a>メッセージングのみの Web サービスの使用  
 メッセージングのみの Web サービスを使用する場合、BizTalk メッセージのボディ部分の名前はすべて、Web メソッドのパラメータ名と一致する必要があります。 たとえば、Web サービスの署名が `WebMethod(MyType1 type1, MyType2 type2)` である場合、ボディ部分の名前は type1 および type2 である必要があります。それ以外の場合は、次の実行時エラーが発生することがあります。  
  
 "パラメータ "%1" のメッセージ部分を取得できませんでした。"  
  
 詳細については、次を参照してください。[メッセージングのみのシナリオで Web サービスを使用する方法](../core/how-to-consume-web-services-in-a-messaging-only-scenario.md)します。  
  
## <a name="configuring-a-soap-send-port-programmatically"></a>プログラムによる SOAP 送信ポートの構成  
 プログラムを使って、構成プロパティをメッセージ コンテキストに設定できます。 これらのプロパティは、送信ポートが静的であるか動的であるかにかかわらず、オーケストレーションまたはカスタム パイプライン コンポーネントに設定できます。  
  
> [!NOTE]
>  構成する、 **MethodName**プロパティ、静的 soap 送信ポートをプログラムで、設定する必要がある**メソッド名**に **[後で指定]** で、 **Webサービス**のタブ、 **SOAP トランスポートのプロパティ** ダイアログ ボックスで、BizTalk Server 管理コンソール。  
> 
>  詳細については、 **MethodName**プロパティを参照してください[消費する Web サービスの URI を動的に設定する方法](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md)します。  
> 
>  詳細については**SOAP トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **SOAP トランスポートのプロパティ ダイアログ ボックス、Web サービス**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="property-rules"></a>プロパティのルール  
 構成プロパティがオーケストレーション、または受信パイプラインのカスタム パイプライン コンポーネントで設定されている場合は、次のルールが適用されます。  
  
- メッセージを送信する場合は、静的な送信ポート、プロパティの値は、その送信ポート用に構成された値で上書きされます。  
  
- 動的送信ポートにメッセージを送信する場合、プロパティの値は上書きされません。  
  
  構成プロパティが送信パイプラインのカスタム パイプライン コンポーネントで設定されている場合は、次のルールが適用されます。  
  
- メッセージを送信する送信ポートが静的か動的かにかかわらず、プロパティ値は上書きされません。 つまり、送信パイプライン コンポーネントは、設定されているかどうかにかかわらず、構成プロパティを上書きします。  
  
- カスタム パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)します。  
  
- SOAP 送信アダプタの構成プロパティの詳細については、次を参照してください。[消費する Web サービスの URI を動的に設定する方法](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md)します。  
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-multi-rooted-schema-will-cause-a-compilation-error"></a>使用する Web サービスに複数ルートのスキーマが含まれており、その Web サービスへの Web 参照を追加すると、コンパイル エラーが発生する  
 公開済みの BizTalk オーケストレーションから派生した Web サービスの Web 参照をプロジェクトに追加し、そのオーケストレーションに複数ルートのスキーマが含まれる場合は、プロジェクトのコンパイル時にエラーが発生します。 公開済みの BizTalk オーケストレーションから派生した Web 参照をプロジェクトに追加する場合は、オーケストレーションに複数ルートのスキーマが含まれていないことを確認してください。  
  
## <a name="using-typeddatasets-as-parameters-to-web-methods"></a>Web メソッドのパラメータとしての TypedDataSets の使用  
 Web メソッドのパラメータとして TypedDataSets を使用するには、次の手順を実行します。  
  
1. Web 参照を C# プロジェクトに追加し、プロキシを生成します。  
  
2. SOAP 送信ポートを作成し、送信ポートにプロキシを指定して、メソッドを選択します。  
  
3. オーケストレーションで、遅延バインディング ポートとメッセージの種類を定義します。 ほとんどの場合は、プロパティの昇格や識別フィールドへのアクセスは必要ありません、として、型を定義できます**XMLDocument**します。 この種類に対応したパススルー パイプラインを選択してください。  
  
4. BizTalk Server 管理コンソールで、 **Web サービス** タブで、 **SOAP トランスポートのプロパティ**SOAP のダイアログ ボックスで送信ポート、その作成したプロキシを使用することを指定します。 アセンブリ、型、メソッドも指定する必要があります。 詳細については、次を参照してください。、 **SOAP トランスポートのプロパティ ダイアログ ボックス、Web サービス**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-web-method-expecting-generic-based-parameters-will-cause-a-compilation-error"></a>使用する Web サービスにジェネリック パラメータを想定した Web メソッドが含まれており、その Web サービスへの Web 参照を追加すると、コンパイル エラーが発生する  
 NULL 許容パラメータなどのジェネリック パラメータを想定した Web メソッドを含む Web サービスの Web 参照をプロジェクトに追加すると、プロジェクトのコンパイル時にエラーが発生します。 これはサポートされていません。 ジェネリック クラスは XLANG/s から明示的な特殊化によって呼び出す必要があります。  
  
## <a name="biztalk-schema-generation-using-the-add-service-reference"></a>[サービス参照の追加] を使用した BizTalk スキーマの生成  
 使用すると、**サービス参照の追加**を BizTalk プロジェクトにサービス参照を追加するには、BizTalk Server はスキーマに対して各 Web メソッドを呼び出すために必要なスキーマ型に変換します。 変換後のスキーマは Reference.xsd に追加されます。 いることを確認する、**サービス参照の追加**BizTalk スキーマを生成します。 正しく、Web サービスは、次のガイドラインに従う必要があります。  
  
-   Web メソッド**SoapDocumentMethodAttribute**の代わりに**SoapRpcMethodAttribute**します。  
  
-   Web サービスおよびメソッドを使用する必要があります、**リテラル**の代わりにバインド**Encoded**など **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]** します。  
  
-   Web メソッドのパラメーターと戻り値の型**XmlRootAttribute**有効な**Namespace**プロパティ ネイティブ XSD 型、および XmlNode 型でない限り、します。  
  
-   Web メソッドが使用する必要があります、 **RequestNamespace**と**ResponseNamespace**プロパティ**SoapDocumentMethodAttribute**します。  
  
-   Web サービスは、Web Services Interoperability (WSI) Basic Profile バージョン 1.1 に準拠する。  
  
## <a name="xsd-will-not-contain-nodes-for-simple-parameter-types"></a>XSD に単純なパラメーターの型のノードが含まれない  
 Web 参照を追加するときに、Web メソッドに単純な型のパラメーターが含まれている場合、生成される XSD にはそのパラメーターのノードは含まれません。 代わりに、生成されるマルチパート メッセージに単純な型の部分が含まれます。 このメッセージ部分は、オーケストレーションで適切に処理する必要があります。 Web サービスへの要求の部分である場合は、メッセージの割り当て図形により、その部分に手動で値を割り当てます。 Web サービスからの応答の部分である場合は、図形式でその部分に手動でアクセスして、値を確認します。  
  
## <a name="the-add-service-reference-do-not-support-the-web-services-description-language-wsdl-import-element"></a>[サービス参照の追加] で Web Services Description Language (WSDL) インポート要素がサポートされない  
 インポート要素を使用して WSDL ファイルのサービス参照を追加すると、[サービス参照の追加] は失敗します。  
  
## <a name="see-also"></a>参照  
 [Web メッセージの構築](../core/constructing-web-messages.md)