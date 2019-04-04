---
title: XML スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ec364e7-866d-4164-be91-be75a40ce878
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b46f5b43a34049dfc3ad366fd87fa82d6dac2cb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997491"
---
# <a name="xml-schemas"></a>XML スキーマ
XML スキーマは、XML で表されるビジネス ドキュメントの詳細情報を記述します。 Microsoft BizTalk Server では、ビジネス ドキュメントの正規表現として XML を使用するため受信および送信ドキュメントには、翻訳は不要です。 また、すべてのスキーマで使用できる基本的なプロパティだけを使用して、XML スキーマを BizTalk エディターで作成できるので、スキーマ エディター拡張機能を有効にする必要はありません。  
  
 BizTalk Server で XML スキーマを作成することがいくつかの方法はあります。 たとえば、次のオブジェクトにアクセスできます。  
  
- **新しいスキーマを作成する**します。 このスキーマ作成の方法には、新しいスキーマを BizTalk プロジェクトに追加することも含まれます。 **ソリューション エクスプ ローラー**、BizTalk プロジェクトを右クリックし、をクリックして**追加**、 をクリックして**新しい項目の**、 をクリックし、**スキーマ**します。 スキーマ ツリー ビューでさまざまなノードを追加してスキーマの構造を構築します。  
  
- **他のスキーマと組み合わせて、新しいスキーマを作成する**します。 : 複雑なスキーマを実際に使用するとき、一般的には、既存の他のスキーマで提供されている型を使用して、メッセージのスキーマを作成します。 XSD (XML Schema Definition) 言語の概念 (スキーマのインポート、包含、および再定義) を使用することにより、他のスキーマで既に定義されている型を利用できます。 複数のスキーマを組み合わせて使用の詳細については、[使用その他のスキーマを](../core/schemas-that-use-other-schemas.md)を参照してください。  
  
- **インスタンス メッセージからスキーマを生成する**します。 : インスタンス メッセージが整形式 XML で構成されていれば、特定のインスタンス メッセージに対応する XML スキーマを生成できます。 使用して、**生成した項目の追加 -  *\<BizTalk プロジェクト名\>***   ダイアログ ボックスをクリックして**生成した項目の追加**で**プロジェクト** メニューの この種類のスキーマ生成操作を実行します。  
  
  > [!NOTE]
  >  この生成操作は、XML スキーマを生成する場合のみ使用できます。プロパティ スキーマやフラット ファイル スキーマには使用できません。  
  
- **以前のスキーマ仕様言語から XSD にスキーマを移行する**します。 Xml-data Reduced (XDR) 形式でスキーマを格納する BizTalk Server の以前のバージョンを使用して開発されたスキーマから、BizTalk Server の XML スキーマを生成できます。 古い XDR スキーマを BizTalk Server で使用される XSD 形式に移行する方法の詳細については、[スキーマの移行前のバージョンの BizTalk Server から](../core/schema-migration-from-previous-versions-of-biztalk-server.md)を参照してください。  
  
   また、DTD (Document Type Definition) 構文で表記されるドキュメント スキーマから、XSD に基づいた XML スキーマを生成できます。  
  
   使用して、**生成した項目の追加 -  *\<BizTalk プロジェクト名\>***   ダイアログ ボックスをクリックして**生成した項目の追加**で**プロジェクト** メニューの この種類のスキーマ生成操作を実行します。  
  
  > [!NOTE]
  >  これらの生成操作は、XML スキーマを生成する場合のみ使用できます。プロパティ スキーマやフラット ファイル スキーマには使用できません。  
  
  スキーマの作成にどの方法を使用していても、スキーマを変更して、対応するインスタンス メッセージを完全に説明できます。 これらのタスクを開始するを参照してください。[スキーマ内のノードを管理する](../core/managing-the-nodes-within-a-schema.md)、[ノードのプロパティの設定](../core/how-to-set-node-properties.md)、および[既存のノードの操作](../core/working-with-existing-nodes.md)します。  
  
## <a name="see-also"></a>参照  
 [さまざまな種類の BizTalk スキーマ](../core/different-types-of-biztalk-schemas.md)