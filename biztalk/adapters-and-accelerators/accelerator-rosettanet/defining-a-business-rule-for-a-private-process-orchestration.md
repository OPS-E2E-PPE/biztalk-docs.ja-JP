---
title: プライベート プロセス オーケストレーションのビジネス ルールの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- vocabularies, saving
- private processes, orchestrations
- business rules, private processes
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- policies, deploying
- vocabularies, creating
- orchestrations, private-process orchestrations
- private processes, customizing
- policies, publishing
- business rules, Set elements
- creating, policies
- customizing private processes
- Set elements
- business rules, orchestrations
- publishing, vocabularies
- vocabularies, publishing
- creating, rules
- business rules, Get elements
- policies, saving
- publishing, policies
- Get elements
- orchestrations, business rules
- rules
- private processes, business rules
- policies, creating
ms.assetid: 5d2b0257-1b15-482b-a562-798b808e9a2d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae4657e82c99630cc5d9a31915246b2bf3ebc02c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283751"
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a>プライベート プロセス オーケストレーションのビジネス ルールの定義
受信確認プライベート プロセスで使用するビジネス ルールを定義できます。 これにより、プライベート プロセス オーケストレーションを停止することなく、ビジネス ルールを大幅に変更できます。 このプロセスで、Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ビジネス ルール エンジン。 このプロセスには以下の手順が含まれます。  
  
1. 新しいボキャブラリの追加。 少なくとも 1 つのボキャブラリ定数値を定義する必要があります。 この値により、ビジネス ルールのしきい値が設定されます。 さらに XML ドキュメントの `Get` 要素と `Set` 要素の定義も必要です。 これを確立する方法 Microsoft[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]しきい値を使用します。  
  
2. 新しいポリシーの追加。 ポリシーの作成、ルール セットの作成、およびそのポリシーの保存、公開、展開が含まれます。  
  
3. プライベート プロセス オーケストレーションからのビジネス ルールの呼び出し。 これは、追加、**ルールの呼び出し**オーケストレーションへの図形。  
  
   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、サンプルが含まれています[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ビジネス ポリシー、samplebtarnpolicy.xml、で\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>。Accelerator for rosettanet \sdk\pipautomation\3a4 します。 詳細については、次を参照してください。[サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)します。  
  
   PIP3A4PrivateResponder.odx オーケストレーションは、ビジネス ルールを組み込んでいる PIP (Partner Interface Process) 固有の応答側プライベート プロセスを実装する方法を示すプライベート プロセス オーケストレーションのサンプルです。 このサンプルの詳細については、次を参照してください。 [3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)します。  
  
   ボキャブラリとポリシーの詳細については、BizTalk Server で「ビジネス ルールの開発」トピックを参照してください。  
  
### <a name="to-add-a-new-vocabulary"></a>新しいボキャブラリを追加するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。  
  
2. 場合、**ルール ストアを開く** ダイアログ ボックスが開いたら、選択、 **BizTalk ルール エンジン**データベースを現在のサーバーを設定し、をクリックし、 **OK**。  
  
3. Microsoft ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**ボキャブラリ**、 をクリックし、**新しいボキャブラリの追加**します。  
  
4. プロパティ ウィンドウ (左下) で、設定、**名前**プロパティを適切なボキャブラリを押してからの名前に **」と入力**します。  
  
5. 作成したボキャブラリ フォルダを展開し、右クリックして**バージョン 1.0 (未保存)**、 をクリックし、**新しい定義の追加**します。  
  
6. **ボキャブラリの定義ウィザード**] ページで、[**定数値、値の範囲、または値セットの**、順にクリックします**次**します。  
  
7. **定数値、値の範囲、または値セット**ページで、**定義名**ボックスに、適切なボキャブラリ定数値の名前を入力します**Maximum Quantity Allowed。**、 をクリックし、**次**します。  
  
8. **定数値の定義**] ページの [、**値フィールド**ボックスに、しきい値を入力し、をクリックし、**完了**。  
  
### <a name="to-define-get-and-set-elements"></a>Get 要素と Set 要素を定義するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで、"に、新しいボキャブラリ プロシージャ"を追加で作成したボキャブラリ フォルダの下を右クリックして**バージョン 1.0 (未保存)**、 をクリックし、**新しい定義の追加**.  
  
2.  **ボキャブラリの定義ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリックします**次**します。  
  
3.  **XML ドキュメントの要素または属性** ページで、定義名 テキスト ボックス内の名前を入力、**取得**要素。  
  
4.  クリックして**参照**を使用して、スキーマ ファイルを選択してクリックするスキーマの場所に移動**オープン**します。  
  
5.  場合、**ルート ノードの選択**ページが開いたら、参照するルート ノードを選択します。  
  
6.  **バインドの選択** ページで、しきい値を定義するフィールドに移動してクリックして**OK**します。  
  
7.  **ドキュメントの種類**ボックスに、ドキュメントの名前を入力します。  
  
8.  **操作の種類**セクションで、 **「取得」操作の実行**します。  
  
9. **[完了]** をクリックします。  
  
10. 1 つまたは複数定義するには、この手順を繰り返します`Set`操作で、 **「設定」操作の実行**の**操作の種類**します。  
  
### <a name="to-save-and-publish-the-vocabulary"></a>ボキャブラリを保存および公開するには  
  
1.  ビジネス ルール作成ツールで作成したボキャブラリ フォルダの下のファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**、 をクリックし、**保存**します。  
  
2.  3A4PurchaseOrderVocabulary フォルダーの下のファクト エクスプローラ ペインで右クリック**バージョン 1.0**、し、**発行**します。  
  
### <a name="to-add-a-new-policy-and-rules"></a>新しいポリシーとルールを追加するには  
  
1.  ビジネス ルール作成ツールでポリシー エクスプローラ ペインで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。  
  
2.  クリックして**Policy1**します。  
  
3.  プロパティ ウィンドウで、設定、**名前**プロパティを適切なポリシーの名前にします。  
  
4.  ポリシー エクスプ ローラー ウィンドウの新しいポリシーのフォルダーの下で右クリック**バージョン 1.0 (未保存)**、 をクリックし、**新しいルールの追加**します。  
  
5.  クリックして**Rule1**します。  
  
6.  プロパティ ウィンドウで、設定、**名前**プロパティ ルールの名前を選択して、キーを押します **」と入力**します。  
  
7.  ルール作成ツールで 、**場合**ウィンドウで、右クリック**条件**、該当する場合に、論理条件を選択します。  
  
8.  ファクト エクスプ ローラー] ウィンドウで [**ボキャブラリ**、展開**述語**、展開**バージョン 1.0 - 公開済み**、作成ツール画面にドラッグ、希望の述語を選択します。上にドロップして**条件**または論理演算子です。  
  
9. ファクト エクスプ ローラー ウィンドウで、ボキャブラリ フォルダーの下で作成したボキャブラリを展開し、**バージョン 1.0 - 公開済み**を選択、`Get`または`Set`要素、作成ツール画面にドラッグし、上にドロップ**引数 1**します。  
  
10. [ボキャブラリ] フォルダーを選択、`Get`または`Set`要素、作成ツール画面にドラッグしにドロップ **[引数 2]** します。  
  
11. [ボキャブラリ] フォルダーを選択、`Set`要素、作成ツール画面にドラッグし、ドロップ、**アクション**[THEN] ペインにボックスします。  
  
12. 変数が関連付けられている場合、`Set`要素に、必要に応じて変更し、変数キーを押します**Enter**します。 必要に応じて、他の `Set` 要素を使用してこの手順を繰り返します。  
  
### <a name="to-save-publish-and-deploy-the-policy"></a>ポリシーを保存、公開、展開するには  
  
1.  ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下でビジネス ルール作成ツール、ルールの定義が完了したら、右クリックして**バージョン 1.0 (未保存)**、 をクリックし、**保存**します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下で右クリック**バージョン 1.0**、 をクリックし、**発行**します。  
  
3.  ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下で右クリック**バージョン 1.0**、 をクリックし、**デプロイ**します。  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a>オーケストレーションからビジネス ルールを呼び出すには  
  
1.  開始**Microsoft Visual Studio 2012**します。  
  
2.  **ファイル** メニューの 開く をポイントし、順にクリックします**プロジェクト/ソリューション**します。  
  
3.  ビジネス ルールを呼び出す必要があります、クリックしてオーケストレーションを含むソリューションを見つける**オープン**します。  
  
4.  をクリックして**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
5.  展開**変数**します。 オーケストレーション変数の一覧に、オーケストレーションから呼び出すビジネス ポリシー内の各パラメーターに対応する変数が含まれているいことを確認します。 その変数がポリシー パラメーターと同じ種類であることを確認します。 右クリックし、一覧に各ポリシー パラメーターのオーケストレーション変数が含まれていない場合**変数**、 をクリックし、**新しい変数**します。 [オーケストレーションの種類] に変数名を入力し、プロパティ ウィンドウでパラメーターの種類を入力します。  
  
6.  **ツールボックス**、ドラッグ、**ルールの呼び出し**図形をオーケストレーション デザイン画面と、下にドロップし、**受信**図形。  
  
7.  ダブルクリックして、**ルールの呼び出し**図形。  
  
8.  **呼び出すビジネス ポリシーの選択**ボックスで、ドロップダウン リストから、ビジネス ポリシーを選択します。  
  
9. 最初のパラメーターが示すようの**パラメーター名**、ドロップダウン リストから名前を選択します。  
  
    > [!NOTE]
    >  BTARN を設定、**ポリシー パラメーター**一覧で、ビジネス ポリシーのすべてのパラメーターを使用します。 BTARN の一覧の各パラメーターで値が入力**パラメーターの型**ビジネス ポリシーから。 関連付けられているドロップダウン リストで**パラメーター名**BTARN は、ポリシー パラメータと同じ型を持つオーケストレーションの変数の一覧からすべての変数の名前を入力します。 オーケストレーション変数を選択することにより、その変数はポリシー パラメーターに関連付けられます。 オーケストレーション変数は、[オーケストレーションの種類] で表示できます。  
  
10. その他すべてのパラメーターについて手順 9. を繰り返します。  
  
11. オーケストレーションのデザイン ウィンドウで、入力の追加など、ビジネス ポリシーに関連付けられている処理に必要なすべての他の図形を**デシジョン**図形の下、**ルールの呼び出し**図形。  
  
    > [!NOTE]
    >  使用する方法の例については、**ルールの呼び出し**図形をオーケストレーションに、BTARN SDK に含まれる PIP3A4PrivateResponder.odx オーケストレーションを参照してください。 場所は\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\3a4\pr です。 詳細については、次を参照してください。 [3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)します。  
  
12. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)