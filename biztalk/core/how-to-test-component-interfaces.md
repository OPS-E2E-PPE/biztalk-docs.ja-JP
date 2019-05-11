---
title: コンポーネント インターフェイスをテストする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8450177cd97d7136d8ee4146ff93fceee20b351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333853"
---
# <a name="how-to-test-component-interfaces"></a>コンポーネント インターフェイスをテストする方法
Microsoft BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft メタデータとコンポーネントのインターフェイスです。そのため、新しいまたは変更されたコンポーネントのインターフェイスに対応できます。 アダプターによりの前提条件コンポーネント インターフェイスについてが、論理的かつ有効です。 そのため、アダプターのソースとして使用される前に、各コンポーネントのインターフェイスをテストする必要があります。  
  
 ユーザーまたは PeopleSoft のアップグレードによって、基になるアプリケーションに変更が行われた変更が、コンポーネント インターフェイスを無効になる場合は、ユーザーは、アダプタが使用前に、無効なコンポーネント インターフェイスを修復する必要があります。  
  
### <a name="to-test-a-component-interface"></a>コンポーネント インターフェイスをテストするには  
  
1.  アプリケーション デザイナーでの**ツール** メニューのをクリックして**Test Component Interface**します。  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  **Component Interface Tester**  ダイアログ ボックスで、次のメソッドを 1 つを使用してコンポーネント インターフェイスをテストします。 変更が完了したら、ウィンドウの最上位の項目を右クリックします。  
  
    > [!NOTE]
    >  必要な場合は、フォア グラウンドに表示させる ダイアログ ボックスをクリックします。  
  
    -   Find メソッドを使用してコンポーネント インターフェイスをテストするには、クリックして**検索**します。  
  
         **Component Interface Tester - 検索結果** ダイアログ ボックスが開き、基になるコンポーネントのすべての可能なエントリを表示します。 300 以上のエントリがある場合は、メッセージが表示されます。  
  
         A. 左側のウィンドウで、**検索結果** ダイアログ ボックスで、フィールドを選択します。  
  
         B. その特定のフィールドに関連するデータを表示する をクリックして**Get Selected**します。  
  
         次の画面が表示されます。  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         セキュリティ設定で許可される場合は、個々 のフィールドの値を変更できます。  
  
         次のダイアログ ボックスが開きます。  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   使用してコンポーネント インターフェイスをテストする、`Get`メソッド。  
  
         A. 既存のキーを入力します。  
  
         B. クリックして**既存**します。  
  
         これは、入力したキーの公開されているプロパティを返します。  
  
         値を変更するには、場合**更新アクセス**が指定されました。  
  
         使用してをテストする代わりに、`Create`メソッド。  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   使用してコンポーネント インターフェイスをテストする、`Create`メソッド。  
  
         A. 必要なすべてのキー値を入力します。  
  
         B. クリックして**新規作成**です。  
  
         有効な値を入力すると**キーを作成する**テーブル名には、配置の既定のデータが展開されてから、JOBCODE データを表示するウィンドウが開きます。  
  
         これでフィールドを変更できます。  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         変更は、コンポーネントの基になるビジネス ロジックに対して検証されます。  
  
3.  をクリックして変更を保存、**保存**アイコン。  
  
     レコードの作成に使用されるキーは、データを表示するための Get メソッドで使用できます。 追加されたデータは、次の例に示すように、PeopleSoft コンポーネントで表示できます。  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     **有効日**は既定値の 1 つです。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)   
 [付録 c:コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md)