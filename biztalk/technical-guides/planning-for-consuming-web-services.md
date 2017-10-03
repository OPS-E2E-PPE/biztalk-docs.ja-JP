---
title: "Web サービスを使用するための計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24863069-929b-4b0b-9643-073965fb5532
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a13151a5dd76b20b70872b963dc6a688370444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-consuming-web-services"></a>Web サービスを使用の計画
Web サービスの計画は、Web サービスを公開し、Web サービスの使用を計画の計画、2 つのカテゴリに分けることができます。 このトピックでは、Web サービスの使用に関する考慮事項について説明します。 Web サービスを発行する方法については、次を参照してください。 [Planning for Publishing Web Services1](../technical-guides/planning-for-publishing-web-services1.md)です。  
  
 計画を作成するには、次を考慮してください。  
  
-   **パラメーター名に 2 つのアンダー スコア文字を使用**  
  
     Web メソッドのパラメータ名を "__" (2 つのアンダースコア文字) で始めることはできません。 2 つのアンダースコア文字で始まる名前を使用すると、XLANG/s でサポートされない (使用できない) Web メッセージ部分が作成される場合があります。  
  
-   **すべての要素と anyAttribute の Web メソッドでは、属性はサポートされていません**  
  
     使用することはできません、**任意**要素または**anyAttribute** Web メソッドのスキーマの属性です。  
  
-   **Xlang/s キーワードの使用**  
  
     Web サービス名または Web メソッド名に XLANG/s のキーワードを使用することはできません。 Web サービス名または Web メソッド名で XLANG/s のキーワードを使用すると、Web サービスを追加するときにコンパイル エラーが発生します。 Xlang/s 言語の予約語の一覧は、次を参照してください。、 [xlang/s の予約語](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。  
  
-   **パラメーターの型に必要な xlang/s のサポート**  
  
     非 xlang/s サポートされている Web メソッドのパラメーター型を使用すると、コンパイル エラーが発生します。 たとえば、BizTalk Server では 1 次元配列のスキーマの種類で構成されるパラメータはサポートされていません。 さらに、BizTalk Server は多次元配列をサポートしていません。 Xlang/s 言語は、BizTalk Server で予約語の一覧は、次を参照してください。 [xlang/s の予約語](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。  
  
-   **Web 参照を含む c# のキーワードまたは識別子を追加することによってコンパイル エラーが生じないように**  
  
     使用すると、 **Web 参照の追加**BizTalk プロジェクトに Web 参照を追加するには、BizTalk Server は、スキーマには、各 Web メソッドを呼び出すために必要なスキーマの種類に変換します。 変換後のスキーマは Reference.xsd に追加されます。 スキーマに C# のキーワードと同じ要素名や C# の識別子として有効でない要素名が含まれる場合は、ランタイム エラーが発生することがあります。 ランタイム エラーを回避するには、使用する Web サービスに C# のキーワードと同じ要素名や C# の識別子として無効な要素名を含めないようにしてください。  
  
-   **複数のサービスとポートの種類の定義はサポートされていません**  
  
     BizTalk Server では、単一のサービスおよびポートの種類の定義を含む Web サービス ファイルを追加することができます。 複数のサービスまたはポートの種類の定義を含む WSDL ファイルを追加すると、次のエラーが発生することがあります。  
  
     `Could not generate BizTalk files. Object reference not set to an instance of an object.`  
  
-   **Web サービスによって公開される配列を使用するためのサポート**  
  
     BizTalk Server では、BizTalk Server Web サービスではない Web サービスによって公開される 1 次元配列およびジャグ配列を使用できます。 Web サービスの配列を使用する方法の詳細については、次を参照してください。 [Web サービスの配列を使用する方法](http://go.microsoft.com/fwlink/?LinkId=155766)(http://go.microsoft.com/fwlink/?LinkId=155766)。  
  
    > [!NOTE]  
    >  多次元配列の構文はサポートされていません。 たとえば、 *MyArray [「1, 5]*です。  
  
    > [!NOTE]  
    >  BizTalk Server がの配列の使用をサポートしていません**データセット**Web サービスによって公開されているオブジェクト。 Xlang/s サブサービスは、.NET DataSet クラスでは、ネイティブでサポートが、.NET DataSet オブジェクトの配列を公開する Web サービスへの Web 参照を含む BizTalk プロジェクトを作成する場合、プロジェクトをコンパイルしようとするエラーが表示されます。  
  
-   **Web メソッドのパラメーターがあります Xml シリアル化可能**  
  
     使用する Web サービスのパラメータはすべて、XML シリアル化可能である必要があります。 XML シリアル化可能でないパラメータを含む Web メソッドを追加すると、次のエラー メッセージが表示されることがあります。  
  
     "System.Xml.Element はメッセージ部分の型になるように、XML にシリアル化可能である必要があります。"  
  
    > [!NOTE]  
    >  データ型、 **XmlDocument**と**データセット**、サポートされていない Xml シリアル化可能なの中にします。  
  
-   **メッセージングのみの Web サービスの使用**  
  
     メッセージングのみの Web サービスを使用するときに、すべて BizTalk Server メッセージ ボディ部分の名前は、Web メソッドのパラメーター名と一致する必要があります。 たとえば、Web サービスの署名が `WebMethod(MyType1 type1, MyType2 type2)` である場合、ボディ部分の名前は type1 および type2 である必要があります。それ以外の場合は、次の実行時エラーが発生することがあります。  
  
     `Failed to retrieve the message part for parameter %1`  
  
     詳細については、次を参照してください。 [Messaging-Only シナリオで Web サービスの使用方法](http://go.microsoft.com/fwlink/?LinkId=155767)(http://go.microsoft.com/fwlink/?LinkId=155767)。  
  
-   **プログラムによる SOAP 送信ポートの構成**  
  
     プログラムを使って、構成プロパティをメッセージ コンテキストに設定できます。 送信ポートが静的か動的かどうかは、オーケストレーションまたはカスタム パイプライン コンポーネントでこれらのプロパティを設定できます。  
  
    > [!NOTE]  
    >  構成するのには**MethodName**プロパティの静的 SOAP 送信ポートがプログラムで、設定する必要があります**メソッド名**に**[後で指定]**で、 **Webサービス**のタブ、 **SOAP トランスポートのプロパティ**ダイアログ ボックスで、BizTalk Server 管理コンソールです。  
  
     詳細については、 **MethodName**プロパティを参照してください[を消費する Web サービスの URI を動的に設定する方法](http://go.microsoft.com/fwlink/?LinkID=155768)(http://go.microsoft.com/fwlink/?LinkID=155768)。  
  
-   **プロパティの規則**  
  
     構成プロパティがオーケストレーション、または受信パイプラインのカスタム パイプライン コンポーネントで設定されている場合は、次のルールが適用されます。  
  
    -   メッセージが送信された場合は、静的な送信ポート、プロパティの値は、その送信ポート用に構成された値で上書きされます。  
  
    -   動的送信ポートにメッセージを送信する場合、プロパティの値は上書きされません。  
  
     構成プロパティが送信パイプラインのカスタム パイプライン コンポーネントで設定されている場合は、次のルールが適用されます。  
  
    -   メッセージを送信する送信ポートが静的か動的かにかかわらず、プロパティ値は上書きされません。 つまり、送信パイプライン コンポーネントは、設定されているかどうかにかかわらず、構成プロパティを上書きします。  
  
    -   カスタム パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](http://go.microsoft.com/fwlink/?LinkId=155769)(http://go.microsoft.com/fwlink/?LinkId=155769)。  
  
    -   SOAP 送信アダプタの構成プロパティの詳細については、次を参照してください。[を消費する Web サービスの URI を動的に設定する方法](http://go.microsoft.com/fwlink/?LinkID=155768)(http://go.microsoft.com/fwlink/?LinkID=155768)。  
  
-   **使用する Web サービスを複数ルートのスキーマが原因でコンパイル エラーを含む Web 参照を追加します。**  
  
     公開済み BizTalk オーケストレーションから派生した Web サービス プロジェクトに Web 参照を追加して、オーケストレーションに複数のルートを持つスキーマが含まれています、し、エラーが発生、プロジェクトをコンパイルするときにします。 公開済みの BizTalk オーケストレーションから派生した Web 参照をプロジェクトに追加する場合は、オーケストレーションに複数ルートのスキーマが含まれていないことを確認してください。  
  
-   **Web メソッドのパラメータとして TypedDataSets の使用**  
  
     Web メソッドのパラメータとして TypedDataSets を使用するには、次の手順を実行します。  
  
    1.  Web 参照を C# プロジェクトに追加し、プロキシを生成します。  
  
    2.  SOAP 送信ポートを作成し、送信ポートにプロキシを指定して、メソッドを選択します。  
  
    3.  オーケストレーションで、遅延バインディング ポートとメッセージの種類を定義します。 ほとんどの場合に、プロパティの昇格や識別フィールドのアクセスは必要ありません、として、型を定義できる**XMLDocument**です。 この種類に対応したパススルー パイプラインを選択してください。  
  
    4.  BizTalk Server 管理コンソールでの**Web サービス** タブで、 **SOAP トランスポートのプロパティ**SOAP のダイアログ ボックスの送信ポートを作成したそのプロキシを使用することを指定します。 アセンブリ、型、メソッドも指定する必要があります。  
  
-   **ジェネリック パラメーターと、コンパイル エラーを想定した Web メソッドを含む使用する Web サービスへの Web 参照を追加します。**  
  
     Null 許容パラメーターなどのジェネリック パラメーターを想定した Web メソッドを含む Web サービスには、プロジェクトに Web 参照を追加する場合、プロジェクトをコンパイルするときにエラーが発生します。 これはサポートされていません。 ジェネリック クラスは XLANG/s から明示的な特殊化によって呼び出す必要があります。  
  
-   **Web 参照の追加を使用して BizTalk スキーマの生成**  
  
     使用すると、 **Web 参照の追加**BizTalk プロジェクトに Web 参照を追加するには、BizTalk Server は、スキーマには、各 Web メソッドを呼び出すために必要なスキーマの種類に変換します。 変換後のスキーマは Reference.xsd に追加されます。 いることを確認する、 **Web 参照の追加**BizTalk スキーマを生成正しく、Web サービスは、次のガイドラインに従う必要があります。  
  
    -   Web メソッドが必要**SoapDocumentMethodAttribute**の代わりに**ください**です。  
  
    -   Web サービスおよびメソッドを使用する必要があります、**リテラル**の代わりにバインド**Encoded**など**[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**です。  
  
    -   Web メソッドのパラメータと戻り値の型**XmlRootAttribute** 、有効な**Namespace**プロパティ ネイティブ XSD 型、および XmlNode 型でない限り、します。  
  
    -   Web メソッドを使用しないでください、**された**と**ResponseNamespace**プロパティ**SoapDocumentMethodAttribute**です。  
  
    -   Web サービスは、Web Services Interoperability (WSI) Basic Profile バージョン 1.1 に準拠する。  
  
-   **Web 参照の追加が Web Services Description Language (WSDL) インポート要素をサポートしていません**  
  
     インポート要素を使用して WSDL ファイルの Web 参照を追加すると、[Web 参照の追加] は失敗します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)