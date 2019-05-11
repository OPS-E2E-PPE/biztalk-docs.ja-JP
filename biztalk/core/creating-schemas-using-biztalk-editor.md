---
title: BizTalk エディターを使用してスキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03fac91b-5b67-4baf-968c-294c525d3018
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32b4667e0f9777ccf21f26fdfc38a2d12946998
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389884"
---
# <a name="create-schemas-using-biztalk-editor"></a>BizTalk エディターを使用してスキーマを作成します。

## <a name="overview"></a>概要
BizTalk エディターは、Microsoft 内で実行されるツール[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境。 作成、編集、およびアプリケーションで使用するためのスキーマの管理に使用できます。 BizTalk エディターでは、階層レコードおよびフィールドの独自のグラフィカル システムを使用して、インスタンス メッセージの構造を表すし、定義するスキーマを格納する XML スキーマ定義 (XSD) 言語を使用します。 これはインスタンス メッセージの交換を形式に関係なく当てはまります。 たとえば、取引先パートナーとフラット ファイルを交換するとします。 BizTalk Server では、フラット ファイルを処理するように変換して、BizTalk エディターで定義されている XSD スキーマに準拠した XML 形式から。  
  
 BizTalk エディターを使用して作成するスキーマは、次の図に示すように、協調動作するビジネス プロセス内で使用できます。  
  
 ![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")  
  
 スキーマは、フラット ファイル形式と XML 間など、別のインスタンス メッセージの形式を変換するためのアセンブラーおよび逆アセンブラーも使用されます。 スキーマは、インスタンス メッセージの変換、別の構造、インスタンス メッセージを構築するインスタンス メッセージ内のデータを使用する場合でも重要な役割を果たします。 そのコンテンツの元のインスタンス メッセージからのデータの一部またはすべてを必要とするインスタンス メッセージの異なるが、関連する型が考えられますか、新しいインスタンス メッセージは、注文書のさまざまな表現など、意味的に同等にあります。  
  
 すべてのインスタンス メッセージを XSD スキーマに準拠した XML 形式に変換するための重要な理由の 1 つの構造体からのメッセージを別の構造体に変換するプロセスを簡略化することです。 メッセージの構造は、その構文の違いに関係なくと同じ意味ですがです。 たとえば、取引先パートナーと構造が発注書を異なる方法が含まれている基本的な情報は、自動的に変換を行き来することができます。 最初は、対応する XSD スキーマに基づいて XML 形式にすべてのインスタンス メッセージを変換、してには、インスタンス メッセージを XML と非 XML の形式の間を行き来翻訳して 1 つの XML 構造からを変換することができます。 インスタンス メッセージの変換とインスタンス メッセージの変換の違いの詳細については、次を参照してください。[データ変換](../core/data-transformation.md)します。  
  
 Microsoft Visual Studio 環境内でのコンパニオン ツールを BizTalk エディターでは、BizTalk マッパーです。 BizTalk マッパーを使用して、1 つのスキーマに準拠するインスタンス メッセージを変換する方法をグラフィカルに定義する BizTalk エディターを使用して、構造と関連するインスタンス メッセージのペアの形式を定義するスキーマを作成した後 (送信元インスタンス メッセージとスキーマ) を別のスキーマ (送信先インスタンス メッセージおよびスキーマ) に準拠するインスタンス メッセージにします。 このような変換の仕様では、拡張可能なスタイル シート言語変換 (XSLT) を使用して実装され、呼び出されたマップをファイルとして保存します。 BizTalk マッパーの概念と手順については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)します。 BizTalk マッパーのプロパティおよび functoid のリファレンスについては、次を参照してください。、**マップ プロパティ参照**と**Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
 BizTalk エディターを使用して、構造体が含まれていない空のスキーマを開くことができます、既存の XSD スキーマを開くことができます。 または XSD 以外のソースからスキーマを生成することができます。 XSD 以外のソースからスキーマを生成する場合、BizTalk エディターは、ソースの構造を解釈し、その XSD 表現であるスキーマを生成します。 任意のレコードと、BizTalk エディター スキーマ ツリー ビューに表示されるフィールドを編集し、BizTalk スキーマと構造を保存できます。  
  
 BizTalk エディターのキーボード ショートカットの使用方法の詳細については、次を参照してください。 [BizTalk エディターのキーボード ショートカット](../core/biztalk-editor-keyboard-shortcuts.md)します。  
  
## <a name="next-steps"></a>次のステップ
  
-   [スキーマ作成の計画](../core/planning-for-schema-creation.md)  
  
-   [インスタンス メッセージについて](../core/about-instance-messages.md)  
  
-   [スキーマについて](../core/about-schemas.md)  
  
-   [BizTalk エディターを使用してください。](../core/using-biztalk-editor.md)  
  
-   [スキーマの作成](../core/creating-schemas.md)  
  
-   [BizTalk フラット ファイル スキーマ ウィザードでのスキーマの作成](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)  
  
-   [スキーマのテスト](../core/testing-schemas.md)  
  
-   [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)  
  
-   [スキーマを作成する際の考慮事項](../core/considerations-when-creating-schemas.md)  
  
-   [スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)