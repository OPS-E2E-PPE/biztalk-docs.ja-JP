---
title: 'チュートリアル: ポリシーのテスト |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53ed915d-0f3a-48ea-bfd5-a1f89b9b689c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ddf9dcc459fbee7494a913846f1c9d2a7137579
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001771"
---
# <a name="walkthrough-testing-the-policy"></a>チュートリアル: ポリシーのテスト
このチュートリアルでは、詳細な手順で作成したポリシーのテスト、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアル。  

## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。  

## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 2 つの手順が含まれています。  

|プロシージャ タイトル|手順の説明|  
|---------------------|---------------------------|  
|テスト ファイルを作成するには|作成の 2 つのサンプル XML ファイルを 400 は Quantity フィールドの値を持つ 1 つの手順について説明します (\<= 500)、もう 1 つは Quantity フィールド 700 (> 500) の値を持つとします。|  
|ProcessPurchaseOrder ポリシーをテストするには|ステップごとの説明に従って、ビジネス ルール作成ツールを使用してポリシーをテストします。|  

### <a name="to-create-the-test-files"></a>テスト ファイルを作成するには  

1.  **開始**] メニューの [open**メモ帳**します。  

2.  次の XML をメモ帳にコピーします。  

    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>400</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>    
    ```  

3.  **ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**します。  

4.  値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)** に**すべてのファイル**します。  

5.  ディレクトリに移動します**C:\BRE-Walkthroughs**します。  

6.  型**SamplePO.xml**の**ファイル名**、 をクリックし、**保存**します。  

7.  **[ファイル]** メニューの **[新規作成]** をクリックします。  

8.  次の XML をメモ帳にコピーします。  

    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>700</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>   
    ```  

9. **ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**します。  

10. 値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)** に**すべてのファイル**します。  

11. ディレクトリに移動します**C:\BRE-Walkthroughs**します。  

12. 型**SamplePO2.xml**の**ファイル名**、 をクリックし、**保存**します。  

13. メモ帳を閉じます。  

### <a name="to-test-the-processpurchaseorder-policy"></a>ProcessPurchaseOrder ポリシーをテストするには  

1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 既にを開き、更新、f5 キーを押してのビジネス ルール作成ツールの場合は。  

    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  

2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、 をクリックし、 **ポリシーのテスト**.  

3.  **XMLDocuments**ノードの [ **RuleTest.PO**、] をクリックし、**インスタンスの追加**。  

     ![ビジネス ルール作成ツール&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")  

4.  選択、 **SamplePO.xml**クリックして、先ほど作成したファイル**オープン**します。  

5.  クリックして**テスト**します。  

6.  出力ウィンドウで出力を確認します。 表示される出力の説明については、「最初のテスト (samplepo.xml) からの出力の分析」セクションを参照してください。  

7.  開いている**SamplePO.xml**でメモ帳に注目してくださいの値、**状態**にフィールドが設定されている**Approved**します。  

8.  右クリック**バージョン 1.0**、 をクリックし、**ポリシーのテスト**します。  

9. 選択**SamplePO.xml**、 をクリックして**インスタンスの削除**、 をクリックし、**インスタンスの追加**します。  

10. 選択、 **SamplePO2.xml**クリックして、先ほど作成したファイル**オープン**します。  

11. クリックして**テスト**します。 表示される出力の説明については、「2 番目のテスト (samplepo2.xml) からの出力の分析」セクションを参照してください。  

12. 開く、 **SamplePO2.xml**メモ帳でファイルし、注意の値、**状態**フィールドはまだ**XYZ**。  

## <a name="analysis-of-the-output-from-the-first-test-samplepoxml"></a>最初のテスト (samplepo.xml) からの出力の分析  

> [!NOTE]
>  出力テキストは太字です。この出力テキストの後に説明が続きます。  

 **ルールセットのルール エンジン トレース: ProcessPurchaseOrder 2006/8/31 1時 33分: 10 PM**  

 ポリシーの実行のルール エンジン トレース**ProcessPurchaseOrder** 2006 年 8 月 31 日に開始された 1時 33分: 10 PM。  

 **ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**  

 **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **ルール セット名: ProcessPurchaseOrder**  

 **操作: アサート**  

 **オブジェクトの種類: TypedXmlDocument:PurchaseOrder**  

 **オブジェクト インスタンス識別子: 14626574**  

 クリックすると**テスト**、次の処理が行われます。  

1. ビジネス ルール作成ツール、 **RuleEngine.Policy**オブジェクトでは、さらに新しいルール エンジン インスタンスを作成するか、ルール エンジン キャッシュからルール エンジンのインスタンスを取得します。  

2. ビジネス ルール作成ツール、 **TypedXmlDocument** SamplePO.xml ファイルに基づいてオブジェクト。  

3. ビジネス ルール作成ツールを起動、 **Policy.Execute**メソッドを**TypedXmlDocument**オブジェクトをパラメーターとして。  

4. **Policy.Execute**メソッド アサート (追加)、 **TypedXmlDocument**オブジェクトをファクトをルール エンジンの作業メモリとして。  

5. ルール エンジンを使用して、 **TypedXmlDocument**オブジェクトをファクトとして、実行、 **ProcessPurchaseOrder**ポリシー。  

   **ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**  

   **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

   **ルール セット名: ProcessPurchaseOrder**  

   **操作: アサート**  

   **オブジェクトの種類: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**  

   **オブジェクト インスタンス識別子: 64530307**  

   **ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**  

   **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

   **ルール セット名: ProcessPurchaseOrder**  

   **操作: アサート**  

   **オブジェクトの種類: TypedXmlDocument:PurchaseOrder: PurchaseOrder/項目**  

   **オブジェクト インスタンス識別子: 43901854**  

6. ルール エンジンは、どの子を決定します。 **TypedXmlDocument**規則で定義された XPath セレクターに基づいて、オブジェクトを作成します。 ビジネス ルール作成ツールでルールを構築するときに XPath セレクターの既定値で選択したノード上のノード、 **XML スキーマ**ファクト エクスプ ローラー タブ。 [XPath フィールド] の既定値は選択したノード自体になり、親ノードに関連しています。 ただし、選択したノードに子がある場合は、選択したノードを指すために XPath セレクター バインドだけが作成され、XPath フィールド バインドは作成されません。  

7. 次の表は、XPath セレクターおよび XPath フィールド バインド値で使用されるフィールド、 **ProcessPurchaseOrder**ポリシー。 (このポリシーには ApprovalRule というルールが 1 つだけあります)。  

| [フィールド名] |                                                             [XPath セレクター]                                                              |                    [XPath フィールド]                     | [XPath セレクター] (簡略化された形式) | [XPath フィールド]<br /><br /> (簡略化された形式) |
|------------|-----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|----------------------------------|-------------------------------------------|
|  Quantity  | /\*[ローカル名 () = 'PurchaseOrder' and namespace-uri() ='http://EAISolution.PurchaseOrder']/\*[ローカル名 () 'Item' and namespace-uri() = = '] | \*[ローカル名 () '数量' and namespace-uri() = = '] |       /PurchaseOrder/Item        |                 Quantity                  |
|   状態   |                       /\*[ローカル名 () = 'PurchaseOrder' and namespace-uri() ='<http://EAISolution.PurchaseOrder>']                        |  \*[ローカル名 () = 'Status' and namespace-uri() = ']  |          /PurchaseOrder          |                  状態                   |

<!---Loc Comment: Please, verify strucutre in line 183 and 184--->

#### <a name="to-view-the-xpath-selector-and-xpath-field-bindings-for-the-quantity-and-status-fields"></a>Quantity および Status フィールドに対する Xpath セレクターおよび Xpath フィールドのバインドを表示するには  

1. ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**、順に展開**バージョン 1.0**します。  

2. クリックして**ApprovalRule**します。  

3. 右側の [IF] ペインで次のようにクリックします。 **PO:/PurchaseOrder/Item/quantity**します。  

4. 前の表に示すように値を表示することを確認、 **XPath セレクター**と**XPath フィールド**プロパティ ウィンドウでバインドします。  

5. 手順 3. と 4. を繰り返して、 **PO:/purchaseorder/status**フィールド。  

   ルール エンジンは、子を作成します。 **TypedXmlDocument** 、元のオブジェクト**TypedXmlDocument**各 XPath セレクターに対して送信しました。 ポリシーで使用される 2 つの異なる XPath セレクターがあるため (**/PurchaseOrder/項目**の**数量**フィールドと **/PurchaseOrder**の**ステータス**フィールド)、ルール エンジンは、2 つの子を作成します。 **TypedXmlDocument**オブジェクトとルール エンジンの作業メモリにアサートします。  

> [!NOTE]
>  もう一度出力で、トレースを表示する**バージョン 1.0**ポリシー エクスプ ローラー ウィンドウ。  

 **条件の評価テスト (一致) 2006/8/31 1時 33分: 10 PM**  

 **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **ルール セット名: ProcessPurchaseOrder**  

 **テスト式: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  

 **左のオペランド値: 400**  

 **右のオペランド値: 500**  

 **テスト結果: True**  

 **議題の更新 2006/8/31 1時 33分: 10 PM**  

 **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **ルール セット名: ProcessPurchaseOrder**  

 **操作: 追加**  

 **ルール名: ApprovalRule**  

 **競合解決条件: 0**  

 ルール エンジンは、条件の評価、競合解決、およびアクションの実行という 3 つのステージによるアルゴリズムを使用してポリシーを実行します。 条件の評価のステージでは、ルール エンジンは、ポリシーのすべてのルールで条件を評価し、条件が議題に対して `true` と評価されているルールを追加します。 この簡単な例で、 **ProcessPurchaseOrder**ポリシーが 1 つのルール**ApprovalRule**します。 ルール エンジンでという条件を評価するため、**数量 < = 500**の**ApprovalRule**の値を使用して、**数量**フィールドに送信された XML ドキュメントこれは**400**します。 上記の出力には、左側のオペランド、右側のオペランド、およびテスト結果の値が表示されます。  

 第 2 段階である競合解決条件のステージでは、条件が `true` と評価されるルールがそれぞれの優先度に基づいた順序で議題に追加されます。 このシナリオでは、ルール エンジンを追加、 **ApprovalRule**議題にための条件、 **ApprovalRule**に評価される`true`します。 上記の出力に示すように、競合解決条件は、ルールの優先度のみ (**ApprovalRule**)。 クリックすると、 **ApprovalRule**ポリシー エクスプ ローラー ウィンドウでノードの値を表示する、**優先度**プロパティとして プロパティ ウィンドウで、規則を**0**、これは、ルールの既定値です。 ポリシーに複数のルールがあり、1 つのルールのアクションを別のルールのアクションの後に実行する必要がある場合は、適切に優先度を設定する必要があります。 数値が大きいほど、優先度が高くなります。  

 **2006 年 8 月 31 日に実行されたルール 1時 33分: 10 PM**  

 **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **ルール セット名: ProcessPurchaseOrder**  

 **ルール名: ApprovalRule**  

 **競合解決条件: 0**  

 最終段階であるアクションの実行のステージでは、ルール エンジンによってルールのアクションの実行が開始されます。 1 つのアクションがある、 **ApprovalRule**の値を設定する、**状態**フィールドに送信された XML ドキュメントに**Approved**します。  

 **ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**  

 **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **ルール セット名: ProcessPurchaseOrder**  

 **操作: 取り消し**  

 **オブジェクトの種類: TypedXmlDocument:PurchaseOrder**  

 **オブジェクト インスタンス識別子: 14626574**  

 **ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**  

 **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **ルール セット名: ProcessPurchaseOrder**  

 **操作: 取り消し**  

 **オブジェクトの種類: TypedXmlDocument:PurchaseOrder: PurchaseOrder/項目**  

 **オブジェクト インスタンス識別子: 43901854**  

 **ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**  

 **ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **ルール セット名: ProcessPurchaseOrder**  

 **操作: 取り消し**  

 **オブジェクトの種類: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**  

 **オブジェクト インスタンス識別子:** 64530307  

 送信されたすべてのファクト (**PurchaseOrder**) ルール エンジンと、ルール エンジンによって作成された子ファクトに基づいて、XPath セレクター (**\PurchaseOrder**と**\PurchaseOrder\Item**)取り消されます (削除)、ルール エンジンの作業メモリから。  

## <a name="analysis-of-the-output-from-the-second-test-samplepo2xml"></a>2 番目のテスト (samplepo2.xml) からの出力の分析  
 **条件の評価テスト (一致) 2006 年 9 月 5 日 5時 24分: 42 PM**  

 **ルール エンジン インスタンス識別子: b749d2fd-a883-4c2f-9974-5cf688010622**  

 **ルール セット名: ProcessPurchaseOrder**  

 **テスト式: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  

 **左のオペランド値: 700**  

 **右のオペランド値: 500**  

 **テスト結果:** False  

 条件を評価するルール エンジン (**数量 < = 500**) で、 **ApprovalRule** 、内の単一行を使用して**項目**オブジェクト。 左側のオペランド値は、の値であるを参照してください、**数量**、XML ドキュメント内の要素**700**します。 テスト結果は`false`ため**700 < = 500**ルールがルール エンジンの議題に追加されていないため、します。 議題にはルールが存在しません。 そのためを実行する操作はありませんしの値がありますが、**状態**フィールドは**XYZ**します。  

## <a name="comments"></a>コメント  

-   BizTalk アプリケーションなどのクライアント アプリケーションからポリシーを使用する前に、ポリシーをテストすることをお勧めします。  

-   と共にデータベース ファクトを使用するポリシーをテストするとき、 **DataConnection**ビジネス ルール作成ツールで、バインド、 **DataConnection**オブジェクトが自動的に作成します。 ただし、呼び出すと、同じポリシー オーケストレーションからを使用して、**ルールの呼び出し**図形、いいえ**DataConnection**オブジェクトがポリシーに自動的に渡されます。 作成する必要があります、 **DataConnection**オーケストレーション内のオブジェクトや、パラメーターとして渡すことをアサートするファクト取得コンポーネントを作成、 **DataConnection**オブジェクト、および使用するポリシーを構成します。ファクト取得コンポーネント。  

-   .NET ファクトを使用するポリシーをテストするには、ファクト作成コンポーネントを作成し、で指定する必要があります、 **[ファクトの**] ダイアログ ボックス。 ファクト作成コンポーネントの作成の詳細については、[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)を参照してください。 ポリシーがデータベース ファクトを使用する場合は、同じ処理を行うことができます (**TypedDataConnection**または**TypedDataTable**または**TypedDataRow**) または XML ファクト (**TypedXmlDocument**)。  

## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了すると、実行、[チュートリアル: オーケストレーションからポリシーを呼び出す](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)を呼び出す手順を説明するチュートリアル、 **ProcessPurchaseOrder**オーケストレーションからのポリシー。  

## <a name="see-also"></a>参照  
 [ポリシー テストのトレース出力](../core/policy-test-trace-output.md)   
 [条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md)   
 [議題と優先度](../core/agenda-and-priority.md)
