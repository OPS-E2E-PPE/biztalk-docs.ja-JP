---
title: "チュートリアル: BizTalk Server のポリシー実行の追跡 |Microsoft ドキュメント"
description: "追跡を有効にして、BizTalk Server で、ポリシーの追跡の詳細を表示するのには、チュートリアル"
ms.custom: 
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f1baca3a561702546ca2fae10b1c567042cd387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-tracking-policy-execution"></a>チュートリアル: ポリシーの実行を追跡します。
追跡を有効にするための手順、 **ProcessPurchaseOrder**ポリシー、およびポリシーが実行された後に追跡情報を表示するためです。  
  
## <a name="prerequisites"></a>前提条件  
完了、[チュートリアル: ポリシーを変更する](../core/walkthrough-modifying-the-policy.md)このチュートリアルを実行する前にチュートリアルです。  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a>ProcessPurchaseOrder ポリシーの追跡を有効にします。  
  
1.  開いている**BizTalk Server 管理**です。 既に開いている場合は、f5 キーを押して更新します。  
  
2.  展開**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**です。  
  
3.  右クリック**ポリシー****追加**、し、**ポリシー**です。  
  
    > [!NOTE]
    >  ポリシーの追跡を有効にするには、BizTalk Server 管理コンソールを使用して BizTalk アプリケーションにポリシーを追加する必要があります。  
  
4.  **ポリシーの追加** ダイアログ ボックスで、展開**ProcessPurchaseOrder**、バージョンを選択して**1.3**です。  
  
5.  **[OK]**をクリックします。  
  
6.  表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新するを選択します。
  
7.  右クリック**ProcessPurchaseOrder**、し、**追跡します。**  
  
8.  **ポリシー追跡オプション** ダイアログ ボックスで、すべてのチェック ボックスを**ファクト アクティビティ**、**条件の評価**、**ルールの実行**、および**議題の更新**です。  
  
9. **[OK]**をクリックします。  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a>ソリューションをテストして、追跡情報を表示  
  
1.  開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳の値を変更し、**ステータス**フィールドを**XYZ**です。  
  
2.  コピー **SamplePO.xml**で作成した[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。  
  
3.  オーケストレーションの出力ディレクトリに、出力ファイルが表示されます。 出力 XML ファイルを開くことを確認の値、**ステータス**にフィールドが設定されている**Approved**です。  
  
4.  **BizTalk Server 管理コンソール**に移動して、**グループの概要** ページで、をクリックして、**グループ ハブ** タブし、をクリックして**追跡サービス インスタンス**.  
  
5.  オーケストレーション (RuleTest.Orchestration_1) の名前を右クリックし、をクリックして**メッセージ フロー**です。  
  
6.  をクリックして**このオーケストレーション インスタンスのポリシー実行の詳細を表示するには、このリンク**です。 次の図のようなウィンドウに表示することを確認します。  
  
     ![BRE &#45;チュートリアル &#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")  
  
7. [時刻] をクリックしてまたは**ProcessPurchaseOrder1.3**を次の画面を表示します。 この画面では、ポリシーの実行を要求したサービス (オーケストレーション)、オーケストレーションの ID、ポリシーが実行された時刻、およびポリシーの ID を参照できます。  
  
     ![BRE &#45;チュートリアル &#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")  
  
8. をクリックして**ファクト アクティビティ**ルールにアサートされたファクト (データ) を表示するエンジンの作業メモリと、取り消されたファクトをルール エンジンの作業メモリからです。  
  
     ![BRE &#45;チュートリアル &#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")  
  
9. **ファイル** メニューのをクリックして**移動背面**です。  
  
10. をクリックして**評価条件**です。 評価された条件の詳細を参照してください。 この場合は、ポリシーに 2 つのルールがあり、各ポリシーに条件が 1 つずつ設定されています。 は 2 つの条件が評価されたことを確認できます評価される 1 つ`true`に評価される、もう 1 つと`false`です。  
  
     ![BRE &#45;チュートリアル &#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")  
  
11. **ファイル** メニューのをクリックして**移動背面**です。  
  
12. をクリックして**議題の更新**です。 ApprovalRule のみが議題に追加されていることがわかります。 DeniedRule は、条件が `false` と評価されるため議題に追加されていません。  
  
     ![BRE &#45;チュートリアル &#45;議題](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")  
  
13. をクリックして**ApprovalRule** ApprovalRule の定義を表示します。  
  
14. **ファイル** メニューのをクリックして**移動背面**です。  
  
15. [**ファイル**] メニューのをクリックして**移動背面**もう一度です。  
  
16. をクリックして**を発生させたルール**です。 ApprovalRule のみが実行された (ApprovalRule のアクションが実行された) ことがわかります。  
  
17. **ファイル** メニューのをクリックして**移動背面**です。  
  
18. をクリックして**実行されなかったルール**です。 DeniedRule は、議題に含まれていなかったため実行されなかったことがわかります。  
  
19. 手順 1-18 で**SamplePO2.xml**です。  
  
## <a name="key-details"></a>キーの詳細  
  
-   ポリシーの追跡情報は、ポリシーをテストする場合にビジネス ルール作成ツールで表示される追跡情報とよく似ています。  
  
-   オーケストレーション名は RuleTest.odx ですが、名前が変更されてもオーケストレーションの型名が Orchestration_1 に設定されているため、オーケストレーションの名前は Orchestration_1 と表示されます。 追跡は、オーケストレーション名形式で表示\<Namespace >.\<名前を入力 >。  
  
-   BizTalk Server 管理コンソールを使用して BizTalk アプリケーションからポリシーを削除した場合、そのポリシーはアプリケーションから削除されるだけでなく、ルール エンジン データベースからも削除されます。 削除されたポリシーは、ビジネス ルール作成ツールに表示されなくなります (F5 キーを押して表示を更新してください)。 このため、アプリケーションからポリシーを削除する場合は、十分に注意する必要があります。  
  
-   RuleTestApp の停止し、選択すると、**完全停止**オプション、ProcessPurchaseOrder ポリシー (バージョン 1.3) は自動的に展開されていません。  
  
-   複数のアプリケーションでポリシーを使用する場合は、ポリシー用に独立したアプリケーションを作成して、クライアント アプリケーションからそのアプリケーションへの参照を作成します。 ポリシーをすべてのクライアント アプリケーションに追加すると、クライアント アプリケーションの 1 つを停止した時点でポリシーが展開解除され、そのポリシーを他のクライアント アプリケーションで使用できなくなります。 したがって、複数のアプリケーション間で共有するポリシーについては、独立したアプリケーションを作成することをお勧めします。  
  
-   RuleTestApp を開始すると、ProcessPurchaseOrder ポリシー (バージョン 1.3) は自動的に展開されます。  
  
## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了するには、[チュートリアル: ポリシーを展開する](../core/walkthrough-deploying-the-policy.md)ポリシーを展開するための手順を説明するチュートリアルです。  
  
## <a name="see-also"></a>参照  
 [ポリシーの追跡を構成する方法](../core/how-to-configure-tracking-for-a-policy.md)   
 [ポリシーの管理](../core/managing-policies.md)