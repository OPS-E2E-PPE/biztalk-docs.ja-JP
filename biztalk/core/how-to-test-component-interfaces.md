---
title: "コンポーネント インターフェイスをテストする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be50521e5c4421d8ac8902bcf7a414d734c3b9f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-component-interfaces"></a>コンポーネント インターフェイスをテストする方法
Microsoft BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft メタデータとコンポーネント インターフェイスを使用するため、新規または変更したコンポーネント インターフェイスを処理できます。 アダプタは、コンポーネント インターフェイスが論理的かつ有効であることを除き、コンポーネント インターフェイスについて想定を行いません。 したがって、各コンポーネント インターフェイスをアダプタのソースとして使用する前にテストする必要があります。  
  
 ユーザーまたは PeopleSoft のアップグレードによって基になるアプリケーションに変更が加えられ、その変更によってコンポーネント インターフェイスが無効になる場合は、無効なコンポーネント インターフェイスをアダプタが使用する前に修正する必要があります。  
  
### <a name="to-test-a-component-interface"></a>コンポーネント インターフェイスをテストするには  
  
1.  アプリケーション デザイナーでの**ツール** メニューのをクリックして**Test Component Interface**です。  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  **Component Interface Tester**  ダイアログ ボックスで、1 つに、次のメソッドを使用してコンポーネント インターフェイスをテストします。 変更を加えたら、ペインの一番上にあるアイテムを右クリックします。  
  
    > [!NOTE]
    >  必要に応じて、ダイアログ ボックスをクリックして前面に表示します。  
  
    -   Find メソッドを使用してコンポーネント インターフェイスをテストするには、クリックして**検索**です。  
  
         **Component Interface Tester - の検索結果** ダイアログ ボックスが開き、基になるコンポーネントの考えられるすべてのエントリを表示します。 エントリの数が 300 を超える場合は、メッセージが表示されます。  
  
         a. 左側のウィンドウで、**検索結果** ダイアログ ボックスでフィールドを選択します。  
  
         b. その特定のフィールドに関連するデータを表示する をクリックして**Get Selected**です。  
  
         次の画面が表示されます。  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         セキュリティ設定で許可される場合は、各フィールドの値を変更できます。  
  
         次のダイアログ ボックスが開きます。  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   使用してをコンポーネント インターフェイスをテストする、`Get`メソッド。  
  
         a. 既存のキーを入力します。  
  
         b. をクリックして**既存**です。  
  
         入力したキーについて公開されているプロパティが返されます。  
  
         値を変更するには、場合**更新アクセス**が指定されました。  
  
         または、`Create` メソッドを使用してテストすることもできます。  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   使用してをコンポーネント インターフェイスをテストする、`Create`メソッド。  
  
         a. 必要なすべてのキー値を入力します。  
  
         b. をクリックして**新規作成**です。  
  
         有効な値を入力すると**キーを作成する**場所の既定データとテーブル名が展開された後に、JOBCODE データを表示するウィンドウが開きます。  
  
         この段階で、フィールドを変更できます。  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         コンポーネントの基になるビジネス ロジックに対して、変更が検証されます。  
  
3.  をクリックして変更を保存、**保存**アイコン。  
  
     レコードの作成に使用されるキーは、データを表示するために Get メソッドと共に使用できます。 追加されたデータは、次の例に示すように、PeopleSoft コンポーネントで表示できます。  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     **発効日**既定値の 1 つです。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)   
 [付録 c: コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md)