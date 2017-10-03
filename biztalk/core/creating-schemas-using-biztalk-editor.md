---
title: "BizTalk エディターを使用してスキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03fac91b-5b67-4baf-968c-294c525d3018
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9e4c6496f43a9602ad56bc0e095d98f2da90d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-schemas-using-biztalk-editor"></a>BizTalk エディターを使用してスキーマを作成します。

## <a name="overview"></a>概要
BizTalk エディターは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境内で動作するツールです。 BizTalk エディターを使用して、アプリケーションに必要なスキーマを作成、編集、および管理できます。 BizTalk エディターは、レコードおよびフィールドを階層で表す独自のグラフィカル システムを使ってインスタンス メッセージの構造を表現します。また、定義されたスキーマは、XSD (XML Schema Definition) 言語を使って格納されます。 この方法は、インスタンス メッセージを交換するときの形式に依存しません。 たとえば、取引先とのデータ交換にフラット ファイルが使用されるとします。 BizTalk Server は、BizTalk エディターで定義された XSD スキーマに基づいて、これらのフラット ファイルを XML 形式に変換したり、XML 形式のファイルをフラット ファイルに変換したりします。  
  
 次の図に示したように、BizTalk エディターを使って作成したスキーマを、オーケストレーションに基づくビジネス プロセスで使用できます。  
  
 ![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")  
  
 スキーマは、アセンブラーおよび逆アセンブラーが、インスタンス メッセージの形式を変換するときにも使用されます (フラット ファイル形式と XML 形式間の変換など)。 インスタンス メッセージの変換では、インスタンス メッセージ内のデータを使って別の構造のインスタンス メッセージが構築されますが、こうしたインスタンス メッセージの変換においても、スキーマが重要な役割を果たしています。 新しいインスタンス メッセージは、意味的に等価である場合があります。たとえば、同じ注文書にもさまざまな表現手段が考えられます。また、異なるインスタンス メッセージでも、データの一部または全体が、他のインスタンス メッセージから流用される場合もあります。  
  
 なぜ、すべてのインスタンス メッセージを、XSD スキーマに準拠した XML 形式に変換するのでしょうか。その理由の 1 つとして、メッセージの構造を変換するためのプロセスを効率化することがあります。 構文的な違いはあれ、メッセージの構造が、意味的には等価であるということはよくあることです。 たとえば、あなたの会社とその取引先とで使われている注文書を考えてみてください。構造が異なっていても、そこに含まれている基本的な情報が同じであれば、相互間で自動的に変換することが可能です。 すべてのインスタンス メッセージを、対応する XSD スキーマに基づいて XML 形式に変換しておくことにより、そのインスタンス メッセージを XML 以外の形式に変換したり、特定の XML 構造を別の XML 構造に変換したりすることができます。 インスタンス メッセージの変換とインスタンス メッセージの変換の違いの詳細については、次を参照してください。[データ変換](../core/data-transformation.md)です。  
  
 Microsoft Visual Studio 環境内で対をなすツールを BizTalk エディターには、BizTalk マッパーです。 関連する 2 つのインスタンス メッセージの構造と形式を定義するスキーマを BizTalk エディターで作成した後、あるスキーマに基づいたインスタンス メッセージ (送信元インスタンス メッセージおよびスキーマ) を別のスキーマに基づくインスタンス メッセージ (送信先インスタンス メッセージおよびスキーマ) に変換する方法を、BizTalk マッパーを使ってグラフィカルに定義できます。 こうした変換の仕様は、XSLT (Extensible Stylesheet Language Transformations) を使って実装され、マップと呼ばれるファイルに格納されます。 BizTalk マッパーの概念と手順については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)です。 BizTalk マッパーのプロパティおよび functoid のリファレンスについては、次を参照してください。、**マップ プロパティの参照**と**Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
 BizTalk エディターでは、構造の含まれない空のスキーマを開いたり、既存の XSD スキーマを開いたりできるほか、XSD 以外のソースからスキーマを生成することもできます。 XSD 以外のソースからスキーマを生成した場合、BizTalk エディターは、そのソースの構造を解釈して、対応する XSD 表現のスキーマを生成します。 BizTalk エディターのスキーマ ツリー ビューに表示されたレコードおよびフィールドは自由に編集でき、その構造を BizTalk スキーマとして保存できます。  
  
 BizTalk エディターのキーボード ショートカットの使用方法の詳細については、次を参照してください。 [BizTalk エディターのキーボード ショートカット](../core/biztalk-editor-keyboard-shortcuts.md)です。  
  
## <a name="next-steps"></a>次の手順
  
-   [スキーマの作成の計画](../core/planning-for-schema-creation.md)  
  
-   [インスタンス メッセージについて](../core/about-instance-messages.md)  
  
-   [スキーマについて](../core/about-schemas.md)  
  
-   [BizTalk エディターの使用](../core/using-biztalk-editor.md)  
  
-   [スキーマの作成](../core/creating-schemas.md)  
  
-   [BizTalk フラット ファイル スキーマ ウィザードを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)  
  
-   [スキーマのテスト](../core/testing-schemas.md)  
  
-   [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)  
  
-   [スキーマを作成する際の考慮事項](../core/considerations-when-creating-schemas.md)  
  
-   [スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)