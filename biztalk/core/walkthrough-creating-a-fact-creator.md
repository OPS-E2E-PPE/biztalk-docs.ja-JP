---
title: "チュートリアル: ファクト作成コンポーネントの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 041c8f73-c72e-43fd-8446-144cecdc95ef
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a1c91417cb58eb53e35c724513d4f955e4e6b6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-creating-a-fact-creator"></a>チュートリアル: ファクト作成コンポーネントの作成
このチュートリアルは、ファクト作成コンポーネントを作成する手順を示します**POFactCreator**、テストに使用できる、 **ProcessPurchaseOrder**以前で作成したポリシーチュートリアル。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 2 つの手順が含まれています。  
  
|手順のタイトル|手順の説明|  
|---------------------|---------------------------|  
|POFactCreator コンポーネントを作成するには|ファクト作成コンポーネントを作成するための手順をわかりやすく説明**POFactCreator**です。|  
|POFactCreator を使用して、ProcessPurchaseOrder ポリシーをテストするには|ビジネス ルール作成ツールを使用してテストするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーを使用して、 **POFactCreator**コンポーネントです。|  
  
### <a name="to-create-the-pofactcreator-component"></a>POFactCreator コンポーネントを作成するには  
  
1.  開始**Microsoft Visual Studio**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|をクリックして**Visual c#**です。|  
    |**[テンプレート]**|をクリックして**クラス ライブラリ**です。|  
    |**名前**|型**POFactCreatorLib**です。|  
    |**場所**|指定**C:\BRE-Walkthroughs**場所として。|  
    |**[ソリューション名]**|型**POFactCreatorSol**です。|  
    |**ソリューションのディレクトリを作成します。**|ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。|  
  
4.  **[OK]**をクリックします。 **POFactCreatorLib**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  
  
5.  [プロパティ] ウィンドウで、ファイルの名前変更**Class1.cs**を**POFactCreator.cs**です。  
  
6.  ソリューション エクスプ ローラー ウィンドウで右クリック**参照**、クリックして**参照の追加**です。  
  
7.  をクリックして**参照**に移動**C:\Program files \common files \microsoft BizTalk**、順にダブルクリック**[microsoft.ruleengine.dll]**です。  
  
8.  先頭に次の行を追加、 **POFactCreator.cs**後、既存のファイル`using`ステートメント。  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
9. 変更、 **POFactCreator**から派生するクラス、 **IFactCreator**インターフェイス。  
  
    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  
  
10. 右クリック**IFactCreator**、をポイント**インターフェイスの実装**、クリックして**インターフェイスの実装**です。  
  
     ![BRE &#45;チュートリアル &#45; ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")  
  
11. Public コンス トラクターを追加、 **POFactCreator**クラスの次のようにします。  
  
    ```  
    public POFactCreator()  
    {  
    }  
    ```  
  
12. 唯一のステートメントを削除、 **CreateFacts**メソッドです。  
  
13. 次のコードを追加、 **CreateFacts**メソッドを作成、 **TypedXmlDocument**オブジェクトに基づいて、 **SamplePO.xml**ドキュメント。  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
14. ファクトの配列を作成する次のコードを追加、 **TypedXmlDocument**オブジェクトのみのファクトとして。  
  
    ```  
    object[] facts = new object[1];  
    facts[0] = txd;   
    ```  
  
15. ファクトの配列からの戻り値、 **CreateFacts**メソッド。  
  
    ```  
    return facts;  
    ```  
  
16. いることを確認で完全なコード、 **CreateFacts**メソッドは、次のようになります。  
  
    ```  
    public object[] CreateFacts(RuleSetInfo ruleSetInfo)  
    {  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
  
    object[] facts = new object[1];  
    facts[0] = txd;  
    return facts;  
    }  
    ```  
  
17. 唯一のステートメントを削除、 **GetFactTypes**メソッドです。  
  
18. 次のコードを追加、 **GetFactTypes**の型を含む型の配列を返すメソッドを**TypedXmlDocument**クラス。  
  
    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  
  
19. 開始**Visual Studio コマンド プロンプト**です。  
  
20. ディレクトリに移動**C:\BRE-Walkthroughs\POFactCreatorSol**、次のコマンドを実行します。  
  
     **Sn-k POFactCreator.snk**  
  
21. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、**プロパティ**、順にダブルクリック**AssemblyInfo.cs**です。  
  
22. 次のステートメントを追加、 **AssemblyInfo.cs**最後のファイル。  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  
  
23. ソリューション エクスプ ローラー ウィンドウで右クリック**POFactCreatorLib**、クリックして**ビルド**です。  
  
24. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動**C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**、登録するには、次のコマンドを実行し、 **POFactCreator**コンポーネントを GAC (グローバル アセンブリ キャッシュ)。 コマンド プロンプトが開いていない場合は、手順 19. に従って開きます。  
  
     **Gacutil-i POFactCreatorLib.dll**  
  
### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a>POFactCreator を使用して、ProcessPurchaseOrder ポリシーをテストするには  
  
1.  **開始**メニューのをポイント**すべてのプログラム**、をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、クリックして**ビジネス ルール作成ツール**です。 ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  ポリシー エクスプ ローラー] ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**最新バージョンを右クリックし、[クリックして**テスト ポリシー**です。  
  
     ![ビジネス ルール作成ツール &#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")  
  
3.  ダイアログ ボックスの下部には、をクリックして**追加**です。  
  
4.  **.NET アセンブリ**ダイアログ ボックスで、 **POFactCreatorLib**、順にクリック**OK**です。  
  
5.  **バインドの選択**ダイアログ ボックスで、をクリックして**POFactCreator**で**POFactCreatorLib、10.0.0**、クリックして**[ok]**です。  
  
6.  をクリックして**テスト**です。  
  
7.  いることを確認、 **ApprovalRule**出力ウィンドウには、発生します。  
  
## <a name="comments"></a>コメント  
  
-   .NET クラスの非静的メソッドを使用するポリシーをビジネス ルール作成ツールでテストするには、ファクト作成コンポーネントを作成する必要があります。  
  
## <a name="see-also"></a>参照  
 [ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)