---
title: "プライベート プロセス オーケストレーションのビジネス ルールの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dd0ebb22bcf6253604e4e8bf7fd858deb776b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a>プライベート プロセス オーケストレーションのビジネス ルールの定義
受信確認プライベート プロセスで使用するビジネス ルールを定義できます。 これにより、プライベート プロセス オーケストレーションを停止することなく、ビジネス ルールを大幅に変更できます。 このプロセスでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ビジネス ルール エンジンを使用します。 このプロセスには以下の手順が含まれます。  
  
1.  新しいボキャブラリの追加。 少なくとも 1 つのボキャブラリ定数値を定義する必要があります。 この値により、ビジネス ルールのしきい値が設定されます。 さらに XML ドキュメントの `Get` 要素と `Set` 要素の定義も必要です。 これにより、確立方法[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]しきい値を使用します。  
  
2.  新しいポリシーの追加。 ポリシーの作成、ルール セットの作成、およびそのポリシーの保存、公開、展開が含まれます。  
  
3.  プライベート プロセス オーケストレーションからのビジネス ルールの呼び出し。 これは、追加、**ルールの呼び出し**オーケストレーションへの図形です。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、サンプルが含まれています[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ビジネス ポリシー、samplebtarnpolicy.xml、で\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>。Accelerator for rosettanet \sdk\pipautomation\3a4 です。 詳細については、次を参照してください。[サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)です。  
  
 PIP3A4PrivateResponder.odx オーケストレーションは、ビジネス ルールを組み込んでいる PIP (Partner Interface Process) 固有の応答側プライベート プロセスを実装する方法を示すプライベート プロセス オーケストレーションのサンプルです。 このサンプルの詳細については、次を参照してください。 [3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)です。  
  
 ボキャブラリおよびポリシーの詳細については、BizTalk Server で「ビジネス ルールの開発」トピックを参照してください。  
  
### <a name="to-add-a-new-vocabulary"></a>新しいボキャブラリを追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。  
  
2.  場合、**ルール ストアを開く**ダイアログ ボックスが開き、選択、 **BizTalk ルール エンジン**データベースを現在のサーバーを設定し、をクリックして**OK**です。  
  
3.  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ビジネス ルール作成ツールで、ファクト エクスプ ローラー ウィンドウを右クリックして**ボキャブラリ**、クリックして**新しいボキャブラリの追加**です。  
  
4.  プロパティ ウィンドウで (左下)、次のように設定します。、**名前**プロパティを適切なボキャブラリは、を押してからの名前に**Enter**です。  
  
5.  作成したボキャブラリ フォルダを展開しを右クリックして**バージョン 1.0 (未保存)**、クリックして**新しい定義の追加**です。  
  
6.  **ボキャブラリの定義ウィザード**] ページで、[**定数値、値の範囲、または値セット**、クリックして**[次へ]**です。  
  
7.  **定数値、値の範囲、または値セット**] ページの [、**定義名**ボックスで、適切なボキャブラリ定数値の名前を入力します**Maximum Quantity Allowed。**、クリックして**次**です。  
  
8.  **定数値の定義**] ページの [、**値フィールド**ボックスに、しきい値を入力し、をクリックして**完了**です。  
  
### <a name="to-define-get-and-set-elements"></a>Get 要素と Set 要素を定義するには  
  
1.  ビジネス ルール作成ツールのファクト エクスプローラ ペインで、"に、新しいボキャブラリ プロシージャ"を追加で作成したボキャブラリ フォルダの下を右クリックして**バージョン 1.0 (未保存)**、クリックして**新しい定義の追加**.  
  
2.  **ボキャブラリの定義ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリック**次**です。  
  
3.  **XML ドキュメントの要素または属性** ページの定義名 テキスト ボックス内の名前を入力、**取得**要素。  
  
4.  をクリックして**参照**を使用して、スキーマ ファイルを選択してをクリックするスキーマの場所に移動して**開く**です。  
  
5.  場合、**ルート ノードの選択**ページが表示されたらを参照するルート ノードを選択します。  
  
6.  **バインドの選択** ページで、しきい値を定義するフィールドに移動してをクリックして**OK**です。  
  
7.  **ドキュメントの種類**ボックスに、ドキュメントの名前を入力します。  
  
8.  **操作の種類**セクションで、 **「取得」操作の実行**です。  
  
9. **[完了]**をクリックします。  
  
10. 1 つまたは複数を定義するには、この手順を繰り返します`Set`操作で、 **「設定」操作の実行**の**操作の種類**です。  
  
### <a name="to-save-and-publish-the-vocabulary"></a>ボキャブラリを保存および公開するには  
  
1.  ビジネス ルール作成ツールで、ファクト エクスプ ローラー ウィンドウで、作成したボキャブラリ フォルダの下を右クリックして**バージョン 1.0 (未保存)**、クリックして**保存**です。  
  
2.  ファクト エクスプ ローラー ウィンドウで、3 a4purchaseordervocabulary フォルダの下を右クリックして**バージョン 1.0**、し、**発行**です。  
  
### <a name="to-add-a-new-policy-and-rules"></a>新しいポリシーとルールを追加するには  
  
1.  ビジネス ルール作成ツールでポリシー エクスプローラ ペインで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。  
  
2.  をクリックして**"policy1"**です。  
  
3.  プロパティ ペインで、設定、**名前**プロパティを適切なポリシーの名前にします。  
  
4.  ポリシー エクスプ ローラー ウィンドウで、新しいポリシーのフォルダーを右クリックして**バージョン 1.0 (未保存)**、クリックして**新しいルールの追加**です。  
  
5.  をクリックして**Rule1**です。  
  
6.  プロパティ ウィンドウで、次のように設定します。、**名前**プロパティをルール名を選択し、キーを押します**Enter**です。  
  
7.  ルール作成ツールで下にある、 **IF**  ウィンドウを右クリックして**条件**、し、該当する場合、論理条件を選択します。  
  
8.  ファクト エクスプローラ ペインで下にある**ボキャブラリ**、展開**述語**、展開**バージョン 1.0 - 公開済み**、作成ツール画面にドラッグして、希望の述語の選択上にドロップして**条件**または論理演算子です。  
  
9. ファクト エクスプ ローラー ウィンドウで、ボキャブラリ フォルダーの下で作成したボキャブラリを展開し、**バージョン 1.0 - 公開済み**、select、`Get`または`Set`要素が作成ツール画面にドラッグし、上にドロップ**argument1**です。  
  
10. ボキャブラリ フォルダーを選択、`Get`または`Set`要素が作成ツール画面にドラッグし、上にドロップ**argument2**です。  
  
11. ボキャブラリ フォルダーの下の選択、`Set`要素、作成ツール画面にドラッグしにドロップ、**アクション**ボックスの [THEN] ペインでします。  
  
12. 変数に関連付けられている場合、`Set`要素に、必要に応じて変更し、変数、キーを押します**Enter**です。 必要に応じて、他の `Set` 要素を使用してこの手順を繰り返します。  
  
### <a name="to-save-publish-and-deploy-the-policy"></a>ポリシーを保存、公開、展開するには  
  
1.  ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下でビジネス ルール作成ツールでは、ルールの定義が完了したら、右クリック**バージョン 1.0 (未保存)**、クリックして**保存**です。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下を右クリックして**バージョン 1.0**、クリックして**発行**です。  
  
3.  ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下を右クリックして**バージョン 1.0**、クリックして**展開**です。  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a>オーケストレーションからビジネス ルールを呼び出すには  
  
1.  開始**Microsoft Visual Studio 2012**です。  
  
2.  **ファイル** メニューの 開く をポイントし、をクリックして**プロジェクト/ソリューション**です。  
  
3.  ビジネス ルールを呼び出す必要があります、クリックしてオーケストレーションを含むソリューションを見つける**開く**です。  
  
4.  をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
5.  展開**変数**です。 オーケストレーション変数の一覧に、オーケストレーションから呼び出すビジネス ポリシー内の各パラメーターに対応する変数が含まれているいことを確認します。 その変数がポリシー パラメーターと同じ種類であることを確認します。 右クリックし、一覧に各ポリシー パラメーターのオーケストレーション変数が含まれていない場合**変数**、クリックして**新しい変数**です。 [オーケストレーションの種類] に変数名を入力し、プロパティ ウィンドウでパラメーターの種類を入力します。  
  
6.  **ツールボックス**、ドラッグ、**ルールの呼び出し**図形をオーケストレーション デザイン画面に、下にドロップし、**受信**図形です。  
  
7.  ダブルクリックして、**ルールの呼び出し**図形です。  
  
8.  **呼び出すビジネス ポリシーの選択**ボックスで、ドロップダウン リストから、ビジネス ポリシーを選択します。  
  
9. 最初のパラメーターが示すようの**パラメーター名**、ドロップダウン リストから名前を選択します。  
  
    > [!NOTE]
    >  Btarn、**ポリシー パラメーター**ビジネス ポリシー内のすべてのパラメーターを使用してリスト。 リスト内の各パラメーターの BTARN が入力した値で**パラメーターの型**ビジネス ポリシーから。 関連付けられているドロップダウン リストで**パラメーター名**BTARN は、ポリシー パラメータと同じ型を持つオーケストレーションの変数の一覧からすべての変数の名前を入力します。 オーケストレーション変数を選択することにより、その変数はポリシー パラメーターに関連付けられます。 オーケストレーション変数は、[オーケストレーションの種類] で表示できます。  
  
10. その他すべてのパラメーターについて手順 9. を繰り返します。  
  
11. オーケストレーション デザイン ウィンドウで、入力の追加など、ビジネス ポリシーに関連付けられている処理に必要なすべての他の図形、**デシジョン**図形の下、**ルールの呼び出し**図形です。  
  
    > [!NOTE]
    >  使用する方法の例については、**ルールの呼び出し**オーケストレーションに図形を BTARN SDK に付属の PIP3A4PrivateResponder.odx オーケストレーションを参照してください。 これは、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\3a4\pr です。 詳細については、次を参照してください。 [3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)です。  
  
12. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)