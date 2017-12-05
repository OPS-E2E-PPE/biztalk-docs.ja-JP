---
title: "XML メッセージ用スキーマを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6396d4607e93298961e6691ded2ca8d4566d819c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-schemas-for-xml-messages"></a>XML メッセージ用スキーマの作成方法
BizTalk メッセージのスキーマは、複数の方法で作成できます。 このトピックでは、いくつかの方法について手順を説明します。  
  
### <a name="to-create-a-new-schema"></a>新しいスキーマを作成するには  
  
1.  **ソリューション エクスプ ローラー**スキーマを追加する BizTalk プロジェクトを選択します。  
  
2.  **[プロジェクト]** メニューの **[新しい項目の追加]**をクリックします。  
  
3.  **新しい項目の追加 - \<* BizTalk ProjectName*\>* * ダイアログ ボックスで、**テンプレート**セクションで、**スキーマ**.  
  
4.  **名前**ボックスで、スキーマの名前を入力し、をクリックして**追加**です。  
  
5.  必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。  
  
6.  スキーマ ツリー ビューで、選択、**スキーマ**ノード、し、[プロパティ] ウィンドウで次のように選択します。、 **Target Namespace**プロパティとターゲットの名前空間の名前を入力します。 スキーマ作成; の初期段階では、このプロパティを設定することが重要であります。既定値は使用しないでください**Target Namespace**プロパティの値。  
  
    > [!NOTE]
    >  プロジェクトのメンバー ファイル (スキーマ ファイルなど) に特定の名前を使用すると、C# の予約語や .NET Framework の型/名前空間名 (System など) との競合によってコンパイル エラーになる場合があります。 このようなスキーマ名には、schema.xsd、XmlContent、RootNodes などがあります。 これは、ため、**型名**の基本 (拡張機能) 部分のプロパティの既定値、 **Filename**プロパティです。 この種のコンパイル エラーを回避するには、値を明示的に変更して、**型名**プロパティを競合しないようにします。  
  
    > [!NOTE]
    >  必要に応じて、スキーマ内のレコードとフィールド、および、関連するプロパティを追加、削除、変更します。 詳細についてを参照してください。 [、スキーマ内のノードを管理する](../core/managing-the-nodes-within-a-schema.md)です。  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a>XSD 以外のソースからスキーマを生成するには  
  
1.  **ソリューション エクスプ ローラー**、BizTalk プロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加 - \<* BizTalk ProjectName*\>* * ダイアログ ボックスで、**テンプレート**セクションで、 **スキーマ生成**、クリックして**追加**です。  
  
3.  **スキーマの生成** ダイアログ ボックスで、**ドキュメントの種類**ドロップダウン リストで、 **XDR スキーマ**、 **DTD スキーマ**、または**整形式 XML**です。  
  
     いずれかを表示する場合は**DTD (読み込まれていません)**または**整形式 XML (読み込まれていません)**ドロップダウン リストで、適切なドキュメントの種類を選択し、インストール プロセスをガイドします、DLL が不足しています。 その後で、上記の手順を繰り返してください。  
  
4.  **スキーマの生成**ダイアログ ボックスで、をクリックして**参照**、クリックして、インポートするファイルを検索**開く**です。 前の手順で選択したドキュメント型のファイルを指定する必要があります。  
  
     指定したファイルから新しいスキーマが生成され、BizTalk エディターに表示されます。スキーマ名には、指定したファイルと同じ名前 (拡張子は .xsd) が使用されます。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマの管理](../core/managing-schemas-within-projects.md)