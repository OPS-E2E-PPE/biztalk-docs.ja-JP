---
title: 'チュートリアル: 単純なビジネス ポリシーの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 1eb4f21cf9311399ef6092b95fa818547679a240
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975821"
---
# <a name="walkthrough-creating-a-simple-business-policy"></a>チュートリアル: 単純なビジネス ポリシーを作成します。
このチュートリアルは、ビジネス ルール作成ツールを使用してという名前の単純なビジネス ポリシーを作成する手順を示します**ProcessPurchaseOrder**という名前のルールを含む**ApprovedRule**です。 **ApprovedRule**ルールは、ユーザーが、ファクトとして XML ドキュメントを送信するを必要としの値を設定、**ステータス**フィールドをドキュメントに**Approved**場合、の値**数量**フィールドは、以下を**500**です。  
  
## <a name="prerequisites"></a>前提条件  
 このチュートリアルを実行するには、ビジネス ルール フレームワークの基礎を理解している必要があります。 ビジネス ルール フレームワークのアーキテクチャの概要を読むことをお勧め、ビジネス ルール フレームワークを新しい場合は、[ビジネス ルール エンジン](../core/business-rules-engine.md)このチュートリアルを実行する前にします。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 2 つの手順が含まれています。  
  
|手順のタイトル|手順の説明|  
|---------------------|---------------------------|  
|PO スキーマ ファイルを作成するには|ドキュメントのスキーマを作成するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーが使用されます。|  
|ProcessPurchaseOrder ポリシーを作成するには|作成するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ビジネス ルール作成ツールを使用してポリシー。|  
  
### <a name="to-create-the-po-schema-file"></a>PO スキーマ ファイルを作成するには  
  
1.  **開始**] メニューの [開いている**メモ帳**です。  
  
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
  
4.  **ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**です。  
  
5.  値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)** に**すべてのファイル**です。  
  
6.  型**PO.xsd**で、**ファイル名**テキスト ボックスで、ディレクトリに移動**C:\BRE-Walkthroughs**の値を変更**エンコード**に**Unicode**  をクリックし、**保存**です。  
  
    > [!NOTE]
    >  ディレクトリを作成**BRE チュートリアル** **c:\\** それが存在してをクリックしなかった場合**保存**です。  
  
7.  メモ帳を閉じます。  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a>ProcessPurchaseOrder ビジネス ポリシーを作成するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
    > [!NOTE]
    >  ビジネス ルール作成ツールを表示、**ルール ストアを開く** ダイアログ ボックスを初めてコンピューターで開かれたとき。 表示される場合、**ルール ストアを開く**ダイアログ ボックスで、をクリックして**OK** SQL server 名とデータベース名を確認した後です。  
  
2.  ポリシー エクスプ ローラー ウィンドウで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。  
  
3.  ポリシーの名前を編集 **"policy1"** を**ProcessPurchaseOrder** ENTER キーを押します。 ポリシーの名前を変更することも、**プロパティ**ウィンドウです。  
  
4.  右クリック**バージョン 1.0**、クリックして**新しいルールの追加**です。  
  
5.  ルールの名前を編集**Rule1**に**ApprovalRule** ENTER キーを押します**です。** 内のルールの名前を変更することも、**プロパティ**ウィンドウです。  
  
6.  [ファクト エクスプ ローラー] ウィンドウ、 **XML スキーマ**タブです。  
  
7.  右クリック**スキーマ**、 をクリックして**参照**、クリックして、 **PO.xsd**先ほど作成したファイルです。  
  
8.  [プロパティ] ウィンドウでの値を変更、**ドキュメントの種類**プロパティから**PO**に**RuleTest.PO**です。  
  
    > [!NOTE]
    >  という名前の BizTalk プロジェクトを作成して**RuleTest**後半、[チュートリアル: オーケストレーションからポリシーを呼び出す](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)チュートリアルです。 チュートリアルでは、追加点で、 **PO.xsd**ファイルをプロジェクトを呼び出すオーケストレーションを作成、 **ProcessPurchaseOrder**ポリシー、およびポリシーをテストします。 オーケストレーションからポリシーをテストするを変更することを確認する必要があります、**ドキュメントの種類**プロパティを**\<プロジェクト名\>.\<SchemaName\>**、これは**RuleTest.PO**ここでします。  
  
     ![BRE &#45;チュートリアル &#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")  
  
9. ファクト エクスプ ローラー ウィンドウで、 **PurchaseOrder**の順に展開および**項目**です。  
  
10. IF ペイン (上部) の右側を右クリックし**条件**をクリックして**述語**、順にクリック**以下**です。  
  
     ![ビジネス ルール作成ツール &#45;以下](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")  
  
11. ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**argument1** IF ペイン。  
  
     ![ビジネス ルール作成ツール &#45;DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")  
  
     ![ビジネス ルール作成ツール &#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")  
  
12. IF ペインで、をクリックして**argument2**、型`500`、ENTER キーを押します。  
  
13. ドラッグ、**ステータス**ノード、ファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右側下部の THEN ペインにします。  
  
     ![ビジネス ルール作成ツール &#45; DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")  
  
14. [THEN] ペインでをクリックして**\<値を入力\>** し入力**Approved**です。  
  
15. ポリシー エクスプ ローラー ウィンドウで右クリック**バージョン 1.0 (未保存)**、クリックして**保存**です。  
  
## <a name="comments"></a>コメント  
  
-   ポリシーには、1 つ以上のルールを含めることができます。 別のルールを追加する**DeniedRule**で、[チュートリアル: ポリシーにルールを追加する](../core/walkthrough-adding-a-rule-to-the-policy.md)チュートリアルです。  
  
-   ポリシーが保存済みの状態であれば、ポリシーを変更して、さらにルールを追加したり、条件を変更したり、アクションを変更することができます。  
  
-   指定してルールの実行を優先することができます、**優先度**ビジネス ルール作成ツールでルールのプロパティです。 たとえばをクリックする、 **ApprovedRule**ポリシー エクスプ ローラー ウィンドウでノードを確認できます、**優先度**プロパティ ウィンドウでプロパティです。 数字が大きくなるほど、そのルールの優先順位は高くなります。  
  
-   ポリシーのデータ ソースとして、XML スキーマ、データベース、または .NET アセンブリを使用できます。 このチュートリアルでは、データ ソースとして XML スキーマを使用しました。 ポリシーを実行するには、ファクトとしてスキーマの XML ドキュメント インスタンスをルール エンジンに送信する必要があります。  
  
## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)テストするための手順を説明するチュートリアル、 **ProcessPurchaseOrder**ポリシーします。このチュートリアルで作成します。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルールについて](../core/about-business-rules.md)