---
title: 'チュートリアル: ファクト作成コンポーネントの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041c8f73-c72e-43fd-8446-144cecdc95ef
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbe1e856ad97d81a153828a4d5ae45795670ed1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017323"
---
# <a name="walkthrough-creating-a-fact-creator"></a>チュートリアル: ファクト作成コンポーネントの作成
このチュートリアルは、ファクト作成コンポーネントを作成する手順を示します**POFactCreator**、テストに使用できる、 **ProcessPurchaseOrder**で先ほど作成したポリシーチュートリアル。  

## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。  

## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 2 つの手順が含まれています。  

|プロシージャ タイトル|手順の説明|  
|---------------------|---------------------------|  
|POFactCreator コンポーネントを作成するには|ファクト作成コンポーネントを作成するための手順について説明します**POFactCreator**します。|  
|POFactCreator を使用して ProcessPurchaseOrder ポリシーをテストするには|ビジネス ルール作成ツールを使用してテストする手順について説明します、 **ProcessPurchaseOrder**ポリシーを使用して、 **POFactCreator**コンポーネント。|  

### <a name="to-create-the-pofactcreator-component"></a>POFactCreator コンポーネントを作成するには  

1. 開始**Microsoft Visual Studio**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  

3. **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  


   |             プロパティ              |                             目的                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **プロジェクトの種類**         |                        クリックして**Visual c#** します。                         |
   |           **[テンプレート]**           |                      クリックして**クラス ライブラリ**します。                       |
   |             **名前**              |                     型**POFactCreatorLib**します。                      |
   |           **場所**            |          指定**C:\BRE-Walkthroughs**場所として。           |
   |         **[ソリューション名]**         |                     型**POFactCreatorSol**します。                      |
   | **ソリューションのディレクトリを作成します。** | ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。 |


4. **[OK]** をクリックします。 **POFactCreatorLib**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  

5. [プロパティ] ウィンドウで、ファイルの名前を変更する**Class1.cs**を**POFactCreator.cs**します。  

6. ソリューション エクスプ ローラー ウィンドウで右クリック**参照**、 をクリックし、**参照の追加**します。  

7. をクリックして**参照**に移動します**C:\Program files \common files \microsoft BizTalk**、し、ダブルクリック **[microsoft.ruleengine.dll]** します。  

8. 先頭に次の行を追加、 **POFactCreator.cs**既存の後にファイルを`using`ステートメント。  

   ```  
   //To use the XmlDocument class  
   using System.Xml;  
   //To use the TypedXmlDocument and Policy classes  
   using Microsoft.RuleEngine;   
   ```  

9. 変更、 **POFactCreator**クラスから派生する、 **IFactCreator**インターフェイス。  

    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  

10. 右クリックして**IFactCreator**、 をポイント**インターフェイスの実装**、順にクリックします**インターフェイスの実装**します。  

     ![BRE&#45;チュートリアル&#45;ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")  

11. パブリック コンストラクターを追加、 **POFactCreator**次に示すようにクラスします。  

    ```  
    public POFactCreator()  
    {  
    }  
    ```  

12. 唯一のステートメントを削除、 **CreateFacts**メソッド。  

13. 次のコードを追加、 **CreateFacts**を作成する方法、 **TypedXmlDocument**オブジェクトに基づいて、 **SamplePO.xml**ドキュメント。  

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

15. ファクトの配列から返された場合、 **CreateFacts**メソッド。  

    ```  
    return facts;  
    ```  

16. いることを確認で完全なコード、 **CreateFacts**メソッドは、次のようにします。  

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

17. 唯一のステートメントを削除、 **GetFactTypes**メソッド。  

18. 次のコードを追加、 **GetFactTypes**の種類を含む型の配列を返すメソッドを**TypedXmlDocument**クラス。  

    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  

19. 開始**Visual Studio コマンド プロンプト**します。  

20. ディレクトリに移動します**C:\BRE-Walkthroughs\POFactCreatorSol**、次のコマンドを実行します。  

     **Sn-k POFactCreator.snk**  

21. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、**プロパティ**、し、ダブルクリック**AssemblyInfo.cs**します。  

22. 次のステートメントを追加、 **AssemblyInfo.cs**最後にファイル。  

    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  

23. ソリューション エクスプ ローラー ウィンドウで右クリック**POFactCreatorLib**、 をクリックし、**ビルド**します。  

24. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動します**C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**、し登録するには、次のコマンドを実行し、 **POFactCreator**コンポーネントを GAC (グローバル アセンブリ キャッシュ)。 コマンド プロンプトが開いていない場合は、手順 19. に従って開きます。  

     **Gacutil-i POFactCreatorLib.dll**  

### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a>POFactCreator を使用して ProcessPurchaseOrder ポリシーをテストするには  

1. **開始**メニューで、**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。 ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。  

   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  

2. ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**、最新のバージョンを右クリックし、**ポリシーのテスト**します。  

    ![ビジネス ルール作成ツール&#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")  

3. ダイアログ ボックスの下部には、次のようにクリックします。**追加**します。  

4. **.NET アセンブリ**ダイアログ ボックスで、 **POFactCreatorLib**、順にクリックします**OK**します。  

5. **バインドの選択**ダイアログ ボックスで、をクリックして**POFactCreator**で**POFactCreatorLib、10.0.0**、順にクリックします**OK**。  

6. クリックして**テスト**します。  

7. いることを確認、 **ApprovalRule**が出力ウィンドウに発生します。  

## <a name="comments"></a>コメント  

-   .NET クラスの非静的メソッドを使用するポリシーをビジネス ルール作成ツールでテストするには、ファクト作成コンポーネントを作成する必要があります。  

## <a name="see-also"></a>参照  
 [ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)