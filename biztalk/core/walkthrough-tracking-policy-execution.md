---
title: 'チュートリアル: BizTalk Server でのポリシー実行の追跡 |Microsoft Docs'
description: チュートリアルでは、追跡を有効にして、BizTalk Server で、ポリシーの追跡の詳細を表示
ms.custom: ''
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2285353afb1049574e5f78eafeba41931102ac56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395953"
---
# <a name="walkthrough-tracking-policy-execution"></a>チュートリアル: ポリシー実行の追跡
追跡を有効にするための詳細な手順、 **ProcessPurchaseOrder**ポリシー、およびポリシーの実行後に追跡情報を表示するためです。  
  
## <a name="prerequisites"></a>前提条件  
完了、[チュートリアル。ポリシーを変更する](../core/walkthrough-modifying-the-policy.md)このチュートリアルを実行する前にチュートリアル。  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a>ProcessPurchaseOrder ポリシーの追跡を有効にします。  
  
1.  開いている**BizTalk Server 管理**します。 既に開いている場合、f5 キーを押して更新します。  
  
2.  展開**コンソール ルート**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**します。  
  
3.  右クリックして**ポリシー**を選択します**追加**、し、**ポリシー**します。  
  
    > [!NOTE]
    >  ポリシーの追跡を有効にするには、BizTalk Server 管理コンソールを使用して BizTalk アプリケーションにポリシーを追加する必要があります。  
  
4.  **ポリシーの追加** ダイアログ ボックスで、展開**ProcessPurchaseOrder**、バージョンを選択します。 **1.3**します。  
  
5.  **[OK]** をクリックします。  
  
6.  表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新を選択します。
  
7.  右クリックして**ProcessPurchaseOrder**、し、**追跡します。**  
  
8.  **ポリシー追跡オプション**] ダイアログ ボックスで、[すべてのチェック ボックスを**ファクト アクティビティ**、**条件評価**、**ルール実行**、および**議題の更新**します。  
  
9. **[OK]** をクリックします。  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a>ソリューションをテストして、追跡情報を表示  
  
1.  開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳での値を変更し、**状態**フィールドを**XYZ**します。  
  
2.  コピー **SamplePO.xml**で作成した[チュートリアル。ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。  
  
3.  オーケストレーションの出力ディレクトリに出力ファイルを確認する必要があります。 出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。  
  
4.  **BizTalk Server 管理**に移動して、**グループの概要** ページで、をクリックして、**グループ ハブ** タブをクリックして**のサービスインスタンスの追跡**.  
  
5.  オーケストレーション (RuleTest.Orchestration_1) の名前を右クリックし、をクリックし、**メッセージ フロー**します。  
  
6.  クリックして**このオーケストレーション インスタンスのポリシー実行の詳細を表示するには、このリンクに従ってください**します。 次の図のようなウィンドウに表示することを確認します。  
  
     ![BRE&#45;チュートリアル&#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")  
  
7. [時間] をクリックしてまたは **[processpurchaseorder1.3]** に次の画面を参照してください。 この画面で、ポリシーの実行、ポリシーの実行位置、オーケストレーションの ID とポリシーの ID を要求したサービス (オーケストレーション) を確認できます。  
  
     ![BRE&#45;チュートリアル&#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")  
  
8. クリックして**ファクト アクティビティ**ルールにアサートされたファクト (データ) を表示するエンジンの作業メモリと、ルール エンジンの作業メモリから取り消されたファクト。  
  
     ![BRE&#45;チュートリアル&#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")  
  
9. **ファイル** メニューのをクリックして**Navigate バック**します。  
  
10. クリックして**条件評価**します。 評価された条件の詳細を参照してください。 この場合、ポリシーでは、2 つの規則があるし、各ポリシー条件があります。 2 つの条件が評価されることを確認できます。1 つ`true`とに評価される、もう 1 つ`false`します。  
  
     ![BRE&#45;チュートリアル&#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")  
  
11. **ファイル** メニューのをクリックして**Navigate バック**します。  
  
12. クリックして**議題の更新**します。 ApprovalRule のみが議題に追加されたことを確認できます。 その条件が評価されるため、DeniedRule は、議題に追加されません`false`します。  
  
     ![BRE&#45;チュートリアル&#45;議題](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")  
  
13. クリックして**ApprovalRule** ApprovalRule の定義を確認します。  
  
14. **ファイル** メニューのをクリックして**Navigate バック**します。  
  
15. **ファイル** メニューのをクリックして**Navigate バック**もう一度です。  
  
16. クリックして**実行されたルール**します。 ApprovalRule のみが発生したことを確認できます (ApprovalRule のアクションが実行された)。  
  
17. **ファイル** メニューのをクリックして**Navigate バック**します。  
  
18. クリックして**されなかったルール**します。 議題に含まれていなかったために、DeniedRule が実行されなかったことを確認できます。  
  
19. 手順 1-18 で**SamplePO2.xml**します。  
  
## <a name="key-details"></a>キーの詳細  
  
-   ポリシーの追跡情報は、ポリシーをテストするときにビジネス ルール作成ツールで表示される追跡情報とよく似ています。  
  
-   オーケストレーション名は RuleTest.odx が、オーケストレーションの名前として表示 Orchestration_1、名前が変更された場合でも、オーケストレーションの種類の名前が Orchestration_1 に設定されているためです。 追跡で表示されます、オーケストレーション名形式\<Namespace\>.\<名前を入力\>します。  
  
-   BizTalk Server 管理コンソールを使用して BizTalk アプリケーションからポリシーを削除する場合、ツールは、アプリケーションからだけでなく、ルール エンジン データベースからも、ポリシーを削除します。 不要になったビジネス ルール作成ツール (f5 キーを更新するキーを押します)、ポリシーが表示されます。 そのため、アプリケーションからポリシーを削除するときに注意する必要があります。  
  
-   RuleTestApp の停止して、選択したとき、**完全停止**オプション、ProcessPurchaseOrder ポリシー (バージョン 1.3) は、自動的に展開されます。  
  
-   複数のアプリケーションでポリシーを使用する場合は、ポリシーの別のアプリケーションを作成しへの参照がクライアントからアプリケーションを作成します。 クライアント アプリケーションの 1 つを停止すると、すべてのクライアント アプリケーションにポリシーを追加する場合、ポリシーが展開を解除し、他のクライアント アプリケーションは、ポリシーを使用できなくします。 そのためは 2 つまたは複数のアプリケーションで共有されているポリシーの別のアプリケーションを作成することをお勧めします。  
  
-   RuleTestApp を開始すると、ProcessPurchaseOrder ポリシー (バージョン 1.3) は自動的に展開します。  
  
## <a name="next-steps"></a>次の手順  
 このチュートリアルを完了すると、これに移動、[チュートリアル。ポリシーを展開する](../core/walkthrough-deploying-the-policy.md)ポリシーを展開するための手順を説明するチュートリアル。  
  
## <a name="see-also"></a>参照  
 [ポリシーの追跡を構成する方法](../core/how-to-configure-tracking-for-a-policy.md)   
 [ポリシーの管理](../core/managing-policies.md)