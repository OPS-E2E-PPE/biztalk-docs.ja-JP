---
title: マップの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc9f8ad1-4aad-4866-8aa4-4877fdc5e5f9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00121334b076ed4c705e7b440c75c1347e4208c9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969112"
---
# <a name="creating-maps"></a>マップの作成
BizTalk マッパーの主要なユーザー インターフェイスが内のタブに表示される、 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。 この表示は、3 つのペインに分割されています。 左ペインでは、送信元スキーマがツリーとして表示されます。 右ペインでは、送信先スキーマがツリーとして表示されます。 中央のペインでは、グリッドが複数のページに表示されます。 送信元スキーマのデータを送信先スキーマにどのようにマップするかを示すには、マップする対象のレコードとフィールドの間に線を引きます。 これらの行が呼び出される*リンク*データのマッピングを指定する最も簡単な方法です。 レコードおよびフィールドのリンクの詳細については、次を参照してください。[マップでリンク](../core/links-in-maps.md)です。  
  
 高度なマッピング手法を実装する場合は Functoid を使用できます。 Functoid は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックス内の BizTalk マッパー タブで使用できるツールです。 これを使用すると、次のような複雑な操作を実行するマップを作成できます。  
  
-   送信元スキーマに含まれる 2 つのフィールドの値を加算し、その結果を送信先スキーマのフィールドに入力する。  
  
-   ルーピング レコードのフィールドの平均値を計算し、その結果を送信先スキーマのフィールドに入力する。  
  
-   ビジネス ニーズに応じて、インスタンス データを操作するカスタム スクリプトを記述する。  
  
 Functoid の詳細については、次を参照してください。[マップの Functoid](../core/functoids-in-maps.md)です。  
  
 BizTalk マッパーは、単純な親子関係から、レコードと階層の詳細で複雑なルーピングまで、さまざまなマッピング シナリオをサポートできます。 マップを作成するときは、次の点を考慮してください。  
  
-   BizTalk マッパーは、結合および並べ替えをサポートしていません。  
  
-   送信元スキーマと送信先スキーマの構造が極端に異なる場合、1 つのマップでは変換できないことがあります。 二重に渡す必要が生じる場合があります。  
  
-   **ループ**functoid には、柔軟かつ強力ですが、まだ対象ループの次のイテレーションを開始する送信元スキーマの値の変更が検出されたときに反復処理を中断することはできません。  
  
-   メソッドの外部変数を宣言することができます、**スクリプト**functoid は、マップの有効期間のスコープ内の変数の中に発生します。 したがって、使用することができます、**スクリプト**functoid 変換のスコープ領域間で値を保持するためです。  
  
 処理されるすべてのデータ[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時に XML 形式である必要があります。 XML でないデータは、マッピングの前に、対応する XML 形式に変換する必要があります。 同様に、マッピング プロセスが完了したときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はマッピング操作の出力を使用し、データの送信先である取引先またはアプリケーションが認識できるファイル形式を作成します。  
  
 BizTalk マッパーにはコンパイラが含まれています。 このツール レベル コンポーネントは、入力インスタンス メッセージを出力インスタンス メッセージに変換するために必要な XSLT (Extensible Stylesheet Language Transformations) を生成します。  
  
 このセクションでは、BizTalk マッパーを使用して 2 つのスキーマ間のマッピングを作成する場合の、タスク固有の情報について説明します。 ここでは、BizTalk マッパーが既に開かれ、マップの送信元スキーマと送信先スキーマが選択されていることを前提にしています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プロジェクト内のマップの管理](../core/managing-maps-within-projects.md)  
  
-   [リンクを使用してレコードとフィールド マッピングを指定する](../core/using-links-to-specify-record-and-field-mappings.md)  
  
-   [Functoid を使用した複雑なマッピングの作成](../core/using-functoids-to-create-more-complex-mappings.md)  
  
-   [マップなしのマップを作成する方法](../core/how-to-create-a-map-without-maps.md)  
  
-   [既定のマッパーを使用して動作を管理する\<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md)