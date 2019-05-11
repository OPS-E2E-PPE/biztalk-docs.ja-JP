---
title: XML メッセージ用スキーマの作成方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 993d491dd6eda8f066598c98be0790813cc1e491
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338960"
---
# <a name="how-to-create-schemas-for-xml-messages"></a>XML メッセージ用スキーマの作成方法
BizTalk メッセージのスキーマを作成するためのいくつかの方法はあります。 このトピックでは、これらのメソッドのいくつかの手順が説明します。  
  
### <a name="to-create-a-new-schema"></a>新しいスキーマを作成するには  
  
1. **ソリューション エクスプ ローラー**スキーマを追加する BizTalk プロジェクトを選択します。  
  
2. **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。  
  
3. **新しい項目の追加 - \< *BizTalk ProjectName* \>**  ] ダイアログ ボックスで、**テンプレート**セクションで、[ **スキーマ**.  
  
4. **名前**ボックスで、スキーマの名前を入力し、クリックして**追加**します。  
  
5. 必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。  
  
6. スキーマ ツリー ビューで、選択、**スキーマ**ノード、し、プロパティ ウィンドウで、、 **Target Namespace**プロパティとターゲットの名前空間の名前を入力します。 スキーマ作成; の初期段階では、このプロパティを設定することが重要します。既定値は使用しないでください**Target Namespace**プロパティの値。  
  
   > [!NOTE]
   >  特定の名前のスキーマ ファイルなどのプロジェクト メンバー ファイルなる競合によってコンパイル エラー c# 予約語で (System など) と.net Framework 型と名前空間名。 スキーマの例には、schema.xsd、XmlContent、および Rootnode が含まれます。 これは、ため、**型名**プロパティの既定値の基本 (拡張機能) の部分、**ファイル名**プロパティ。 この種のコンパイル エラーを回避するには、値を明示的に変更することで、**型名**プロパティを競合しないようにします。  
  
   > [!NOTE]
   >  追加、削除、およびその関連プロパティと共に、スキーマのフィールドとレコードを変更する必要があります。 これに関する詳細についてを参照してください。[スキーマ内のノードを管理する](../core/managing-the-nodes-within-a-schema.md)します。  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a>XSD 以外のソースからスキーマを生成するには  
  
1.  **ソリューション エクスプ ローラー**、BizTalk プロジェクトを右クリックし、 をポイント**追加**、 をクリックし、**生成した項目の追加**します。  
  
2.  **生成した項目の追加 - \< *BizTalk ProjectName* \>**   ダイアログ ボックスで、**テンプレート**セクションで、**生成スキーマ**、 をクリックし、**追加**します。  
  
3.  **スキーマの生成** ダイアログ ボックスで、**ドキュメントの種類**ドロップダウン リストで、 **XDR スキーマ**、 **DTD スキーマ**、または**整形式 XML**します。  
  
     いずれかが表示される場合**DTD (読み込まれていません)** または**整形式の XML (読み込まれていません)** ボックスの一覧で、適切なドキュメントの種類を選択しをインストールするプロセスをガイドします、DLL がありません。 次の手順を繰り返します。  
  
4.  **スキーマの生成**ダイアログ ボックスで、をクリックして**参照**、クリックして、インポートするファイルを見つけます**オープン**。 ファイルを指定は、前の手順で選択したドキュメントの種類と一致する必要があります。  
  
     新しいスキーマは、拡張子は .xsd とそのファイルと同じ名前を使用して、BizTalk エディターで開かれる、指定したファイルから生成されます。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマの管理](../core/managing-schemas-within-projects.md)