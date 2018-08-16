---
title: 'チュートリアル: 単純なビジネス ポリシーの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02d35735-dce2-4ee2-965e-dae307a125b0
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cecf7078592d322f9cc9777aeb530759c5ecf4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023864"
---
# <a name="walkthrough-creating-a-simple-business-policy"></a>チュートリアル: 単純なビジネス ポリシーの作成
このチュートリアルは、ビジネス ルール作成ツールを使用してという名前の単純なビジネス ポリシーを作成する手順を示します**ProcessPurchaseOrder**という名前の規則を含む**ApprovedRule**します。 **ApprovedRule**ルールは、ファクトとして XML ドキュメントを送信するユーザーを想定し、値を設定、**状態**フィールドをドキュメントに**Approved**場合、の値**数量**フィールドと等しいまたはそれよりも小さい**500**します。  
  
## <a name="prerequisites"></a>前提条件  
 このチュートリアルを実行するには、ビジネス ルール フレームワークの基礎を理解している必要があります。 ビジネス ルール フレームワークのアーキテクチャの概要を確認することをお勧め、ビジネス ルール フレームワークに慣れていない場合[ビジネス ルール エンジン](../core/business-rules-engine.md)このチュートリアルを実行する前にします。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 2 つの手順が含まれています。  
  
|プロシージャ タイトル|手順の説明|  
|---------------------|---------------------------|  
|PO スキーマ ファイルを作成するには|ドキュメントのスキーマを作成するための手順について説明します、 **ProcessPurchaseOrder**ポリシーが使用されます。|  
|ProcessPurchaseOrder ポリシーを作成するには|作成するための手順について説明します、 **ProcessPurchaseOrder**ビジネス ルール作成ツールを使用してポリシー。|  
  
### <a name="to-create-the-po-schema-file"></a>PO スキーマ ファイルを作成するには  
  
1.  **開始**] メニューの [open**メモ帳**します。  
  
2.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[ファイル]** をクリックします。  
  
3.  次の XML テキストをエディターにコピーします。  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://EAISolution.PurchaseOrder" targetNamespace="http://EAISolution.PurchaseOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="PurchaseOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="Header">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="ReqID" type="xs:string" />  
                  <xs:element name="Date" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Item">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Description" type="xs:string" />  
                  <xs:element name="Quantity" type="xs:int" />  
                  <xs:element name="UnitPrice" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Status" type="xs:string" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
4.  **ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**します。  
  
5.  値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)** に**すべてのファイル**します。  
  
6.  型**PO.xsd**で、**ファイル名**テキスト ボックスに、ディレクトリに移動します**C:\BRE-Walkthroughs**の値を変更**エンコード**に**Unicode**し**保存**します。  
  
    > [!NOTE]
    >  ディレクトリを作成**BRE チュートリアル** **c:\\** が存在して、をクリックしなかった場合**保存**します。  
  
7.  メモ帳を閉じます。  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a>ProcessPurchaseOrder ビジネス ポリシーを作成するには  
  
1. **開始**] メニューの [open**ビジネス ルール作成ツール**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
   > [!NOTE]
   >  ビジネス ルール作成ツールが表示されます、**ルール ストアを開く** ダイアログ ボックスをコンピューターに初めて開かれたとき。 表示された場合、**ルール ストアを開く**ダイアログ ボックスで、をクリックして**OK** SQL server 名とデータベース名を確認した後。  
  
2. ポリシー エクスプ ローラー ウィンドウで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。  
  
3. ポリシーの名前を編集**Policy1**を**ProcessPurchaseOrder** ENTER キーを押します。 ポリシーの名前を変更することも、**プロパティ**ウィンドウ。  
  
4. 右クリックして**バージョン 1.0**、 をクリックし、**新しいルールの追加**します。  
  
5. ルールの名前を編集**Rule1**に**ApprovalRule** ENTER キーを押します<strong>します。</strong> ルールの名前を変更することも、**プロパティ**ウィンドウ。  
  
6. [ファクト エクスプ ローラー] ウィンドウ、 **XML スキーマ**タブ。  
  
7. 右クリック**スキーマ**、 をクリックして**参照**を選び、 **PO.xsd**先ほど作成したファイル。  
  
8. [プロパティ] ウィンドウでの値を変更、**ドキュメントの種類**プロパティから**PO**に**RuleTest.PO**します。  
  
   > [!NOTE]
   >  という名前の BizTalk プロジェクトを作成して**RuleTest**後半、[チュートリアル: オーケストレーションからポリシーを呼び出す](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)チュートリアル。 チュートリアルを追加しますが、 **PO.xsd**をプロジェクトにファイルを呼び出すオーケストレーションを作成、 **ProcessPurchaseOrder**ポリシー、およびポリシーをテストします。 オーケストレーションからポリシーをテストするには、変更することを確認する必要があります、**ドキュメントの種類**プロパティを**\<プロジェクト名\>.\<SchemaName\>**、これは**RuleTest.PO**ここでします。  
  
    ![BRE&#45;チュートリアル&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")  
  
9. ファクト エクスプ ローラー ウィンドウで、 **PurchaseOrder**、順に展開**項目**します。  
  
10. 右側の場合にペイン (上部)、右クリック**条件**、 をクリックして**述語**、 をクリックし、 **以下**。  
  
     ![ビジネス ルール作成ツール&#45;以下](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")  
  
11. ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**引数 1** IF ペインでします。  
  
     ![ビジネス ルール作成ツール&#45;DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")  
  
     ![ビジネス ルール作成ツール&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")  
  
12. [IF] ペインで、クリックして **[引数 2]**、型`500`、し、ENTER キーを押します。  
  
13. ドラッグ、**状態**ノードをファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの下部にある右側にある THEN ペインにします。  
  
     ![ビジネス ルール作成ツール&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")  
  
14. [THEN] ペインで、次のようにクリックします。 **\<値を入力します\>** し、入力**Approved**。  
  
15. ポリシー エクスプ ローラー ウィンドウで右クリック**バージョン 1.0 (未保存)**、 をクリックし、**保存**します。  
  
## <a name="comments"></a>コメント  
  
-   ポリシーには、1 つ以上のルールを含めることができます。 別のルールを追加して**DeniedRule**の[チュートリアル: ポリシーにルールを追加する](../core/walkthrough-adding-a-rule-to-the-policy.md)チュートリアル。  
  
-   ポリシーが保存済みの状態であれば、ポリシーを変更して、さらにルールを追加したり、条件を変更したり、アクションを変更することができます。  
  
-   指定してルールの実行を優先することができます、**優先度**ビジネス ルール作成ツールでルールのプロパティ。 たとえばをクリックする、 **ApprovedRule**ポリシー エクスプ ローラー ウィンドウでノードを確認できます、**優先度**プロパティ ウィンドウでプロパティ。 数字が大きくなるほど、そのルールの優先順位は高くなります。  
  
-   ポリシーのデータ ソースとして、XML スキーマ、データベース、または .NET アセンブリを使用できます。 このチュートリアルでは、データ ソースとして XML スキーマを使用しました。 ポリシーを実行するには、ファクトとしてスキーマの XML ドキュメント インスタンスをルール エンジンに送信する必要があります。  
  
## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)をテストするための手順を説明するチュートリアル、 **ProcessPurchaseOrder**ポリシーします。このチュートリアルで作成します。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルールについて](../core/about-business-rules.md)